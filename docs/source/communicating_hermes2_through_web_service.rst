Communicating Hermes 2 through WS
=================================

Introduction
------------
Hermes 2 has implemented SOAP messaging framework to communicate with external applications instead of using the JAVA-based callback registry mechanisms from Hermes 1. The main advantages of using SOAP web services are reducing coupling between external applications and Hermes 2, and allowing external applications to integrate Hermes 2 seamlessly using any programming language that supports SOAP and SOAP Messages with Attachments. 

This article is purposed to assist developers who want to communicate with Hermes 2 using SOAP web services by writing a web service call client. 



It assumes you have successfully installed Hermes 2 and know what a partnership is. Please refer to `Hermes 2 Installation Guide <http://community.cecid.hku.hk/index.php/product/download/download_h2o/#>`_ and `The First Step <http://community.cecid.hku.hk/index.php/product/article/the_first_step_you_hermes/>`_ if you don't. 

.. image:: /_static/images/web_service/h2o-ws-pl-free.png

Overview
--------

Here is a brief summary about the communication port architecture between Hermes 2 and external applications. First of all, the core of Hermes 2 is attached to any J2EE compliant web server as a kind of servlet. The core itself does not provide any SOAP web services or HTTP listeners. It does not even have any functionality related to messaging. All features in Hermes 2 are derived from the core by SPA (simple plugin architecture).

One of the core SPAs, called Main Plugin (shown below in the core SPA layer), provides an HTTP context listener that accepts HTTP requests at the specified context path (extension point) for external invocation. The protocol-specific SPA ebMS and AS2 plugins (shown below at the external SPA layer) make use of this listener to provide all SOAP web services.

By default, the ebMS 2.0 and AS2 plugins each have 5 registered web services in Hermes 2:

1. `ebMS 2.0 Sender Web Service`_
#. `ebMS 2.0 Receiver List Web Service`_
#. `ebMS 2.0 Receiver Web Service`_
#. `ebMS 2.0 Status Web Service`_
#. `ebMS 2.0 Message History Web Service`_
#. `AS2 Sender Web Service`_
#. `AS2 Receiver List Web Service`_
#. `AS2 Receiver Web Service`_
#. `AS2 Status Web Service`_
#. `AS2 Message History Web Service`_

.. image:: /_static/images/web_service/ws-archtecture.png


ebMS 2.0 Sender Web Service
---------------------------

