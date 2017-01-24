.. _java_client:

Writing Hermes 2 WS Clients Using Java
======================================

Introduction
------------
This article is purposed to assist developers who want to write a Hermes 2 web service client using **Java**.
For information about installing Hermes 2 and communicating with Hermes 2 using an external application, please refer to :doc:`installation` and :doc:`web_service_communication`.

The source code shown below is originally from the :download:`Hermes 2 loopback test <_static/hermes2_loopback.zip>`. Please refer to it for more details.
The sample code assumes that Hermes 2 is using :literal:`localhost` with port :literal:`8080` (the default port of Tomcat).

Prerequisite
------------
The sample code requires the libraries shown below:

* :file:`saaj-api.jar` and :file:`saaj-impl.jar` (Starting from JDK 1.6, this is bundled with the JDK)
* :file:`activation.jar`
* :file:`mail.jar`

Global import for web service sample code
-----------------------------------------
Each web service sample code requires at **least** the imports shown below to run properly:

.. code-block:: java

   import java.net.URL;
   import java.net.MalformedURLException;
   import javax.activation.DataHandler;
   import javax.activation.FileDataSource;
   import javax.xml.soap.AttachmentPart;
   import javax.xml.soap.MessageFactory;
   import javax.xml.soap.Name;
   import javax.xml.soap.SOAPBody;
   import javax.xml.soap.SOAPConnection;
   import javax.xml.soap.SOAPConnectionFactory;
   import javax.xml.soap.SOAPElement;
   import javax.xml.soap.SOAPException;
   import javax.xml.soap.SOAPFactory;
   import javax.xml.soap.SOAPMessage;

Writing an ebMS 2.0 sender web service client
---------------------------------------------
We need to create a SOAP message with 10 paremeters and send it to Hermes 2 as the web service request.
The parameters are :literal:`cpaId,` :literal:`service,` :literal:`action,` :literal:`convId,` :literal:`fromPartyId,` :literal:`fromPartyType,` :literal:`toPartyId,` :literal:`toPartyType,` :literal:`refToMessageId` and :literal:`serviceType`.

#. Define a namespace URI and prefix conforming to WSDL, and define the endpoint URL of the ebMS sender web service.
   
   .. code-block:: java
      
      private String nsURI = "http://service.ebms.edi.cecid.hku.hk/";
      private String nsPrefix = "tns";
      private URL senderWSURL = "http://localhost:8080/corvus/httpd/ebms/sender";

#. Create a SOAP message factory and SOAP message object.
   
   .. code-block:: java

      SOAPMessage request = MessageFactory.newInstance().createMessage(); 

#. Populate the SOAP body by filling in the required parameters. For example:
   
   .. code-block:: xml
      
      <cpaId> ebmscpaid </cpaId>
      <service> http://localhost:8080/corvus/httpd/ebms/inbound <service>
      <action> action </action>
      <convId> convId </convId>
      <fromPartyId> fromPartyId </fromPartyId>
      <fromPartyType> fromPartyType </fromPartyType>
      <toPartyId> toPartyId </toPartyId>
      <toPartyType> toPartyType </toPartyType>
      <refToMessageId> </refToMessageId>
      <serviceType> </serviceType>
    
   Sample WSDL request for the ebMS sender web service:
   
   .. code-block:: java
      
      SOAPBody soapBody = request.getSOAPBody();
      soapBody.addChildElement(createElement("cpaId", nsPrefix, nsURI, cpaId));
      soapBody.addChildElement(createElement("service", nsPrefix, nsURI, service));
      soapBody.addChildElement(createElement("action", nsPrefix, nsURI, action));
      soapBody.addChildElement(createElement("convId", nsPrefix, nsURI, conversationId));
      soapBody.addChildElement(createElement("fromPartyId", nsPrefix, nsURI, fromPartyId));
      soapBody.addChildElement(createElement("fromPartyType", nsPrefix, nsURI, fromPartyType));
      soapBody.addChildElement(createElement("toPartyId", nsPrefix, nsURI, toPartyId));
      soapBody.addChildElement(createElement("toPartyType", nsPrefix, nsURI, toPartyType));
      soapBody.addChildElement(createElement("refToMessageId", nsPrefix, nsURI, refToMessageId));
      soapBody.addChildElement(createElement("serviceType", nsPrefix, nsURI, serviceType));
   
   The method :code:`createElement` creates a SOAP element with namespace prefix equal to :literal:`nsPrefix,` namespace URL equal to :literal:`nsURI` and textual value equal to the last arguments of the method.
   
   The implementation of ``createElement`` is shown below:
   
   .. code-block:: java
   
      SOAPElement soapElement = SOAPFactory.newInstance().createElement(localName, nsPrefix, nsURI); 
      soapElement.addTextNode(value);
      return soapElement;

