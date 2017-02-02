Using SOAP API
==============

Introduction
------------
Hermes has implemented SOAP messaging framework to communicate with external applications instead of using the JAVA-based callback registry mechanisms from Hermes 1. The main advantages of using SOAP web services are reducing coupling between external applications and Hermes, and allowing external applications to integrate Hermes seamlessly using any programming language that supports SOAP and SOAP Messages with Attachments. 

This article is purposed to assist developers who want to write a web service call client to communicate with Hermes using SOAP web services. 

For more information on the installation and partnerships of Hermes, please refer to :doc:`installation` and :doc:`first_step`.

.. image:: /_static/images/web_service/h2o-ws-pl-free.png

Overview
--------

Here is a brief summary about the communication port architecture between Hermes and external applications. The core of Hermes can attach to any J2EE compliant web server as a kind of servlet. The core itself does not provide any SOAP web services or HTTP listeners, nor does it have any functionality related to messaging. All features in Hermes are derived from the core using SPA (simple plugin architecture).

One of the core SPAs, called Main Plugin (shown below in the core SPA layer), provides an HTTP context listener that accepts HTTP requests at the specified context path (extension point) for external invocation. The protocol-specific SPA ebMS and AS2 plugins (shown below in the external SPA layer) make use of this listener to provide all SOAP web services.

By default, the ebMS 2.0 and AS2 plugins each have 5 registered web services in Hermes:

1. `ebMS 2.0 sender web service`_
#. `ebMS 2.0 receiver list web service`_
#. `ebMS 2.0 receiver web service`_
#. `ebMS 2.0 status web service`_
#. `ebMS 2.0 message history web service`_
#. `AS2 sender web service`_
#. `AS2 receiver list web service`_
#. `AS2 receiver web service`_
#. `AS2 status web service`_
#. `AS2 message history web service`_

.. image:: /_static/images/web_service/ws-archtecture.png

.. _ebms-2-0-sender-web-service:

ebMS 2.0 sender web service
---------------------------

Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/sender`

The ebMS 2.0 sender web service is a web service interface for external parties to request Hermes to send an ebMS message to another Hermes or an ebMS compliant messaging gateway. The service provides a message identifier to the sender for future reference. This is the main channel for external applications to deliver ebMS messages using Hermes. 

.. image:: /_static/images/web_service/h2o-ws-sender-ebms.png

**SOAP request message**

Instead of requiring the sender to compose entire ebMS messages or acquire ebMS knowledge, the sender simply needs to request Hermes to do so with key identities including ``CPA ID``, ``Service`` and ``Action``. These 3 key parameter identify the sending partnership in Hermes that will be used to configure the ebMS message.

The sender web service requires elements with namespace URI ``http://service.ebms.edi.cecid.hku.hk/`` and namespace prefix ``tns``.

A sample SOAP request for the sender web service is shown below.

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:cpaId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [CPA_Id] </tns:cpaId>
   <tns:service xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Service] </tns:service>
   <tns:action xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Action] </tns:action>
   <tns:convId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Conversation_Id] </tns:convId>
   <tns:fromPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [From_Party_Id] </tns:fromPartyId>
   <tns:fromPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [From_Party_Type] </tns:fromPartyType>
   <tns:toPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [To_Party_Id] </tns:toPartyId>
   <tns:toPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [To_Party_Type] </tns:toPartyType>
   <tns:refToMessageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Reference_Message_Id] </refToMessageId>
   <tns:serviceType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Service_Type] </tns:serviceType>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   .
   .
   .
   Attached Payload

Descriptions of the elements in the SOAP body are as follows:

+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| Element                  | Mandatory | Description                                                                                  |
+==========================+===========+==============================================================================================+
| ``<cpaId>``,             | Yes       | They are the ``CPA Id``, ``Service`` and ``Action`` elements in the ebMS messages sent by    |
| ``<service>``,           |           | Hermes.                                                                                      |
| ``<action>``             |           |                                                                                              |
|                          |           | These three fields are used to identify the partnership used to send and receive the ebMS    |
|                          |           | messages by the sending and receiving parties respectively.                                  |
|                          |           |                                                                                              |
|                          |           | **These are required to identify a registered partnership in Hermes.**                     |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| ``<convId>``             | Yes       | This corresponds to the ``conversation id`` element in the ebMS messages sent by Hermes.     |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| ``<fromPartyId>``        | Yes       | This identifies the sender.                                                                  |
|                          |           | [`ebMS v2_0 3.1.1 <https://www.oasis-open.org/committees/download.php/272/ebMS_v2_0.pdf>`_]  |
|                          |           |                                                                                              |
|                          |           | It corresponds to the ``PartyId`` element in ``From`` element of ebMS                        |
|                          |           | messages sent by Hermes.                                                                     |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| ``<fromPartyType>``      | Yes       | This identifies the domain of the sender.                                                    |
|                          |           |                                                                                              |
|                          |           | It corresponds to the ``type`` attribute of ``PartyId`` in the ``From``                      |
|                          |           | element of ebMS messages sent by Hermes.                                                     |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| ``<toPartyId>``          | Yes       | This identifies the receiver.                                                                |
|                          |           | [`ebMS v2_0 3.1.1 <https://www.oasis-open.org/committees/download.php/272/ebMS_v2_0.pdf>`_]  |
|                          |           |                                                                                              |
|                          |           | It corresponds to the ``PartyId`` element in ``To`` element of ebMS                          |
|                          |           | messages sent by Hermes.                                                                     |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| ``<toPartyType>``        | Yes       | This identifies the domain of the receiver.                                                  |
|                          |           |                                                                                              |
|                          |           | It corresponds to the ``type`` attribute of ``PartyId`` in the ``From``                      |
|                          |           | element of ebMS messages sent by Hermes.                                                     |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| ``<refToMessageId>``     | No        | This corresponds to the ``RefToMessageId`` of ebMS messages sent by Hermes.                  |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+
| ``<serviceType>``        | No        | A type identifier for the ebXML service defined in the partnership.                          |
+--------------------------+-----------+----------------------------------------------------------------------------------------------+