Service Endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/sender`

ebMS 2.0 Sender Web Service is the web service interface for external sending parties to request Hermes 2 to send an ebMS 2.0 message to another Hermes 2 or any other ebMS 2.0 compliant messaging gateway. The service returns a message identifier to the sending party for reference. This is the main channel for external applications to deliver ebMS messages using Hermes 2. 

.. image:: /_static/images/web_service/h2o-ws-sender-ebms.png

-- SOAP Request Message --

Instead of requiring sender to compose the entire ebMS message or acquire ebMS knowledge, sender just needed to request Hermes 2 to do so with key identities including CPA-ID, Service, Action. These 3 key parameter identify the sender's partnership in Hermes 2 that will be used to configure the ebMS message.

The sender web service requires elements with namespace URI **http://service.ebms.edi.cecid.hku.hk/** and namespace prefix **tns**. The sample SOAP request for sender web service is shown below.

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:cpaId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <CPA-id> </tns:cpaId>
   <tns:service xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <Service> </tns:service>
   <tns:action xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <Action> </tns:action>
   <tns:convId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <Conversation Id> </tns:convId>
   <tns:fromPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <From Party ID> </tns:fromPartyId>
   <tns:fromPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <From Party Type> </tns:fromPartyType>
   <tns:toPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <To Party ID> </tns:toPartyId>
   <tns:toPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <To Party Type> </tns:toPartyType>
   <tns:refToMessageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <Reference Message Id> </refToMessageId>
   <tns:serviceType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <Service Type> </tns:serviceType>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   .
   .
   .
   Attached Payload

The meaning of the elements under SOAP Body in the above request message is as follows:

+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| Element                  | Mandatory | Description                                                                                  |
+==========================+===========+==============================================================================================+
| :code:`<cpaId>`,         | Yes       | They are the CPA Id, Service and Action elements in the ebMS messages sent by Hermes.        |
| :code:`<service>`        |           |                                                                                              |
| and :code:`<action>`     |           | These three fields are used to identify the partnership used to send / receive the ebMS      |
|                          |           | messages at sender / receiver party respectively.                                            |
|                          |           |                                                                                              |
|                          |           | **These are mandatory values to identify a registered partnership in Hermes 2.**             |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| :code:`<convId>`         | Yes       | It corresponds to the conversation id element in the ebMS messages sent by Hermes.           |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| :code:`<fromPartyId>`    | Yes       | It identifies the Party that originated the message (the sender). [ebMS v2_0 3.1.1]          |
|                          |           |                                                                                              |
|                          |           | It corresponds to the :literal:`PartyId` element in :literal:`From` element of the ebMS      |
|                          |           | messages sent by Hermes.                                                                     |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| :code:`<fromPartyType>`  | Yes       | It identifies the domain of the fromPartyId.                                                 |
|                          |           |                                                                                              |
|                          |           | It corresponds to the :literal:`type` attribute of :literal:`PartyId` in the :literal:`From` |
|                          |           | element of the ebMS messages sent by Hermes.                                                 |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| :code:`<toPartyId>`      | Yes       | It identifies the Party that it is the intended recipient of the message (the receiver).     |
|                          |           |                                                                                              |
|                          |           | [ebMS v2_0 3.1.1]                                                                            |
|                          |           |                                                                                              |
|                          |           | It corresponds to the :literal:`PartyId` element in :literal:`To` element of the ebMS        |
|                          |           | messages sent by Hermes.                                                                     |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| :code:`<toPartyType>`    | Yes       | It identifies the domain of the ToPartyId.                                                   |
|                          |           |                                                                                              |
|                          |           | It corresponds to the :literal:`type` attribute of :literal:`PartyId` in the :literal:`From` |
|                          |           | element of the ebMS messages sent by Hermes.                                                 |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| :code:`<refToMessageId>` | No        | It corresponds to the RefToMessageId of the ebMS messages sent by Hermes.                    |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| :code:`<serviceType>`    | No        | A type identifier for the ebXML service defined in partnership.                              |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+

-- SOAP Response Message --

The element inside SOAP Body is using namespace URI http://service.ebms.edi.cecid.hku.hk/.

The sample SOAP response for sender web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <message_id xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="xsd:string" 
               xmlns="http://service.ebms.edi.cecid.hku.hk/" 
               xmlns:xsd="http://www.w3.org/2001/XMLSchema"> <Newly created message id>
   </message_id>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

As with the SOAP request message, the :code:`<message_id>` element is the :literal:`message identifier` assigned by the Hermes 2 of the sending party. The sending application can use it for later reference and status tracking through the Status Web Service. 

ebMS 2.0 Receiver List Web Service
----------------------------------

Service Endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/receiver_list`

The Receiver List Service is used by the application of the receiving party to retrieve message identifiers of received and processed ebMS messages which have not been downloaded by the application. These message identifiers will be used to retrieve message payloads with the Receiver Service.

-- SOAP Request Message --

The Receiver List Web Service requires elements with namespace URI http://service.ebms.edi.cecid.hku.hk/ and namespace prefix tns.

A sample SOAP request for the Receiver List Web Service is shown below: 

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:cpaId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <CPA-id> </tns:cpaId>
   <tns:service xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <Service> </tns:service>
   <tns:action xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <Action> </tns:action>
   <tns:convId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <Conversation Id> </tns:convId>
   <tns:fromPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <From Party ID> </tns:fromPartyId>
   <tns:fromPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <From Party Type> </tns:fromPartyType>
   <tns:toPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <To Party ID> </tns:toPartyId>
   <tns:toPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <To Party Type> </tns:toPartyType>
   <tns:numOfMessages xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <Number of messages> </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