#. Attach a payload if necessary. The example here uses a purchase order XML as the payload of the ebMS message, so the associated content type is :code:`application/xml`.

   .. code-block:: java

      AttachmentPart attachmentPart = request.createAttachmentPart();
      FileDataSource fileDS = new FileDataSource(new File("purchase_order.xml"));
      attachmentPart.setDataHandler(new DataHandler(fileDS));
      attachmentPart.setContentType("application/xml");
      request.addAttachmentPart(attachmentPart); 

#. Save changes to the SOAP message.

   .. code-block:: java
      
      request.saveChange();

#. Send the SOAP request to Hermes 2 ebMS sender web service and get a SOAP response.
   
   .. code-block:: java
      
      SOAPMessage response = soapConn.call(request, senderWSURL);
      SOAPBody responseBody = response.getSOAPBody();

#. Process the SOAP response and extract the identifier of the requested ebMS message to ``System.out`` if there is no SOAP fault.
   
   .. code-block:: java
      
      if (!responseBody.hasFault()){
          SOAPElement messageIdElement = getFirstChild(responseBody, "message_id", nsURI);
          System.out.println(messageIdElement == null ? null : messageIdElement.getValue());
      } else {
          throw new SOAPException(responseBody.getFault().getFaultString());
      }

   The method :code:`getFirstChild` gets the first element with the name :code:`message_id` and namespace URI equal to :literal:`nsURI`.
   An existing :code:`message_id` signifies that the message has been successfully sent to Hermes 2 and has a registered identifier.

   The SOAP request is now transformed into an ebMS message and saved in persistent storage.
   Hermes 2 will deliver the ebMS message to the partner specified in the SOAP request parameters (:literal:`cpaId`, :literal:`service` and :literal:`action` identify the partnership).

Writing an ebMS 2.0 receiver list web service client
----------------------------------------------------
We need to create a SOAP message with 9 parameters and send it to Hermes 2 as the web service request.
The parameters are :literal:`cpaId`, :literal:`service`, :literal:`action`, :literal:`convId`, :literal:`fromPartyId`, :literal:`fromPartyType`, :literal:`toPartyId`, :literal:`toPartyType` and :literal:`numOfMessages`.

#. Define a namespace URI and prefix conforming to WSDL.

   .. code-block:: java

      private String nsURI = "http://service.ebms.edi.cecid.hku.hk/";
      private String nsPrefix = "tns"; 
      private String URL receiverListWSURL = "http://localhost:8080/corvus/httpd/ebms/receiver_list";

#. Create a SOAP message factory and SOAP message object.

   .. code-block:: java

      SOAPMessage request = MessageFactory.newInstance().createMessage();

#. Populate the SOAP body by filling in the required parameters. For example:

   .. code-block:: xml

      <cpaId> ebmscpaid </cpaId>
      <service> http://localhost:8080/corvus/httpd/ebms/inbound <service>
      <action> action </action>
      <convId> convId </convId>
      <fromPartyId> fromPartyId </fromPartyId>
      <fromPartyType> fromPartyType </fromPartyType>
      <toPartyId> toPartyId </toPartyId>
      <toPartyType> toPartyType </toPartyType>
      <numOfMessages> 100 </numOfMessages>

   Sample WSDL request for the ebMS receiver list web service:

   .. code-block:: java

      SOAPBody soapBody = request.getSOAPBody();
      soapBody.addChildElement(createElement("cpaId", nsPrefix, nsURI, cpaId));
      soapBody.addChildElement(createElement("service", nsPrefix, nsURI, service));
      soapBody.addChildElement(createElement("action", nsPrefix, nsURI, action));
      soapBody.addChildElement(createElement("convId", nsPrefix, nsURI, conversationId));
      soapBody.addChildElement(createElement("fromPartyId", nsPrefix, nsURI, fromPartyId));
      soapBody.addChildElement(createElement("fromPartyType", nsPrefix, nsURI, fromPartyType));
      soapBody.addChildElement(createElement("toPartyId", nsPrefix, nsURI, toPartyId));
      soapBody.addChildElement(createElement("toPartyType", nsPrefix, nsURI, toPartyType));
      soapBody.addChildElement(createElement("numOfMessages", nsPrefix, nsURI, numOfMessages));
      
   The method :code:`createElement` creates a SOAP element with namespace prefix equal to :literal:`nsPrefix`, namespace URL equal to :literal:`nsURI` and textual value equal to the last arguments of the method.
   
   The implementation of :code:`createElement` is shown below:

   .. code-block:: java

      SOAPElement soapElement = SOAPFactory.newInstance().createElement(localName, nsPrefix, nsURI); 
      soapElement.addTextNode(value);
      return soapElement;

#. Save changes to the SOAP message.

   .. code-block:: java
      
      request.saveChange();

#. Send the SOAP request to Hermes 2 ebMS receiver list web service and get a SOAP response.

   .. code-block:: java
      
      SOAPMessage response = soapConn.call(request, receiverListWSURL);
      SOAPBody responseBody = response.getSOAPBody();