**SOAP response message**

The element inside the SOAP body is using namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP response for sender web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <message_id xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="xsd:string" 
               xmlns="http://service.ebms.edi.cecid.hku.hk/" 
               xmlns:xsd="http://www.w3.org/2001/XMLSchema"> [Newly_created_message_id]
   </message_id>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

As with the SOAP request message, the ``<message_id>`` element is the ``message identifier`` assigned by Hermes in the sending party. The sending application can use it for later reference and status tracking with the status web service. 

ebMS 2.0 receiver list web service
----------------------------------

Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/receiver_list`

The ebMS receiver list web service is used by the application of the receiving party to retrieve message identifiers of received and processed ebMS messages that have not been downloaded. These message identifiers will be used to retrieve message payloads with the receiver web service.

**SOAP request message**

The receiver list web service requires elements with namespace URI ``http://service.ebms.edi.cecid.hku.hk/`` and namespace prefix ``tns``.

A sample SOAP request for the receiver list web service is shown below: 

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:cpaId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [CPA_Id] </tns:cpaId>
   <tns:service xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Service] </tns:service>
   <tns:action xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Action] </tns:action>
   <tns:convId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Conversation_Id] </tns:convId>
   <tns:fromPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [From_Party_Id] </tns:fromPartyId>
   <tns:fromPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [From_Party_Type] </tns:fromPartyType>
   <tns:toPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [To_Party_Id] </tns:toPartyId>
   <tns:toPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [To_Party_Type] </tns:toPartyType>
   <tns:numOfMessages xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Number_of_messages] </tns:numOfMessages>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

Descriptions of the elements in the SOAP body are as follows:

+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| Element                 | Mandatory | Description                                                                                       |
+=========================+===========+===================================================================================================+
| ``<cpaId>``,            | Yes       | The ``CPA Id``, ``Service`` and ``Action`` elements in ebMS messages sent by Hermes.            |
| ``<service>``,          |           | These three fields identify the partnership used to send ebMS messages.                           |
| ``<action>``            |           |                                                                                                   |
|                         |           | **These are required to query the list of available messages**.                                   |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| ``<convId>``            | No        | Only the identifiers of messages with a matching ``Conversation Id`` will be retrieved.           |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| ``<fromPartyId>``       | No        | Only the identifiers of messages with a matching ``From Party Id`` will be retrieved.             |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| ``<fromPartyType>``     | No        | Only the identifiers of messages with a matching ``From Party Type`` will be retrieved.           |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| ``<toPartyId>``         | No        | Only the identifiers of messages with a matching ``To Party Id`` will be retrieved.               |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| ``<toPartyType>``       | No        | Only the identifiers of messages with a matching ``To Party Type`` will be retrieved.             |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| ``<numOfMessages>``     | No        | The maximum number of message identifiers retrieved by this request.                              |
+-------------------------+-----------+---------------------------------------------------------------------------------------------------+


**SOAP response message**

The element inside the SOAP body is using namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP response for the receiver list web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <messageIds xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="MessageIDs" xmlns="http://service.ebms.edi.cecid.hku.hk/" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
       <messageId ns0:type="xsd:string"> [downloadable_message_id] </messageId>
       <messageId ns0:type="xsd:string"> [downloadable_message_id] </messageId>
   </messageIds>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

Each element in the ``messageIds`` represents the message identifier of an ebMS message received by Hermes.

Note that a message is considered downloaded only when the message body has been downloaded by the ebMS receiver web service. If your application never calls the receiver web service to download the messages, the same set of message identifiers will always be retrieved.


ebMS 2.0 receiver web service
-----------------------------

Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/receiver`