The meanings of the elements in the SOAP Body are as follows:

+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| Element                 | Mandatory | Description                                                                                       |
+=========================+===========+===================================================================================================+
| :code:`<cpaId>`,        | Yes       | The CPA Id, Service and Action elements in ebMS messages sent                                     |
| :code:`<service>`       |           | by Hermes. These three fields are used to identify the partnership used to send the ebMS messages.|
| and :code:`<action>`    |           |                                                                                                   |
|                         |           | **These are required to query the list of available messages**.                                   |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| :code:`<convId>`        | No        | Only the message identifiers of messages with a matching Conversation Id value will be retrieved. |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| :code:`<fromPartyId>`   | No        | Only the message identifiers of messages with a matching From Party Id value will be retrieved.   |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| :code:`<fromPartyType>` | No        | Only the message identifiers of messages with a matching From Party Type value will be retrieved. |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| :code:`<toPartyId>`     | No        | Only the message identifiers of messages with a matching To Party Id value will be retrieved.     |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| :code:`<toPartyType>`   | No        | Only the message identifiers of messages with a matching To Party Type value will be retrieved.   |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| :code:`<numOfMessages>` | No        | The maximum number of message identifiers retrieved by this request.                              |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+


-- SOAP Response Message --

As with the SOAP request message, the element inside SOAP Body is using namespace URI http://service.ebms.edi.cecid.hku.hk/.

A sample SOAP response for the Receiver List Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <messageIds xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="MessageIDs" xmlns="http://service.ebms.edi.cecid.hku.hk/" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
   <messageId ns0:type="xsd:string"> <downloadable message id> </messageId>
   <messageId ns0:type="xsd:string"> <downloadable message id> </messageId>

   </messageIds>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

Each element in the SOAP Body represents a message identifier of an ebMS message received by Hermes 2.

Note that a message is considered downloaded only when the message body has been downloaded by the Receiver Web Service. If your application never calls the Receiver Web Service to download the messages, the same set of message identifiers will always be retrieved.


ebMS 2.0 Receiver Web Service
-----------------------------

Service Endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/receiver`

The Receiver Web Service is for the application of the receiving party to retrieve the message payloads of received ebMS messages. After the message payloads have been downloaded, the message will be marked as received by the application, and its message identifier will no longer be retrieved by the Receiver List Web Service.

.. image:: /_static/images/web_service/h2o-ws-recv.png

**-- SOAP Request Message --**

The Receiver Web Service requires only one element with namespace URI **http://service.ebms.edi.cecid.hku.hk/** and namespace prefix **tns**.

A sample SOAP request for the Receiver Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <messageId> <The message id you want to download> </tns:messageId>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>


The :code:`<messageId>` element contains the message identifiers you can obtain from the ebMS Receiver List Web Service.


-- SOAP Response Message --

The element inside the SOAP body is using namespace URI http://service.ebms.edi.cecid.hku.hk/.

A sample SOAP response for the Receiver Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <hasMessage xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="xsd:string" xmlns="http://service.ebms.edi.cecid.hku.hk/" xmlns:xsd="http://www.w3.org/2001/XMLSchema"> true if payload in message </hasMessage> </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

   .
   .
   .
   Attached Payload


If a payload is associated with the message identifier, the :code:`<hasMessage>` element will have the value true.
If the received ebMS message has payloads, the response message will have one or more SOAP attachments. Each SOAP attachment has a content type, which is set by the sending application. 



ebMS 2.0 Status Web Service
---------------------------

Service Endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/status`

The Status Web Service is for the application of the sending or receiving party to retrieve the status of a sent or received ebMS message.

The message status is a two-character code indicating the progress of an ebMS message. The Status Web Service provides a tracking service to monitor ebMS messages requested from Hermes 2.

**-- SOAP Request Message --**

The Status Web Service requires only one element with namespace URI http://service.ebms.edi.cecid.hku.hk/ and namespace prefix **tns**.

A sample SOAP request for the Status Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <messageId> <The message id you want to download> </tns:messageId>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>