#. SOAP response:

   .. code-block:: xml

      <soap-body>
          <messageIds>
              <messageId> .. </messageId>
              <messageId> .. </messageId>
              <messageId> .. </messageId>
              <messageId> .. </messageId>
          </messageIds>
      </soap-body>

   Process the SOAP response and extract the identifiers of the requested ebMS messages to ``System.out`` if there is no SOAP fault.
   
   .. code-block:: java

      if (!responseBody.hasFault()){
          SOAPElement messageIdsElement = getFirstChild(responseBody, "messageIds", nsURI);
          Iterator messageIdElementIter = getChildren(messageIdsElement, "messageId", nsURI); 
      
          while(messageIdElementIter.hasNext()) {
              SOAPElement messageIdElement = (SOAPElement)messageIdElementIter.next();
              System.out.println(messageIdElement.getValue());
          }
      } else {
          throw new SOAPException(responseBody.getFault().getFaultString());
      }

   The method :code:`getFirstChild` gets the first element with the name :literal:`messageIds` and namespace URI equal to :literal:`nsURI`.
   It then extracts every :literal:`messageId` which each represent an available message awaiting further action.

Writing an ebMS 2.0 receiver web service client
-----------------------------------------------
We need to create a SOAP message with the identifier of the target message and send it to Hermes 2 as the web service request.

#. Define a namespace URI and prefix conforming to WSDL.

   .. code-block:: java

      private String nsURI = "http://service.ebms.edi.cecid.hku.hk/";
      private String nsPrefix = "tns";
      private URL receiverWSURL = "http://localhost:8080/corvus/httpd/ebms/receiver";

#. Create a SOAP message factory and SOAP message object.
   
   .. code-block:: java

      SOAPMessage request = MessageFactory.newInstance().createMessage();

#. Populate the SOAP body by filling in the required parameters.

   .. code-block:: xml
      
      <messageId> messageId </messageId>

   Sample WSDL request for the ebMS receiver web service:

   .. code-block:: java
      
      SOAPBody soapBody = request.getSOAPBody();
      soapBody.addChildElement(createElement("messageId", nsPrefix, nsURI, messageId));

   The method :code:`createElement` creates a SOAP element with namespace prefix equal to :literal:`nsPrefix`, namespace URL equal to :literal:`nsURI` and textual value equal to the last arguments of the method.
   
   The implementation of :code:`createElement` is shown below:
   
   .. code-block:: java
      
      SOAPElement soapElement = SOAPFactory.newInstance().createElement(localName, nsPrefix, nsURI); 
      soapElement.addTextNode(value);
      return soapElement;

#. Save changes to the SOAP message.

   .. code-block:: java

      request.saveChange();

#. Send the SOAP request to Hermes 2 ebMS receiver web service and get a SOAP response.

   .. code-block:: java
      
      SOAPMessage response = soapConn.call(request, receiverWSURL);
      SOAPBody responseBody = response.getSOAPBody();

#. SOAP response:
   
   .. code-block:: xml
      
      <soap-body>
          <hasMessage> .. </hasMessage>
      </soap-body>
            .
            .
      Attachment as a MIME part.

   Process the SOAP response and extract the payload from the received ebMS message if available.

   .. code-block:: java

      if (!responseBody.hasFault()){
          SOAPElement hasMessageElement = getFirstChild(responseBody, "hasMessage", nsURI);
          ArrayList payloadsList = new ArrayList();
          if (hasMessageElement != null){ 
              Iterator attachmentPartIter = response.getAttachments();
              while(attachmentPartIter.hasNext()) {
                  AttachmentPart attachmentPart = (AttachmentPart) attachmentPartIter.next();
                  InputStream ins = attachmentPart.getDataHandler().getInputStream();
                  // Do something I/O to extract the payload to physical file.
              }
          }
      } else {
          throw new SOAPException(responseBody.getFault().getFaultString());
      }

   The method :code:`getFirstChild` gets the first element with the name :literal:`hasMessage` and namespace URI equal to :literal:`nsURI`.
   The boolean value of :literal:`hasMessage` represents the existence of a payload in this message.

   The payload is extracted from the attachment part to the input stream and can be saved by I/O pipelining to a physical file or another business operation.

Writing an ebMS 2.0 status web service client
---------------------------------------------
We need to create a SOAP message with the identifier of the target message and send it to Hermes 2 as the web service request.

#. Define a namespace URI and prefix conforming to WSDL.
   
   .. code-block:: java
      
      private String nsURI = "http://service.ebms.edi.cecid.hku.hk/";
      private String nsPrefix = "tns";
      private URL statusQueryWSURL = "http://localhost:8080/corvus/httpd/ebms/status";

#. Create a SOAP message factory and SOAP message object.
   
   .. code-block:: java
      
      SOAPMessage request = MessageFactory.newInstance().createMessage();