The ebMS receiver web service is used by the application of the receiving party to retrieve message payloads of received ebMS messages. After the message payloads have been downloaded, the message will be marked as received, and its message identifier will no longer be retrieved by the ebMS receiver list web service.

.. image:: /_static/images/web_service/h2o-ws-recv.png

**SOAP request message**

The ebMS receiver web service requires only one element with namespace URI ``http://service.ebms.edi.cecid.hku.hk/`` and namespace prefix ``tns``.

A sample SOAP request for the receiver web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [messageId] [The_message_id_you_want_to_download] </tns:messageId>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>


The ``<messageId>`` element contains a message identifier obtained from the ebMS receiver list web service.


**SOAP response message**

The element inside the SOAP body is using namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP response for the receiver web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <hasMessage xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="xsd:string" xmlns="http://service.ebms.edi.cecid.hku.hk/" xmlns:xsd="http://www.w3.org/2001/XMLSchema"> true if payload in message </hasMessage>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

   .
   .
   .
   Attached Payload

If a payload is associated with the message identifier, the ``<hasMessage>`` element will have the value ``true``.
If the received ebMS message has payloads, the response message will have one or more SOAP attachments. Each SOAP attachment has a content type, which is set by the sending application. 

ebMS 2.0 status web service
---------------------------

Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/status`

The ebMS status web service is used by the application of the sending or receiving party to retrieve the status of a sent or received ebMS message respectively.

The message status is a two-character code indicating the progress of an ebMS message. The ebMS status web service provides a tracking service to monitor ebMS messages requested from Hermes.

**SOAP request message**

The ebMS status web service requires only one element with namespace URI ``http://service.ebms.edi.cecid.hku.hk/`` and namespace prefix ``tns``.

A sample SOAP request for the status web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [messageId] [The_message_id_you_want_to_download] </tns:messageId>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>


The ``<messageId>`` element contains a message identifier obtained from the ebMS sender web service response or the ebMS receiver list web service.

**SOAP response message**

The element inside the SOAP body is using namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP response for the status web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <messageInfo xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" ns0:type="MessageInfo" xmlns="http://service.ebms.edi.cecid.hku.hk/"
   xmlns:xsd="http://www.w3.org/2001/XMLSchema">
       <status ns0:type="xsd:string"> [status] </status>
       <statusDescription ns0:type="xsd:string"> [statusDescription] </statusDescription>
       <ackMessageId ns0:type="xsd:string"> [ackMessageId] </ackMessageId>
       <ackStatus ns0:type="xsd:string"> [ackStatus] </ackStatus>
       <ackStatusDescription ns0:type="xsd:string"> [ackStatusDescription] </ackStatusDescription>
   </messageInfo>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

Descriptions of the elements in the SOAP body are as follows:

+-----------------------------------+--------------------------------------------------------------------+
| Element                           | Description                                                        |
+===================================+====================================================================+
| ``<status>``                      | The current status of the ebMS message.                            |
+-----------------------------------+--------------------------------------------------------------------+
| ``<statusDescription>``           | A text description of the current status.                          |
+-----------------------------------+--------------------------------------------------------------------+
| ``<ackMessageId>``                | The message identifier of the associated acknowledgment (if any).  |
+-----------------------------------+--------------------------------------------------------------------+
| ``<ackStatus>``                   | The current status of the associated acknowledgment (if any).      |
+-----------------------------------+--------------------------------------------------------------------+
| ``<ackStatusDescription>``        | A text description of the associated acknowledgment (if any).      |
+-----------------------------------+--------------------------------------------------------------------+


ebMS 2.0 message history web service
------------------------------------

Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/msg_history`