The :code:`<messageId>` element contains the message identifiers you can obtain from the ebMS Sender Web Service response or the ebMS Receiver List Web Service.

**-- SOAP Response Message --**

The element inside the SOAP Body is using namespace URI http://service.ebms.edi.cecid.hku.hk/.

A sample SOAP response for the Status Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <messageInfo xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="MessageInfo" xmlns="http://service.ebms.edi.cecid.hku.hk/"
   xmlns:xsd="http://www.w3.org/2001/XMLSchema">
   <status ns0:type="xsd:string"> <status> </status>
   <statusDescription ns0:type="xsd:string"> <statusDescription> </statusDescription>
   <ackMessageId ns0:type="xsd:string"> <ackMessageId> </ackMessageId>
   <ackStatus ns0:type="xsd:string"> <ackStatus> </ackStatus>
   <ackStatusDescription ns0:type="xsd:string"> <ackStatusDescription> </ackStatusDescription>
   </messageInfo>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

The meanings of the elements in the SOAP Body in the above response message are as follows:

+-----------------------------------+--------------------------------------------------------------------+
| Element                           | Description                                                        |
+===================================+====================================================================+
| :code:`<status>`                  | The current status of the ebMS message.                            |
+-----------------------------------+--------------------------------------------------------------------+
| :code:`<statusDescription>`       | A text description of the current status.                          |
+-----------------------------------+--------------------------------------------------------------------+
| :code:`<ackMessageId>`            | The message identifiers of the associated acknowledgment (if any). |
+-----------------------------------+--------------------------------------------------------------------+
| :code:`<ackStatus>`               | The current status of the associated acknowledgment (if any).      |
+-----------------------------------+--------------------------------------------------------------------+
| :code:`<ackStatusDescription>`    | A text description of the associated acknowledgment (if any).      |
+-----------------------------------+--------------------------------------------------------------------+


ebMS 2.0 Message History Web Service
------------------------------------

Service Endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/msg_history`

The Message History Web Service is for the application of the sending or receiving party to query messages according to specific parameters.

.. image:: /_static/images/web_service/MessageHistory.png

**-- SOAP Request Message --**

A sample SOAP request for the Message History Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageBox xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"><Message Box></tns:messageBox>
   <tns:status xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"><Message Status></tns:status>
   <tns:messageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"><Message Id></tns:messageId>
   <tns:conversationId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"><Conversation Id></tns:conversationId>
   <tns:cpaId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"><CPA Id></tns:cpaId>
   <tns:service xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"><Defined Service with trading party></tns:service>
   <tns:action xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"><Action></tns:action>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

In the above example, the receiver list web service requires only one elements with namespace URI http://service.ebms.edi.cecid.hku.hk/ and namespace prefix **tns**.

**-- SOAP Response Message --**

The element :code:`<messageList>` inside the SOAP Body is using namespace URI http://service.ebms.edi.cecid.hku.hk/.

A sample SOAP response for the Message History Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <messageList xmlns="http://service.ebms.edi.cecid.hku.hk/" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="MessageList">
   <messageElement ns0:type="MessageElement">
   <messageId ns0:type="xsd:string"> MessageID of the Message </messageId>
   <messageBox ns0:type="xsd:string">Message Box containing this message </messageBox>
   </messageElement>
   <messageElement ns0:type="MessageElement">
   <messageId ns0:type="xsd:string"> MessageID of the Message </messageId>
   <messageBox ns0:type="xsd:string"> Message Box containing this message </messageBox>
   </messageElement>
   <messageElement ns0:type="MessageElement"> . . . </messageElement>
   <messageElement ns0:type="MessageElement"> . . . </messageElement>
   </messageList>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>


The meanings of the elements in the SOAP Body in the above response message are as follows:

+--------------------------+-----------------------------------------------------------------------------------+
| Element                  | Description                                                                       |
+==========================+===================================================================================+
| :code:`<messageList>`    | A list of return message elements (if any).                                       |
+--------------------------+-----------------------------------------------------------------------------------+
| :code:`<messageElement>` | A complex element containing messageId and messageBox values of a return message. |
+--------------------------+-----------------------------------------------------------------------------------+
| :code:`<messageId>`      | The message identifiers of a return message.                                      |
+--------------------------+-----------------------------------------------------------------------------------+
| :code:`<messageBox>`     | The message box of a return message.                                              |
+--------------------------+-----------------------------------------------------------------------------------+


AS2 Sender Web Service
----------------------

Service Endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/sender`