#. Populate the SOAP body by filling in the required parameters.
   
   .. code-block:: xml
      
      <messageId> messageId </messageId>

   Sample WSDL request for the ebMS status web service:

   .. code-block:: java
      
      SOAPBody soapBody = request.getSOAPBody();
      soapBody.addChildElement(createElement("messageId", nsPrefix, nsURI, messageId));

   The method :code:`createElement` creates a SOAP element with namespace prefix equal to :literal:`nsPrefix`, namespace URL equal to :literal:`nsURI` and textual value equal to the last arguments of the method.
   
   The implementation of :code:`createElement` is shown below:

   .. code-block:: java

      SOAPElement soapElement = SOAPFactory.newInstance().createElement(localName, nsPrefix, nsURI); 
      soapElement.addTextNode(value);
      return soapElement;

#. Save changes to the SOAP message.
   
   .. code-block:: java

      request.saveChange();

#. Send the SOAP request to Hermes 2 ebMS status web service and get a SOAP response.

   .. code-block:: java

      SOAPMessage response = soapConn.call(request, statusQueryWSURL);
      SOAPBody responseBody = response.getSOAPBody();

#. SOAP response:
   
   .. code-block:: xml
      
      <soap-body>
          <MessageInfo>
              <status> The current status of message </status>
              <statusDescription> The current status description of message </statusDescription>
              <ackMessageId> The message id of acknowledgment / receipt if any </ackMessageId>
              <ackStatus> The status of acknowledgment / receipt if any </ackStatus>
              <ackStatusDescription> The status description of acknowledgment / receipt if any </ackStatusDescription> 
          </MessageInfo>
      </soap-body> 
   
   Process the SOAP response and extract the status information of the ebMS message if there is no SOAP fault.

   .. code-block:: java
      
      if (!responseBody.hasFault()){ 
          SOAPElement messageInfoElement = getFirstChild(responseBody, "messageInfo", nsURI);
          System.out.println("Message Status : " + getFirstChild(messageInfoElement, "status", nsURI);
          System.out.println("Message Status Desc : " + getFirstChild(messageInfoElement, "statusDescription", nsURI);
          System.out.println("Ack Message Identifiers : " + getFirstChild(messageInfoElement, "ackMessageId", nsURI);
          System.out.println("Ack Status : " + getFirstChild(messageInfoElement, "ackStatus", nsURI);
          System.out.println("Ack Status Desc : " + getFirstChild(messageInfoElement, "ackStatusDescription", nsURI); 
      } else {
          throw new SOAPException(responseBody.getFault().getFaultString());
      }

   The method :code:`getFirstChild` gets the first element with the name :literal:`messageInfo` and namespace URI equal to :literal:`nsURI`. It then retrieves the status value from that element.

Writing an ebMS 2.0 message history web service client
------------------------------------------------------
We need to create a SOAP message with 7 parameters and send it to Hermes 2 as the web service request.
The parameters are :literal:`messageId`, :literal:`messageBox`, :literal:`conversationId`, :literal:`cpaId`, :literal:`status`, :literal:`action` and :literal:`service`.

#. Define a namespace URI and prefix conforming to WSDL.

   .. code-block:: java
         
      private String nsURI = "http://service.ebms.edi.cecid.hku.hk/";
      private String nsPrefix = "tns";
      private URL msgHistoryWSURL = "http://localhost:8080/corvus/httpd/ebms/msg_history";

#. Create a SOAP message factory and SOAP message object.
   
   .. code-block:: java
      
      SOAPMessage request = MessageFactory.newInstance().createMessage();

#. Populate the SOAP body by filling in the required parameters.
   
   .. code-block:: xml
      
      <messageId> messageId </messageId>
      <messageBox> messageBox </messageBox>
      <conversationId> conversationId </conversationId>
      <cpaId> cpaId </cpaId>
      <service> service </service>
      <action> action </action>
      <status> status </status>

   Sample WSDL request for the ebMS message history web service:

   .. code-block:: java
      
      SOAPBody soapBody = request.getSOAPBody();
      soapBody.addChildElement(createElement("messageId", nsPrefix, nsURI, messageId));
      soapBody.addChildElement(createElement("messageBox", nsPrefix, nsURI, messageBox));
      soapBody.addChildElement(createElement("conversationId", nsPrefix, nsURI, conversationId));
      soapBody.addChildElement(createElement("cpaId", nsPrefix, nsURI, cpaId));
      soapBody.addChildElement(createElement("service", nsPrefix, nsURI, service));
      soapBody.addChildElement(createElement("fromPartyType", nsPrefix, nsURI, fromPartyType));
      soapBody.addChildElement(createElement("action", nsPrefix, nsURI, action));
      soapBody.addChildElement(createElement("status", nsPrefix, nsURI, status));

   The method :code:`createElement` creates a SOAP element with namespace prefix equal to :literal:`nsPrefix`, namespace URL equal to :literal:`nsURI` and textual value equal to the last arguments of the method.
   
   The implementation of :code:`createElement` is shown below:

   .. code-block:: java
      
      SOAPElement soapElement = SOAPFactory.newInstance().createElement(localName, nsPrefix, nsURI);
      soapElement.addTextNode(value);
      return soapElement;

#. Save changes to the SOAP message.

   .. code-block:: java
      
      request.saveChange();

#. Send the SOAP request to Hermes 2 ebMS message history service and get a SOAP response.
   
   .. code-block:: java

      SOAPMessage response = soapConn.call(request, msgHistoryWSURL);
      SOAPBody responseBody = response.getSOAPBody(); 

#. SOAP response:
   
   .. code-block:: xml
      
      <soap-body> 
          <messageList>
              <messageElement>
                  <messageId> Message ID of this message </messageId>
                  <messageBox> Message Box containing this message </messageBox>
              </messageElement>
              <messageElement>
                  <messageId> Message ID of this message </messageId>
                  <messageBox> Message Box containing this message </messageBox>
              </messageElement> 
              <messageElement> .. </messageElement> 
              <messageElement> .. </messageElement> 
          </messageList> 
      </soap-body>

   Process the SOAP response and extract the ebMS message information if there is no SOAP fault.

   .. code-block:: java

      if (!responseBody.hasFault()){ 
          SOAPElement msgList = SOAPUtilities.getElement(responseBody, "messageList", nsURI, 0); 

          Iterator msgIterator = msgList.getChildElements(); 
          while(msgIterator.hasNext()){ 

              List elementList = new ArrayList(); 

              SOAPElement messageElement = (SOAPElement)msgIterator.next(); 

              Iterator elements = messageElement.getChildElements(); 

              // MessageId 
              SOAPElement msgId = (SOAPElement)(elements.next()); 

              // MessageBox 
              SOAPElement msgBox = (SOAPElement)(elements.next()); 

              System.out.println("Message ID: " + (String)msgId.get(0) + "\t" + "Message Box: " + msgBox.get(0)); 
          } 
      }
   
   The method :code:`getElement` gets the element with the name :literal:`messageList` and namespace URI equal to :literal:`nsURI`. Then, a list of :literal:`messageElement` values will be extracted from :literal:`messageList`.
   Each :code:`messageElement` contains the values of :literal:`messageId` and :literal:`messageBox`.

Writing an AS2 sender web service client
----------------------------------------
We need to create a SOAP message with 3 parameters and send it to Hermes 2 as the web service request. The parameters are :literal:`as2_from`, :literal:`as2_to` and :literal:`type`.

#. Define a namespace URI and prefix conforming to WSDL and define the AS2 sender web service for Hermes 2.
   
   .. code-block:: java
      
      private String nsURI = "http://service.as2.edi.cecid.hku.hk/"; 
      private String nsPrefix = "tns"; 
      private URL senderWSURL = "http://localhost:8080/corvus/httpd/as2/sender";

#. Create a SOAP message factor and SOAP message object.
   
   .. code-block:: java
      
      SOAPMessage request = MessageFactory.newInstance().createMessage();

#. Populate the SOAP body by filling in the required parameters.
   
   .. code-block:: xml
      
      <as2_from> as2from </as2_from>
      <as2_to> as2to <as2_to>
      <type> type </type>

   Sample WSDL request for the AS2 sender web service:

   .. code-block:: java
      
      SOAPBody soapBody = request.getSOAPBody(); 
      soapBody.addChildElement(createElement("as2_from", nsPrefix, nsURI, this.as2From)); 
      soapBody.addChildElement(createElement("as2_to" , nsPrefix, nsURI, this.as2To)); 
      soapBody.addChildElement(createElement("type" , nsPrefix, nsURI, this.type));

   The method :code:`createElement` creates a SOAP element with namespace prefix equal to :literal:`nsPrefix`, namespace URL equal to :literal:`nsURI` and textual value equal to the last arguments of the method.
   
   The implementation of :code:`createElement` is shown below:

   .. code-block:: java
      
      SOAPElement soapElement = SOAPFactory.newInstance().createElement(localName, nsPrefix, nsURI); 
      soapElement.addTextNode(value); 
      return soapElement;

#. Attach a payload if necessary. The example here uses a purchase order XML as the payload of the AS2 message, so the associated content type is :code:`application/xml`.
   
   **NOTE:** Only ONE payload is allowed in a SOAP request for the AS2 sender web service.

   .. code-block:: java
      
      AttachmentPart attachmentPart = request.createAttachmentPart(); 
      FileDataSource fileDS = new FileDataSource(new File("purchase_order.xml")); 
      attachmentPart.setDataHandler(new DataHandler(fileDS)); 
      attachmentPart.setContentType("application/xml"); 
      request.addAttachmentPart(attachmentPart);

#. Save changes to the SOAP message.

   .. code-block:: java
      
      request.saveChange();

#. Send the SOAP request to Hermes 2 AS2 sender web service and get a SOAP response.
   
   .. code-block:: java
      
      SOAPMessage response = soapConn.call(request, senderWSURL); 
      SOAPBody responseBody = response.getSOAPBody();

#. Process the SOAP response and extract the identifier of the AS2 message to ``System.out`` if there is no SOAP fault.

   .. code-block:: java
      
      if (!responseBody.hasFault()){ 
          SOAPElement messageIdElement = getFirstChild(responseBody, "message_id", nsURI); 
          System.out.println(messageIdElement == null ? null : messageIdElement.getValue()); 
      } else { 
          throw new SOAPException(responseBody.getFault().getFaultString()); 
      }
   
   The method :code:`getFirstChild` gets the first element with the name :literal:`message_id` and namespace URI equal to :literal:`nsURI`.

   The SOAP request is now transformed into an AS2 message stored in the file system.
   Hermes 2 will deliver the AS2 message to the partner specified in the SOAP request parameters (:literal:`AS2From` and :literal:`AS2To` identify the partnership).

Writing an AS2 receiver list web service client
-----------------------------------------------
We need to create a SOAP message with 3 parameters and send it to Hermes 2 as the web service request. The parameters are :literal:`as2From`, :literal:`as2To` and :literal:`numOfMessages`.

#. Define a namespace URi and prefix conforming to WSDL and define the AS2 receiver list web service for Hermes 2.

   .. code-block:: java
      
      private String nsURI = "http://service.as2.edi.cecid.hku.hk/";
      private String nsPrefix = "tns";
      private URL receiverListWSURL = "http://localhost:8080/corvus/httpd/as2/receiver_list";

#. Create a SOAP message factory and SOAP message object.
   
   .. code-block:: java
      
      SOAPMessage request = MessageFactory.newInstance().createMessage();

#. Populate the SOAP body by filling in the required parameters.

   .. code-block:: xml
      
      <as2_from> as2from </as2_from>
      <as2_to> as2to <as2_to>
      <numOfMessages> 100 </numOfMessages>
   
   Sample WSDL request for the AS2 receiver list web service:

   .. code-block:: java
      
      SOAPBody soapBody = request.getSOAPBody();
      soapBody.addChildElement(createElement("as2From" , nsPrefix, nsURI, this.as2From));
      soapBody.addChildElement(createElement("as2To" , nsPrefix, nsURI, this.as2To));
      soapBody.addChildElement(createElement("numOfMessages", nsPrefix, nsURI, this.numOfMessages + ""));

   The method :code:`createElement` creates a SOAP element with namespace prefix equal to :literal:`nsPrefix`, namespace URL equal to :literal:`nsURI` and textual value equal to the last arguments of the method.
   
   The implementation of :code:`createElement` is shown below: 
   
   .. code-block:: java
      
      SOAPElement soapElement = SOAPFactory.newInstance().createElement(localName, nsPrefix, nsURI); 
      soapElement.addTextNode(value);
      return soapElement;

#. Save changes to the SOAP message.

   .. code-block:: java
      
      request.saveChange();

#. Send the SOAP request to Hermes 2 AS2 receiver list web service and get a SOAP response.

   .. code-block:: java
      
      SOAPMessage response = soapConn.call(request, senderWSURL);
      SOAPBody responseBody = response.getSOAPBody();

#. SOAP response:
   
   .. code-block:: xml
      
      <soap-body>
          <messageIds>
              <messageId> .. </messageId>
              <messageId> .. </messageId>
              <messageId> .. </messageId>
              <messageId> .. </messageId>
          </messageIds>
      </soap-body> 
   
   Process the SOAP response and extract identifiers of the requested AS2 messages to ``System.out`` if there is no SOAP fault.
   
   .. code-block:: java
      
      if (!responseBody.hasFault()){
          SOAPElement messageIdsElement = getFirstChild(responseBody, "messageIds", nsURI);
          Iterator messageIdElementIter = getChildren(messageIdsElement, "messageId", nsURI); 

          while(messageIdElementIter.hasNext()) {
              SOAPElement messageIdElement = (SOAPElement)messageIdElementIter.next();
              System.out.println(messageIdElement.getValue());
          }
      } else {
          throw new SOAPException(responseBody.getFault().getFaultString());
      }
   
   The method :code:`getFirstChild` gets the first element with the name :literal:`messageIds` and namespace URI equal to :literal:`nsURI`.
   All children with the name :literal:`messageId` and namespace URI equal to :literal:`nsURI` are then extracted.

Writing an AS2 receiver web service client
------------------------------------------
We need to create a SOAP message with the identifier of the target message and send it to Hermes 2 as the web service request.

#. Define a namespace URI and prefix conforming to WSDL.

   .. code-block:: java

      private String nsURI = "http://service.as2.edi.cecid.hku.hk/";
      private String nsPrefix = "tns";
      private URL receiverWSURL = "http://localhost:8080/corvus/httpd/as2/receiver";

#. Create a SOAP message factory and SOAP message object.
   
   .. code-block:: java

      SOAPMessage request = MessageFactory.newInstance().createMessage();

#. Populate the SOAP body by filling in the required parameters.

   .. code-block:: xml
      
      <messageId> messageId </messageId>

   Sample WSDL request for the AS2 receiver web service:

   .. code-block:: java
      
      SOAPBody soapBody = request.getSOAPBody();
      soapBody.addChildElement(createElement("messageId", nsPrefix, nsURI, messageId));

   The method :code:`createElement` creates a SOAP element with namespace prefix equal to :literal:`nsPrefix`, namespace URL equal to :literal:`nsURI` and textual value equal to the last arguments of the method.
   
   The implementation of :code:`createElement` is shown below:
   
   .. code-block:: java
      
      SOAPElement soapElement = SOAPFactory.newInstance().createElement(localName, nsPrefix, nsURI); 
      soapElement.addTextNode(value);
      return soapElement;

#. Save changes to the SOAP message.

   .. code-block:: java

      request.saveChange();

#. Send the SOAP request to Hermes 2 AS2 receiver web service and get a SOAP response.

   .. code-block:: java
      
      SOAPMessage response = soapConn.call(request, receiverWSURL);
      SOAPBody responseBody = response.getSOAPBody();

#. SOAP response:
   
   .. code-block:: xml
      
      <soap-body>
          <hasMessage> .. </hasMessage>
      </soap-body>
            .
            .
      Attachment as a MIME part.

   Process the SOAP response and extract the payload from the received AS2 message if available.

   .. code-block:: java

      if (!responseBody.hasFault()){
          SOAPElement hasMessageElement = getFirstChild(responseBody, "hasMessage", nsURI);
          ArrayList payloadsList = new ArrayList();
          if (hasMessageElement != null){ 
              Iterator attachmentPartIter = response.getAttachments();
              while(attachmentPartIter.hasNext()) {
                  AttachmentPart attachmentPart = (AttachmentPart) attachmentPartIter.next();
                  InputStream ins = attachmentPart.getDataHandler().getInputStream();
                  // Do something I/O to extract the payload to physical file.
              }
          }
      } else {
          throw new SOAPException(responseBody.getFault().getFaultString());
      }

   The method :code:`getFirstChild` gets the first element with the name :literal:`hasMessage` and namespace URI equal to :literal:`nsURI`.
   The boolean value of :code:`hasMessage` represents the existence of a payload in this message.

   The payload is extracted from the attachment part to the input stream and can be saved by I/O pipelining to a physical file or another business operation.

Writing an AS2 status web service client
----------------------------------------
We need to create a SOAP message with the identifier of the target message and send it to Hermes 2 as the web service request.

#. Define a namespace URI and prefix conforming to WSDL.
   
   .. code-block:: java
      
      private String nsURI = "http://service.as2.edi.cecid.hku.hk/";
      private String nsPrefix = "tns";
      private URL statusQueryWSURL = "http://localhost:8080/corvus/httpd/as2/status";

#. Create a SOAP message factory and SOAP message object.
   
   .. code-block:: java
      
      SOAPMessage request = MessageFactory.newInstance().createMessage();

#. Populate the SOAP body by filling in the required parameters.
   
   .. code-block:: xml
      
      <messageId> messageId </messageId>

   Sample WSDL request for the AS2 status web service:

   .. code-block:: java
      
      SOAPBody soapBody = request.getSOAPBody();
      soapBody.addChildElement(createElement("messageId", nsPrefix, nsURI, messageId));

   The method :code:`createElement` creates a SOAP element with namespace prefix equal to :literal:`nsPrefix`, namespace URL equal to :literal:`nsURI` and textual value equal to the last arguments of the method.
   
   The implementation of :code:`createElement` is shown below:

   .. code-block:: java
      
      SOAPElement soapElement = SOAPFactory.newInstance().createElement(localName, nsPrefix, nsURI); 
      soapElement.addTextNode(value);
      return soapElement;

#. Save changes to the SOAP message.
   
   .. code-block:: java
      
      request.saveChange();

#. Send the SOAP request to Hermes 2 AS2 status web service and get a SOAP response.
   
   .. code-block:: java

      SOAPMessage response = soapConn.call(request, statusQueryWSURL);
      SOAPBody responseBody = response.getSOAPBody();

#. SOAP response:
   
   .. code-block:: xml
      
      <soap-body>
          <MessageInfo>
              <status> The current status of message </status>
              <statusDescription> The current status description of message </statusDescription>
              <mdnMessageId> The message id of acknowledgment / receipt if any </mdnMessageId>
              <mdnStatus> The status of acknowledgment / receipt if any </mdnStatus>
              <mdnStatusDescription> The status description of acknowledgment / receipt if any </mdnStatusDescription> 
          </MessageInfo> 
      </soap-body>
   
   Process the SOAP response and extract the status information of the AS2 message if there is no SOAP fault.

   .. code-block:: java
      
      if (!responseBody.hasFault()){
          SOAPElement messageInfoElement = getFirstChild(responseBody, "MessageInfo", nsURI);
          System.out.println("Message Status : " + getFirstChild(messageInfoElement, "status", nsURI);
          System.out.println("Message Status Desc : " + getFirstChild(messageInfoElement, "statusDescription", nsURI);
          System.out.println("Ack Message Identifiers : " + getFirstChild(messageInfoElement, "mdnMessageId", nsURI);
          System.out.println("Ack Status : " + getFirstChild(messageInfoElement, "mdnStatus", nsURI);
          System.out.println("Ack Status Desc : " + getFirstChild(messageInfoElement, "mdnStatusDescription", nsURI); 
      } else { 
          throw new SOAPException(responseBody.getFault().getFaultString());
      }

   The method :code:`getFirstChild` gets the first element with the name :literal:`MessageInfo` and namespace URI equal to :literal:`nsURI`.

Writing an AS2 message history web service client
-------------------------------------------------
We need to create a SOAP message with 5 parameters and send it to Hermes 2 as the web service request.
The parameters are :literal:`messageId`, :literal:`messageBox`, :literal:`as2From`, :literal:`as2To`, and :literal:`status`.

#. Define the namespace URI and prefix conforming to WSDL.
   
   .. code-block:: java
      
      private String nsURI = "http://service.as2.edi.cecid.hku.hk/";
      private String nsPrefix = "tns";
      private URL msgHistoryWSURL = "http://localhost:8080/corvus/httpd/as2/msg_history";

#. Create a SOAP message factory and SOAP message object.

   .. code-block:: java
      
      SOAPMessage request = MessageFactory.newInstance().createMessage();

#. Populate the SOAP body by filling in the required parameters.
   
   .. code-block:: xml
      
      <messageId> messageId </messageId>
      <messageBox> messageBox </messageBox>
      <as2From> as2From </as2From>
      <as2To> as2To </as2To>
      <status> status </status>

   Sample WSDL request for the message history web service:

   .. code-block:: java
      
      SOAPBody soapBody = request.getSOAPBody();
      soapBody.addChildElement(createElement("messageId", nsPrefix, nsURI, messageId));
      soapBody.addChildElement(createElement("messageBox", nsPrefix, nsURI, messageBox));
      soapBody.addChildElement(createElement("as2From", nsPrefix, nsURI, cpaId));
      soapBody.addChildElement(createElement("as2To", nsPrefix, nsURI, service));
      soapBody.addChildElement(createElement("status", nsPrefix, nsURI, status));

   The method :code:`createElement` creates a SOAP element with namespace prefix equal to :literal:`nsPrefix`, namespace URL equal to :literal:`nsURI` and textual value equal to the last arguments of the method.
   
   The implementation of :code:`createElement` is shown below:

   .. code-block:: java
      
      SOAPElement soapElement = SOAPFactory.newInstance().createElement(localName, nsPrefix, nsURI); 
      soapElement.addTextNode(value);
      return soapElement;

#. Save changes to the SOAP message. 
   
   .. code-block:: java
      
      request.saveChange();

#. Send the SOAP request to Hermes 2 AS2 message history web service and get a SOAP response.
   
   .. code-block:: java
      
      SOAPMessage response = soapConn.call(request, receiverListWSURL);
      SOAPBody responseBody = response.getSOAPBody();

#. SOAP response:
   
   .. code-block:: xml
      
      <soap-body>
          <messageList>
              <messageElement>
                  <messageId> Message ID of this message </messageId>
                  <messageBox> Message Box containing this message </messageBox>
              </messageElement>
              <messageElement>
                  <messageId> Message ID of this message </messageId>
                  <messageBox> Message Box containing this message </messageBox>
              </messageElement> 
              <messageElement> .. </messageElement> 
              <messageElement> .. </messageElement> 
          </messageList> 
      </soap-body>
   
   Process the SOAP response and extract the AS2 message information if there is no SOAP fault.
   
   .. code-block:: java
      
      if (!responseBody.hasFault()){
          SOAPElement msgList = SOAPUtilities.getElement(responseBody, "messageList", nsURI, 0); 

          Iterator msgIterator = msgList.getChildElements();
          while(msgIterator.hasNext()){ 

              List elementList = new ArrayList(); 

              SOAPElement messageElement = (SOAPElement)msgIterator.next(); 

              Iterator elements = messageElement.getChildElements(); 

              // MessageId
              SOAPElement msgId = (SOAPElement)(elements.next()); 

              // MessageBox
              SOAPElement msgBox = (SOAPElement)(elements.next()); 

              System.out.println("Message ID: " + (String)msgId.get(0) + "\t" + "Message Box: " + msgBox.get(0));
          }
      }

   The method :code:`getElement` gets the element with the name :literal:`messageList` and namespace URI equal to :literal:`nsURI`. The :code:`messageElement` values will then be extracted from :code:`messageList`.
   Each :code:`messageElement` contains the values of :literal:`messageId` and :literal:`messageBox`.

Reference articles
------------------
* :doc:`first_step`
* :doc:`web_service_communication`
* :doc:`ebms_partnership`
* :doc:`as2_partnership`

Reference program source
------------------------
* :download:`Hermes 2 loopback test <_static/hermes2_loopback.zip>`