The ebMS message history web service is used by the application of the sending or receiving party to query messages according to specific parameters.

.. image:: /_static/images/web_service/MessageHistory.png

**SOAP request message**

The ebMS message history web service requires elements with namespace URI ``http://service.ebms.edi.cecid.hku.hk/`` and namespace prefix ``tns``.

A sample SOAP request for the message history web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageBox xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Message_Box]</tns:messageBox>
   <tns:status xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Message_Status]</tns:status>
   <tns:messageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Message_Id]</tns:messageId>
   <tns:conversationId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Conversation_Id]</tns:conversationId>
   <tns:cpaId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[CPA_Id]</tns:cpaId>
   <tns:service xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Defined_Service_with_trading_party]</tns:service>
   <tns:action xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Action]</tns:action>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

**SOAP response message**

The element ``<messageList>`` inside the SOAP body is using namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP response for the message history web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <messageList xmlns="http://service.ebms.edi.cecid.hku.hk/" 
                xmlns:xsd="http://www.w3.org/2001/XMLSchema"
                xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance"
                ns0:type="MessageList">
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


Descriptions of the elements in the SOAP body are as follows:

+--------------------------+----------------------------------------------------------------------------------------------+
| Element                  | Description                                                                                  |
+==========================+==============================================================================================+
| ``<messageList>``        | A list of retrieved message elements (if any).                                               |
+--------------------------+----------------------------------------------------------------------------------------------+
| ``<messageElement>``     | A complex element containing ``messageId`` and ``messageBox`` values of a retrieved message. |
+--------------------------+----------------------------------------------------------------------------------------------+
| ``<messageId>``          | The message identifier of a retrieved message.                                               |
+--------------------------+----------------------------------------------------------------------------------------------+
| ``<messageBox>``         | The message box of a retrieved message.                                                      |
+--------------------------+----------------------------------------------------------------------------------------------+


AS2 sender web service
----------------------

Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/sender`

The AS2 sender web service is used by the application of the sending party to request Hermes to send an AS2 message to another Hermes or a compatible messaging gateway. The service returns a message identifier to the application for future reference.

.. image:: /_static/images/web_service/h2o-ws-sender-as2.png

**SOAP request message**

The sender web service requires elements with namespace URI ``http://service.as2.edi.cecid.hku.hk/`` and namespace prefix ``tns``.

A sample SOAP request for the sender web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:as2_from xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [as2_from] </tns:as2_from>
   <tns:as2_to xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [as2_to] </tns:as2_to>
   <tns:type xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [type] </tns:type>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

   .
   .
   .
   Attached Payload

Descriptions of the elements in the SOAP body are as follows:

+----------------------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
| Element              | Mandatory | Description                                                                                                                                               |
+======================+===========+===========================================================================================================================================================+
| ``<as2_from>``,      | Yes       | The values of the ``From`` and ``To`` fields in AS2 messages sent through the                                                                             |
| ``<as2_to>``         |           | partnership by Hermes. These fields are used to identify the sending partnership.                                                                       |
|                      |           |                                                                                                                                                           |
|                      |           | **These are required to identify the message destination.**                                                                                               |
+----------------------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
| ``<type>``           | Yes       | A three-character code indicating the content type of the sent payload. The available codes are:                                                          |
|                      |           |                                                                                                                                                           |
|                      |           |  * ``edi``, for the content type ``application/EDIFACT``.                                                                                                 |
|                      |           |  * ``x12``, for the content type ``application/EDI-X12``.                                                                                                 |
|                      |           |  * ``eco``, for the content type ``application/edi-consent``.                                                                                             |
|                      |           |  * ``xml``, for the content type ``application/XML``.                                                                                                     |
|                      |           |  * ``bin``, for the content type ``application/ octet-stream``.                                                                                           |
|                      |           |                                                                                                                                                           |
|                      |           | For other values, Hermes will assume the content type of the payload is ``application/deflate``, which means that the payload is compressed by Zip.     |
+----------------------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+




**SOAP response message**

The element inside the SOAP body is using namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP response for the sender web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <message_id xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" 
               ns0:type="xsd:string"
               xmlns="http://service.as2.edi.cecid.hku.hk/"
               xmlns:xsd="http://www.w3.org/2001/XMLSchema"> [Newly_created_message_Id]
   </message_id>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

The ``<message_id>`` element is the identifier of the sent message that can be used for later reference and status tracking with the AS2 status web service. 


AS2 receiver list web service
-----------------------------

Service endpoint: :samp:`http://{<HERMES_HOST>}:{<HERMES_PORT>}/corvus/httpd/as2/receiver_list`