The Sender Web Service is for the application of the sending party to request Hermes 2 to send an AS2 message to another Hermes 2 or any other compatible messaging gateway. The service returns a message identifier to the application for reference.

.. image:: /_static/images/web_service/h2o-ws-sender-as2.png

**-- SOAP Request Message --**

The Sender Web Service requires elements with namespace URI http://service.as2.edi.cecid.hku.hk/ and namespace prefix tns.

The sample SOAP request for sender web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:as2_from xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <as2_from> </tns:as2_from>
   <tns:as2_to xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <as2_to> </tns:as2_to>
   <tns:type xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <type> </tns:type>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

   .
   .
   .
   Attached Payload

The meanings of the elements in the SOAP Body in the above request message are as follows:

+----------------------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
| Element              | Mandatory | Description                                                                                                                                               |
+======================+===========+===========================================================================================================================================================+
| :code:`<as2_from>`   | Yes       | The values of the From and To fields in AS2 messages sent through the                                                                                     |
| and :code:`<as2_to>` |           | partnership by Hermes 2. These fields are used to identify the sending partnership.                                                                       |
|                      |           |                                                                                                                                                           |
|                      |           | **These are required to identify the message destination.**                                                                                               |
+----------------------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`<type>`       | Yes       | A three-character code indicating the content type of the sent payload. The available codes are:                                                          |
|                      |           |                                                                                                                                                           |
|                      |           |  * "edi", for the content type "application/EDIFACT".                                                                                                     |
|                      |           |  * "x12", for the content type "application/EDI-X12".                                                                                                     |
|                      |           |  * "eco", for the content type "application/edi-consent".                                                                                                 |
|                      |           |  * "xml", for the content type "application/XML".                                                                                                         |
|                      |           |  * "bin", for the content type "application/ octet-stream".                                                                                               |
|                      |           |                                                                                                                                                           |
|                      |           | For other values, Hermes 2 will assume the content type of the payload is "application/deflate", which means that the payload is compressed by Zip.       |
+----------------------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+




**-- SOAP Response Message --**

The element inside the SOAP Body is using namespace URI http://service.as2.edi.cecid.hku.hk/.

A sample SOAP response for the Sender Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <message_id xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="xsd:string" xmlns="http://service.as2.edi.cecid.hku.hk/" xmlns:xsd="http://www.w3.org/2001/XMLSchema"> <Newly created message id>
   </message_id>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

The :code:`<message_id>` element is the :literal:`message identifier` that can be used for later reference and status tracking through the AS2 Status Web Service. 


AS2 Receiver List Web Service
-----------------------------

Service Endpoint: :samp:`http://{<HERMES_HOST>}:{<HERMES_PORT>}/corvus/httpd/as2/receiver_list`

The Receiver List Web Service is for the application of the receiving party to retrieve message identifiers of received AS2 messages which have not been downloaded by the application. The message identifiers will be used to retrieve message payloads with the Receiver Web Service.

**-- SOAP Request Message --**

The Receiver List Web Service requires elements with namespace URI **http://service.as2.edi.cecid.hku.hk/** and namespace prefix **tns**.

A sample SOAP request for the Receiver List Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:as2_from xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <as2_from> </tns:as2_from>
   <tns:as2_to xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <as2_to> </tns:as2_to>
   <tns:numOfMessages xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <numOfMessages> </tns:numOfMessages>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>



The meanings of the elements in the SOAP Body in the above request message are as follows:

+-------------------------+-----------+---------------------------------------------------------------------------------------------+
| Element                 | Mandatory | Description                                                                                 |
+=========================+===========+=============================================================================================+
| :code:`<as2_from>`      | Yes       | The values of the :literal:`From` and :literal:`To` fields in AS2 messages sent through the |
| and :code:`<as2_to>`    |           | partnership by Hermes. These fields are used to identify the sending partnership.           |
| and :code:`<as2_to>`    |           |                                                                                             |
|                         |           | **These are required to query messages associated with the specified partnership.**         |
+-------------------------+-----------+---------------------------------------------------------------------------------------------+
| :code:`<numOfMessages>` | No        | The maximum number of message identifiers retrieved by this request.                        |
+-------------------------+-----------+---------------------------------------------------------------------------------------------+

-- SOAP Response Message --

The element inside the SOAP Body is using namespace URI http://service.as2.edi.cecid.hku.hk/.

A sample SOAP response for the Receiver List Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <messageIds xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="MessageIDs" xmlns="http://service.as2.edi.cecid.hku.hk/" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
   <messageId ns0:type="xsd:string"> <downloadable message id> </messageId>
   <messageId ns0:type="xsd:string"> <downloadable message id> </messageId>
   </messageIds>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>


Each :code:`<message_id>` element in the response message represents the message identifier of an AS2 message received by Hermes 2 of the receiving party.

Note that a message is considered downloaded only when the message body has been downloaded by the Receiver Web Service. If your application never calls the Receiver Web Service to download the messages, the same set of message identifiers will always be retrieved.


AS2 Receiver Web Service
------------------------

Service Endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/receiver.`

The Receiver Web Service is for the application of the receiving party to retrieve the message payloads of received AS2 messages. After the payloads have been downloaded, the message will be marked as received by the application, and the message identifier of the message will no longer be retrieved by the Receiver List Service.
 
.. image:: /_static/images/web_service/h2o-ws-recv.png

**-- SOAP Request Message --**

The Receiver Web Service requires only one element with namespace URI **http://service.as2.edi.cecid.hku.hk/** and namespace prefix **tns**.

A sample SOAP request for the Receiver Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageId xmlns:tns="http://service.as2.edi.cecid.hku.hk/"> <messageId> <The message id you want to download> </tns:messageId>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

**-- SOAP Response Message --**

The element inside the SOAP body is using namespace URI http://service.as2.edi.cecid.hku.hk/.

A sample SOAP response for the Receiver Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <hasMessage xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="xsd:string" xmlns="http://service.as2.edi.cecid.hku.hk/" xmlns:xsd="http://www.w3.org/2001/XMLSchema"> true if payload in message </hasMessage>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

   .
   .
   .
   Attached Payload


If a payload is associated with the message identifier, then :code:`<hasMessage>` will have the value true.
If the received AS2 message has payloads, the response message will have one or more SOAP attachments. Each SOAP attachment has a content type, which is set by the sender application. 


AS2 Status Web Service
----------------------

Service Endpoint: :samp:`http://<OST>:<PORT>/corvus/httpd/as2/status.`

The Status Web Service is for the application of the sending or receiving party to retrieve the message status of a sent or received AS2 message.

**-- SOAP Request Message --**

The Status Web Service requires only one element with namespace URI **http://service.as2.edi.cecid.hku.hk/** and namespace prefix **tns**.

A sample SOAP request for the Status Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageId xmlns:tns="http://service.as2.edi.cecid.hku.hk/"> <messageId> <The message id you want to download> </tns:messageId>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

**-- SOAP Response Message --**

The element :code:`<messageInfo>` inside the SOAP body is using namespace URI http://service.as2.edi.cecid.hku.hk/.

A sample SOAP response for the Status Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <messageInfo xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="MessageInfo" xmlns="http://service.as2.edi.cecid.hku.hk/" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
   <status ns0:type="xsd:string"> <status> </status>
   <statusDescription ns0:type="xsd:string"> <statusDescription> </statusDescription>
   <mdnMessageId ns0:type="xsd:string" > <mdnMessageId> </mdnMessageId>
   <mdnStatus ns0:type="xsd:string" > <mdnStatus> </mdnStatus>
   <mdnStatusDescription ns0:type="xsd:string" > <mdnStatusDescription> </mdnStatusDescription>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>