The AS2 receiver list web service is used by the application of the receiving party to retrieve message identifiers of received AS2 messages which have not been downloaded by the application. The message identifiers will be used to retrieve message payloads using the AS2 receiver web service.

**SOAP request message**

The receiver list web service requires elements with namespace URI ``http://service.as2.edi.cecid.hku.hk/`` and namespace prefix ``tns``.

A sample SOAP request for the receiver list web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:as2_from xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [as2_from] </tns:as2_from>
   <tns:as2_to xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [as2_to] </tns:as2_to>
   <tns:numOfMessages xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [numOfMessages] </tns:numOfMessages>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

Descriptions of the elements in the SOAP body are as follows:

+-------------------------+-----------+---------------------------------------------------------------------------------------------+
| Element                 | Mandatory | Description                                                                                 |
+=========================+===========+=============================================================================================+
| ``<as2_from>``,         | Yes       | The values of the ``From`` and ``To`` fields in AS2 messages sent through the               |
| ``<as2_to>``,           |           | partnership by Hermes. These fields are used to identify the sending partnership.         |
| ``<as2_to>``            |           |                                                                                             |
|                         |           | **These are required to query messages associated with the specified partnership.**         |
+-------------------------+-----------+---------------------------------------------------------------------------------------------+
| ``<numOfMessages>``     | No        | The maximum number of message identifiers retrieved by this request.                        |
+-------------------------+-----------+---------------------------------------------------------------------------------------------+

**SOAP response message**

The element inside the SOAP body is using namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP response for the receiver list web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <messageIds xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" 
               ns0:type="MessageIDs"
               xmlns="http://service.as2.edi.cecid.hku.hk/"
               xmlns:xsd="http://www.w3.org/2001/XMLSchema">
       <messageId ns0:type="xsd:string"> [downloadable_message_id] </messageId>
       <messageId ns0:type="xsd:string"> [downloadable_message_id] </messageId>
   </messageIds>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>


Each ``<message_id>`` element in the response message represents the identifier of an AS2 message received by Hermes.

Note that a message is considered downloaded only when the message body has been downloaded by the AS2 receiver web service. If your application never calls the receiver web service to download the messages, the same set of message identifiers will always be retrieved.


AS2 receiver web service
------------------------

Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/receiver.`

The AS2 receiver web service is used by the application of the receiving party to retrieve the message payloads of received AS2 messages. After the payloads have been downloaded, the message will be marked as received, and the message identifier of the message will no longer be retrieved by the AS2 receiver list service.
 
.. image:: /_static/images/web_service/h2o-ws-recv.png

**SOAP request message**

The receiver web service requires only one element with namespace URI ``http://service.as2.edi.cecid.hku.hk/`` and namespace prefix ``tns``.

A sample SOAP request for the receiver web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageId xmlns:tns="http://service.as2.edi.cecid.hku.hk/"> [messageId] [The_message_id_you_want_to_download] </tns:messageId>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

**SOAP response message**

The element inside the SOAP body is using namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP response for the receiver web service is shown below:

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


If a payload is associated with the message identifier, then ``<hasMessage>`` will have the value ``true``.
If the received AS2 message has payloads, the response message will have one or more SOAP attachments. Each SOAP attachment has a content type, which is set by the sender application. 


AS2 status web service
----------------------

Service endpoint: :samp:`http://{<OST>}:{<PORT>}/corvus/httpd/as2/status.`