The meanings of the elements in the SOAP Body in the above response message are as follows:

+--------------------------------+------------------------------------------------------------+
| Element                        | Description                                                |
+================================+============================================================+
| :code:`<status>`               | The current status of the AS2 message.                     |
+--------------------------------+------------------------------------------------------------+
| :code:`<statusDescription>`    | A text description of the current status.                  |
+--------------------------------+------------------------------------------------------------+
| :code:`<mdnMessageId>`         | The message identifier of the associated receipt (if any). |
+--------------------------------+------------------------------------------------------------+
| :code:`<mdnStatus>`            | The current status of the associated receipt.              |
+--------------------------------+------------------------------------------------------------+
| :code:`<mdnStatusDescription>` | A text description of the associated receipt.              |
+--------------------------------+------------------------------------------------------------+


AS2 Message History Web Service
-------------------------------

Service Endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/msg_history`

The Message History Web Service is for the application of the sending or receiving party to query messages according to specific parameters.

.. image:: /_static/images/web_service/MessageHistory.png

**-- SOAP Request Message --**

The Message History Web Service requires only one element with namespace URI **http://service.as2.edi.cecid.hku.hk/** and namespace prefix **tns**.

A sample SOAP request for the Message History Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageBox xmlns:tns="http://service.as2.edi.cecid.hku.hk/"><Message Box></tns:messageBox>
   <tns:status xmlns:tns="http://service.as2.edi.cecid.hku.hk/"><Message Status></tns:status>
   <tns:messageId xmlns:tns="http://service.as2.edi.cecid.hku.hk/"><Message Id></tns:messageId>
   <tns:as2Fromxmlns:tns="http://service.as2.edi.cecid.hku.hk/"><AS2 From Party></tns:as2From>
   <tns:as2Toxmlns:tns="http://service.as2.edi.cecid.hku.hk/"><AS2 To Party></tns:as2To>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

**-- SOAP Response Message --**

The element <messageList> in the SOAP Body is using the namespace URI http://service.as2.edi.cecid.hku.hk/.

A sample SOAP response for the Message History Web Service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <messageList xmlns="http://service.as2.edi.cecid.hku.hk/" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="MessageList">
   <messageElement ns0:type="MessageElement">
   <messageId ns0:type="xsd:string"> MessageID of the Message </messageId>
   <messageBox ns0:type="xsd:string">Message Box containing this message </messageBox>
   </messageElement>
   <messageElement ns0:type="MessageElement">
   <messageId ns0:type="xsd:string"> MessageID of the Message </messageId>
   <messageBox ns0:type="xsd:string"> Message Box containing this message </messageBox>
   </messageElement>
   <messageElement ns0:type="MessageElement"> . . . </messageElement>
   <messageElement ns0:type="MessageElement"> . . . </messageElement>
   </messageList>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

The meanings of the elements in the SOAP Body in the above request message are as follows:

+--------------------------+-----------------------------------------------------------------------------------------+
| Element                  | Description                                                                             |
+==========================+=========================================================================================+
| :code:`<messageList>`    | The list of return message elements.                                                    |
+--------------------------+-----------------------------------------------------------------------------------------+
| :code:`<messageElement>` | A complex element containing the messageId and messageBox values of the return message. |
+--------------------------+-----------------------------------------------------------------------------------------+
| :code:`<messageId>`      | The message identifiers of the return message.                                          |
+--------------------------+-----------------------------------------------------------------------------------------+
| :code:`<messageBox>`     | The message box of the return message.                                                  |
+--------------------------+-----------------------------------------------------------------------------------------+
 
Reference Articles
------------------

    The First Step
    Reference of ebMS 2.0 Partnership Configuration
    Reference of AS2 Partnership Configuration
 
Reference Documentation
-----------------------

    Hermes 2 Application Development Guide

What to read next
-----------------

    Writing Hermes 2 WS Client under JAVA