The AS2 status web service is used by the application of the sending or receiving party to retrieve the message status of a sent or received AS2 message respectively.

**SOAP request message**

The status web service requires only one element with namespace URI ``http://service.as2.edi.cecid.hku.hk/`` and namespace prefix ``tns``.

A sample SOAP request for the status web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageId xmlns:tns="http://service.as2.edi.cecid.hku.hk/"> [messageId] [The_message_id_you_want_to_download] </tns:messageId>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

**SOAP response message**

The element ``<messageInfo>`` inside the SOAP body is using namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP response for the status web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <messageInfo xmlns:ns0="http://www.w3.org/2001/XMLSchema-instance" 
                ns0:type="MessageInfo"
                xmlns="http://service.as2.edi.cecid.hku.hk/"
                xmlns:xsd="http://www.w3.org/2001/XMLSchema">
       <status ns0:type="xsd:string"> [status] </status>
       <statusDescription ns0:type="xsd:string"> [statusDescription] </statusDescription>
       <mdnMessageId ns0:type="xsd:string" > [mdnMessageId] </mdnMessageId>
       <mdnStatus ns0:type="xsd:string" > [mdnStatus] </mdnStatus>
       <mdnStatusDescription ns0:type="xsd:string" > [mdnStatusDescription] </mdnStatusDescription>
   </messageInfo>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>


Descriptions of the elements in the SOAP body are as follows:

+--------------------------------+------------------------------------------------------------+
| Element                        | Description                                                |
+================================+============================================================+
| ``<status>``                   | The current status of the AS2 message.                     |
+--------------------------------+------------------------------------------------------------+
| ``<statusDescription>``        | A text description of the current status.                  |
+--------------------------------+------------------------------------------------------------+
| ``<mdnMessageId>``             | The message identifier of the associated receipt (if any). |
+--------------------------------+------------------------------------------------------------+
| ``<mdnStatus>``                | The current status of the associated receipt.              |
+--------------------------------+------------------------------------------------------------+
| ``<mdnStatusDescription>``     | A text description of the associated receipt.              |
+--------------------------------+------------------------------------------------------------+


AS2 message history web service
-------------------------------

Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/msg_history`

The AS2 message history web service is used by the application of the sending or receiving party to query messages according to specific parameters.

.. image:: /_static/images/web_service/MessageHistory.png

**SOAP request message**

The message history web service requires elements with namespace URI ``http://service.as2.edi.cecid.hku.hk/`` and namespace prefix ``tns``.

A sample SOAP request for the message history web service is shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageBox xmlns:tns="http://service.as2.edi.cecid.hku.hk/">[Message_Box]</tns:messageBox>
   <tns:status xmlns:tns="http://service.as2.edi.cecid.hku.hk/">[Message_Status]</tns:status>
   <tns:messageId xmlns:tns="http://service.as2.edi.cecid.hku.hk/">[Message_Id]</tns:messageId>
   <tns:as2From xmlns:tns="http://service.as2.edi.cecid.hku.hk/">[AS2_From_Party]</tns:as2From>
   <tns:as2To xmlns:tns="http://service.as2.edi.cecid.hku.hk/">[AS2_To_Party]</tns:as2To>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

**SOAP response message**

The element ``<messageList>`` in the SOAP body is using the namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP response for the message history web service is shown below:

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

Descriptions of the elements in the SOAP body are as follows:

+--------------------------+----------------------------------------------------------------------------------------------------+
| Element                  | Description                                                                                        |
+==========================+====================================================================================================+
| ``<messageList>``        | The list of retrieved message elements.                                                            |
+--------------------------+----------------------------------------------------------------------------------------------------+
| ``<messageElement>``     | A complex element containing the ``messageId`` and ``messageBox`` values of the retrieved message. |
+--------------------------+----------------------------------------------------------------------------------------------------+
| ``<messageId>``          | The message identifier of the retrieved message.                                                   |
+--------------------------+----------------------------------------------------------------------------------------------------+
| ``<messageBox>``         | The message box of the retrieved message.                                                          |
+--------------------------+----------------------------------------------------------------------------------------------------+
 
See also
--------
* :doc:`first_step`
* :doc:`ebms_partnership`
* :doc:`as2_partnership`