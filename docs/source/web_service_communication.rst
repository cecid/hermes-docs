Using Hermes API
================

Introduction
------------
Hermes has implemented web services to communicate with external applications. The main advantages of using web services are to reduce coupling between external applications and Hermes, and to allow external applications to integrate Hermes seamlessly using any programming languages that support sending SOAP Messages with Attachments or calling RESTful APIs. This article helps developers  write a client talking to Hermes using web services based on SOAP or RESTful APIs. 

For more information on the installation and partnerships of Hermes, please refer to :doc:`installation` and :doc:`first_step`.

To choose whether to use SOAP or REST APIs in your application, you may refer to `Understanding SOAP and REST Basics and Differences <http://blog.smartbear.com/apis/understanding-soap-and-rest-basics/>`_ for guidance.

.. image:: /_static/images/web_service/h2o-ws-pl-free.png

Overview
--------

Here is a brief summary about the communication architecture between Hermes and external applications. The core of Hermes can attach to any J2EE compliant web server as a servlet. The core itself provides neither any web services or HTTP listeners, nor any functionality related to messaging. All features in Hermes are derived from the core using SPA (Simple Plugin Architecture).

One of the core SPAs, called Main Plugin (shown below in the core SPA layer), provides an HTTP context listener that accepts HTTP requests at the specified context path (extension point) for external invocation. The protocol-specific SPA ebMS and AS2 plugins (shown below in the external SPA layer) make use of this listener to provide all SOAP and REST web services.

.. image:: /_static/images/web_service/ws-archtecture.png

In the default Hermes installation, each of ebMS 2.0 and AS2 plugins supports the following registered web services in Hermes:

.. csv-table:: ebMS 2.0 Hermes API
   :header: "Functionality          ", "REST(ebMS) [1]_", "SOAP(ebMS)"

   ":ref:`ebms-2-0-send-message-ws`", "POST:corvus/api/message/send/ebms", "/corvus/httpd/ebms/sender"
   ":ref:`ebms-2-0-list-message-ws`", "GET:/corvus/api/message/receive/ebms", "/corvus/httpd/ebms/receiver_list"
   ":ref:`ebms-2-0-receiver-ws`", "POST:/corvus/api/message/receive/ebms", "/corvus/httpd/ebms/receiver"
   ":ref:`ebms-2-0-get-status-ws`", "GET:/corvus/api/message/send/ebms", "/corvus/httpd/ebms/status"
   ":ref:`ebms-2-0-reset-status-ws`", "POST:/corvus/api/message/redownload/ebms", "/corvus/httpd/ebms/permitdl"
   ":ref:`ebms-2-0-query-message-ws`", "GET:/corvus/api/message/history/ebms", "/corvus/httpd/ebms/msg_history"
   ":ref:`ebms-2-0-add-partnership-ws`", "POST:/corvus/api/partnership/ebms", "NIL"
   ":ref:`ebms-2-0-delete-partnership-ws`", "DELETE /corvus/api/partnership/ebms/{pid}", "NIL"
   ":ref:`ebms-2-0-update-partnership-ws`", "POST:/corvus/api/partnership/ebms", "NIL"
   ":ref:`ebms-2-0-get-partnership-ws`", "GET:/corvus/api/partnership/ebms", "NIL"

.. csv-table:: AS2 Hermes API
   :header: "Functionality          ", "REST(AS2) [1]_", "SOAP(AS2)"

   ":ref:`as2-2-0-send-message-ws`", "POST:/corvus/api/message/send/as2", "/corvus/httpd/as2/sender"
   ":ref:`as2-2-0-list-message-ws`", "GET:/corvus/api/message/receive/as2", "/corvus/httpd/as2/receiver_list"
   ":ref:`as2-2-0-receiver-ws`", "POST:/corvus/api/message/receive/as2", "/corvus/httpd/as2/receiver"
   ":ref:`as2-2-0-get-status-ws`", "GET:/corvus/api/message/send/as2", "/corvus/httpd/as2/status"
   "Reset message status", "NIL", "NIL"
   ":ref:`as2-2-0-query-message-ws`", "GET:/corvus/api/message/history/as2", "/corvus/httpd/as2/msg_history"
   ":ref:`as2-2-0-add-partnership-ws`", "POST:/corvus/api/partnership/as2", "NIL"
   ":ref:`as2-2-0-delete-partnership-ws`", "DELETE /corvus/api/partnership/as2/{pid}", "NIL"
   ":ref:`as2-2-0-update-partnership-ws`", "POST:/corvus/api/partnership/as2", "NIL"
   ":ref:`as2-2-0-get-partnership-ws`", "GET:/corvus/api/partnership/as2", "NIL"

.. _ebms-2-0-web-service:

ebMS 2.0 Web Service
====================

.. _ebms-2-0-send-message-ws:

Send message
------------

This is a web service interface for external parties to request Hermes to send an ebMS message to another Hermes or an ebMS compliant messaging gateway. The service provides a message identifier to the sender for future reference. This is the main channel for external applications to deliver ebMS messages using Hermes. 

.. image:: /_static/images/web_service/h2o-ws-sender-ebms.png

.. _ebms-2-0-sender-soap:

SOAP
````
Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/sender`

**Request message**

Instead composing the entire ebMS messages, the sender simply needs to send a web service request to Hermes with key parameters including ``CPA ID``, ``Service`` and ``Action``. These 3 key parameters identify the sending partnership in Hermes that will be used to configure the ebMS message.

The elements in the SOAP body use the namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP request is shown below.

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
       <SOAP-ENV:Header/>
       <SOAP-ENV:Body>
           <tns:cpaId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[CPA_Id]</tns:cpaId>
           <tns:service xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Service]</tns:service>
           <tns:action xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Action]</tns:action>
           <tns:convId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Conversation_Id]</tns:convId>
           <tns:fromPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[From_Party_Id]</tns:fromPartyId>
           <tns:fromPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[From_Party_Type]</tns:fromPartyType>
           <tns:toPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[To_Party_Id]</tns:toPartyId>
           <tns:toPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[To_Party_Type]</tns:toPartyType>
           <tns:refToMessageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Reference_Message_Id]</refToMessageId>
           <tns:serviceType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Service_Type]</tns:serviceType>
       </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>
    <!-- Attached payloads... -->

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
|                          |           | **These are required to identify a registered partnership in Hermes.**                       |
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

**Response message**

The elements inside the SOAP body ueses namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP response is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
            <SOAP-ENV:Body>
                <message_id xmlns="http://service.ebms.edi.cecid.hku.hk/">[newly_created_message_id]</message_id>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>

In the SOAP request message, the ``<message_id>`` element is the ``message identifier`` assigned by Hermes in the sending party. The sending application can use it for later reference and status tracking with :ref:`ebms-2-0-get-status-ws` web service. 

.. _ebms-2-0-sender-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh
    
    $ curl -X POST --data '{"partnership_id":"<partnership_id>", "from_party_id":"<from>", "to_party_id":"<to>", "conversation_id":"<conv>", "payload":"<payload>"}' http://<HOST>:<PORT>/corvus/api/message/send/ebms

**Response message**

.. code-block:: json

    {
        "id": "<message_id>"
    }

For the details specification of this REST API, please refer to `HERMES RESTful OpenAPI Specification <https://app.swaggerhub.com/apis/cecid-dev/Hermes2/1.0.0>`_.

.. _ebms-2-0-list-message-ws:

List received message ID
------------------------

This web service is used by the application of the receiving party to retrieve message identifiers of received and processed ebMS messages that have not been downloaded. These message identifiers will be used to retrieve message payloads with :ref:`ebms-2-0-receiver-ws` web service.

.. _ebms-2-0-list-message-soap:

SOAP
````
Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/receiver_list`

**Request message**

The elements in the SOAP body use the namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP request is shown below: 

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <tns:cpaId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[CPA_Id]</tns:cpaId>
            <tns:service xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Service]</tns:service>
            <tns:action xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Action]</tns:action>
            <tns:convId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Conversation_Id]</tns:convId>
            <tns:fromPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[From_Party_Id]</tns:fromPartyId>
            <tns:fromPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[From_Party_Type]</tns:fromPartyType>
            <tns:toPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[To_Party_Id]</tns:toPartyId>
            <tns:toPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[To_Party_Type]</tns:toPartyType>
            <tns:numOfMessages xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Number_of_messages]</tns:numOfMessages>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>

Descriptions of the elements in the SOAP body are as follows:

+-------------------------+-----------+---------------------------------------------------------------------------------------------------+
| Element                 | Mandatory | Description                                                                                       |
+=========================+===========+===================================================================================================+
| ``<cpaId>``,            | Yes       | The ``CPA Id``, ``Service`` and ``Action`` elements in ebMS messages sent by Hermes.              |
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


**Response message**

The elements inside the SOAP body use the namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP response is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <messageIds xmlns="http://service.ebms.edi.cecid.hku.hk/">
                <messageId>[downloadable_message_id]</messageId>
                <messageId>[downloadable_message_id]</messageId>
            </messageIds>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>

Each element in the ``messageIds`` represents the message identifier of an ebMS message received by Hermes.

.. _ebms-2-0-list-message-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh

    $ curl -X GET http://<HOST>:<PORT>/corvus/api/message/receive/ebms?partnership_id=<partnership_id>

**REST reponse message**

.. code-block:: json

    {
        "message_ids": [
            {
                "id": "<message_id>",
                "timestamp": 1234567890,
                "status": "<status>" 
            }
        ]
    }


Please note that a message is considered to be downloaded only when the message body has been downloaded by :ref:`ebms-2-0-receiver-ws` web service. If your application never calls :ref:`ebms-2-0-receiver-ws` web service to download the messages, the same set of message identifiers will always be retrieved.

For the details specification of this REST API, please refer to `HERMES RESTful OpenAPI Specification <https://app.swaggerhub.com/apis/cecid-dev/Hermes2/1.0.0>`_.

.. _ebms-2-0-receiver-ws:

Download received message payload
---------------------------------

This web service is used by the application of the receiving party to retrieve message payloads of received ebMS messages. After the message payloads have been downloaded, the message will be marked as received, and its message identifier will no longer be retrieved by :ref:`ebms-2-0-list-message-ws` web service.

.. image:: /_static/images/web_service/h2o-ws-recv.png

.. _ebms-2-0-receiver-soap:

SOAP
````
Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/receiver`

**Request message**

The elements in the SOAP body use the namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP request is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <tns:messageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[id_of_message_to_download]</tns:messageId>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>

The ``<messageId>`` element contains a message identifier which obtained from :ref:`ebms-2-0-list-message-ws` web service.

**Response message**

The element inside the SOAP body is using namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP response is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <hasMessage xmlns="http://service.ebms.edi.cecid.hku.hk/">[true_if_payload_in_message]</hasMessage>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>
    <!--
        Attached payloads...
    -->

If a payload is associated with the message identifier, the ``<hasMessage>`` element will have the value ``true``.
If the received ebMS message has payloads, the response message will have one or more SOAP attachments. Each SOAP attachment has a content type, which is set by the sending application. 

.. _ebms-2-0-receiver-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh

    $ curl -X POST --data '{"message_id":"<message_id"}' http://<HOST>:<PORT>/corvus/api/message/receive/ebms

**Response message**

.. code-block:: json

    {
        "id": "<message_id>",
        "cpa_id": "<cpa>", 
        "service": "<service>",
        "action": "<action>",
        "from_party_id": "<from>",
        "to_party_id": "<to>",
        "conversation_id": "<conv>",
        "timestamp": 1234567890,
        "status": "<status>",
        "payloads": [
            {
                "payload": "<content>"
            }
        ]
    }

For the details specification of this REST API, please refer to `HERMES RESTful OpenAPI Specification <https://app.swaggerhub.com/apis/cecid-dev/Hermes2/1.0.0>`_.

.. _ebms-2-0-get-status-ws:

Get message status
------------------

This web service is used by the application of the sending party to retrieve the status of a delivered ebMS message.

The message status is a two-character code indicating the progress of an ebMS message. It provides a tracking service to monitor ebMS messages requested from Hermes.

.. _ebms-2-0-get-status-soap:

SOAP
````

Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/status`

**Request message**

The elements in the SOAP body use the namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP request is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <tns:messageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[id_of_message_to_download]</tns:messageId>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>

The ``<messageId>`` element contains a message identifier obtained from :ref:`ebms-2-0-send-message-ws` web service response or :ref:`ebms-2-0-list-message-ws` web service.

**Response message**

The element inside the SOAP body is using namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP response is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <messageInfo xmlns="http://service.ebms.edi.cecid.hku.hk/">
                <status>[status]</status>
                <statusDescription>[statusDescription]</statusDescription>
                <ackMessageId>[ackMessageId]</ackMessageId>
                <ackStatus>[ackStatus]</ackStatus>
                <ackStatusDescription>[ackStatusDescription]</ackStatusDescription>
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

.. _ebms-2-0-get-status-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh

    $ curl -X GET http://<HOST>:<PORT>/corvus/api/message/send/ebms?id=<message_id>
   
**Response message**
      
.. code-block:: json

    {
        "message_id": "<message_id>",
        "status": "<status>"
    }

For the details specification of this REST API, please refer to `HERMES RESTful OpenAPI Specification <https://app.swaggerhub.com/apis/cecid-dev/Hermes2/1.0.0>`_.

.. _ebms-2-0-reset-status-ws:

Reset message status
--------------------

This web service is used by the application of the receiving party to reset the status of a downloaded ebMS message from ``DL`` (delivered) to ``PS`` (processed), so that it can be redownloaded again.

.. _ebms-2-0-reset-status-soap:

SOAP
````
Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/permitdl`

**Request message**

The elements in the SOAP body use the namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP request is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <tns:messageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">
                [The_message_id_you_want_to_redownload] 
            </tns:messageId>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>

The ``<messageId>`` element contains a message identifier obtained from the ebMS sender web service response or the ebMS receiver list web service.

**Response message**

The element inside the SOAP body is using namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP response is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <message_id xmlns="http://service.ebms.edi.cecid.hku.hk/">[newly_created_message_id]</message_id>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>

In the SOAP request message, the ``<message_id>`` element is the ``message identifier`` where they are the same if reset status successfully.

.. _ebms-2-0-reset-status-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh

    $ curl -X POST --data '{"message_id":"<message_id>"}' http://<HOST>:<PORT>/corvus/api/message/redownload/ebms

   
**Response message**
      
.. code-block:: json

    {
        "id": "<message_id>"
    }

For the details specification of this REST API, please refer to `HERMES RESTful OpenAPI Specification <https://app.swaggerhub.com/apis/cecid-dev/Hermes2/1.0.0>`_.

.. _ebms-2-0-query-message-ws:

Query message with parameters
-----------------------------

This web service is used by the application of the sending or receiving party to query messages according to specific parameters.

.. image:: /_static/images/web_service/MessageHistory.png

.. _ebms-2-0-query-message-soap:

SOAP
````
Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/msg_history`

**Request message**

The elements in the SOAP body use the namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP request is shown below:

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

**Response message**

The element ``<messageList>`` inside the SOAP body use the namespace URI ``http://service.ebms.edi.cecid.hku.hk/``.

A sample SOAP response is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <messageList xmlns="http://service.ebms.edi.cecid.hku.hk/">
                <messageElement>
                    <messageId>[message_id]</messageId>
                    <messageBox>[message_box_containing_this_message]</messageBox>
                </messageElement>
                <messageElement>
                    <messageId>[message_id]</messageId>
                    <messageBox>[message_box_containing_this_message]</messageBox>
                </messageElement>
                <messageElement>...</messageElement>
                <messageElement>...</messageElement>
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

.. _ebms-2-0-query-message-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh

    $ curl -X GET http://<HOST>:<PORT>/corvus/api/message/history/ebms?message_id=<message_id>&message_box=<message_box>&conversation_id=<cid>&cpa_id=<cpa_id>&service=<service>&action=<action>&status=<status>&limit=<limit>
   
**Response message**
      
.. code-block:: json

    {
        "message_ids": [ 
            { 
                "id": "<id>", 
                "cpa_id": "<cpa_id>", 
                "service": "<service>", 
                "action": "<action>", 
                "conversation_id": "<conversation_id>", 
                "message_box": "<message_box>", 
                "timestamp": "<timestamp>",
                "status": "<status>"
            } 
        ] 
    }

For the details specification of this REST API, please refer to `HERMES RESTful OpenAPI Specification <https://app.swaggerhub.com/apis/cecid-dev/Hermes2/1.0.0>`_.

.. _ebms-2-0-add-partnership-ws:

Add partnership
---------------

The ebMS Add Partnership web service is used by the application of the sending and receiving party to create partnership. For further details about ebMS partnership, please refer to :doc:`ebms_partnership`.

.. _ebms-2-0-add-partnership-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh
    
    $ curl -X POST -- data '{"id":"<partnership_id>", "cpa_id":"<cpa>", "service":"<service>", "action":"<action>", "transport-endpoint":"http://<RECEIVER HOST>:<RECEIVER PORT>/corvus/httpd/ebms/inbound"}' \
    http://<SENDER_HOST>:<SENDER_PORT>/corvus/api/partnership/ebms

**Response message**
      
.. code-block:: json

    {
        "id" : "<partnership_id>"
    }

.. _ebms-2-0-delete-partnership-ws:

Delete partnership
------------------

The ebMS delete Partnership web service is used by the application of the sending and receiving party to delete partnership.

.. _ebms-2-0-delete-partnership-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh
    
    $ curl -X DELETE http://<HOST>:<PORT>/corvus/api/partnership/ebms/<partnership_id>

**Response message**

.. code-block:: json

    {
        "id": "<partnership_id>",
        "success": true
    }

.. _ebms-2-0-update-partnership-ws:

Update partnership
------------------

The ebMS update Partnership web service is used by the application of the sending and receiving party to update partnership. For further details about ebMS partnership, please refer to :doc:`ebms_partnership`.

.. _ebms-2-0-update-partnership-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh
    
    $ curl -X POST -- data '{"id":"<partnership_id>", "cpa_id":"<cpa>", "service":"<service>", "action":"<action>", "transport-endpoint":"http://<RECEIVER HOST>:<RECEIVER PORT>/corvus/httpd/ebms/inbound"}' \
    http://<SENDER_HOST>:<SENDER_PORT>/corvus/api/partnership/ebms

**Response message**
      
.. code-block:: json

    {
        "id": "<partnership_id>"
    }


.. _ebms-2-0-get-partnership-ws:

Get partnerships
----------------

The ebMS get Partnership web service is used by the application of the sending and receiving party to get all partnership details.

.. _ebms-2-0-get-partnerships-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh
    
    $ curl -X GET http://<HOST>:<PORT>/corvus/api/partnership/ebms

**Response message**

.. code-block:: json

    {
        "partnerships": [
            {
                "id": "<partership_id>",
                "cpa_id": "<cpa>",
                "service": "<service>",
                "action": "<action>",
                "disabled": false,
                "transport_endpoint": "http://<HOST>:<PORT>/corvus/httpd/ebms/inbound",
                "ack_requested": null, 
                "signed_ack_requested": null,
                "duplicate_elimination": null,
                "message_order": null,
                "retries": 0,
                "retry_interval": 0,
                "sign_requested": false,
                "sign_certicate": null
            }
        ]
    }

.. _as2-2-0-web-service:

AS2 Web Service
===============

.. _as2-2-0-send-message-ws:

Send Message
------------

This web service is used by the application of the sending party to request Hermes to send an AS2 message to another Hermes or a compatible messaging gateway. The service returns a message identifier to the application for future reference.

.. image:: /_static/images/web_service/h2o-ws-sender-as2.png

.. _as2-2-0-send-message-soap:

SOAP
````
Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/sender`

**Request message**

The elements in the SOAP body use the namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP request is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <tns:as2_from xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[as2_from]</tns:as2_from>
            <tns:as2_to xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[as2_to]</tns:as2_to>
            <tns:type xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[type]</tns:type>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>
    <!-- Attached payloads... -->

Descriptions of the elements in the SOAP body are as follows:

+----------------------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
| Element              | Mandatory | Description                                                                                                                                               |
+======================+===========+===========================================================================================================================================================+
| ``<as2_from>``,      | Yes       | The values of the ``From`` and ``To`` fields in AS2 messages sent through the                                                                             |
| ``<as2_to>``         |           | partnership by Hermes. These fields are used to identify the sending partnership.                                                                         |
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
|                      |           | For other values, Hermes will assume the content type of the payload is ``application/deflate``, which means that the payload is compressed by Zip.       |
+----------------------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+


**Response message**

The elements inside the SOAP body use the namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP response is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <message_id xmlns="http://service.as2.edi.cecid.hku.hk/">[newly_created_message_Id]</message_id>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>

The ``<message_id>`` element is the identifier of the sent message that can be used for later reference and status tracking with :ref:`as2-2-0-get-status-ws` web service. 

.. _as2-2-0-sender-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh
    
    $ curl -X POST --data '{  "as2_from": <as2_from>, "as2_to": <as2_to>, "type": <type>, "payload": <payload>}' http://<HOST>:<PORT>/corvus/api/message/send/as2

**Response message**

.. code-block:: json

    { 
        "id": "<message_id>"
    }

.. note:: 
   To try the REST API, the simplest way is to use ``curl`` as a command line REST client, or Postman as a GUI based client is a useful tool too.

For the details specification of this REST API, please refer to `HERMES RESTful OpenAPI Specification <https://app.swaggerhub.com/apis/cecid-dev/Hermes2/1.0.0>`_.

.. _as2-2-0-list-message-ws:

List received message ID
------------------------

This web service is used by the application of the receiving party to retrieve message identifiers of received AS2 messages which have not been downloaded by the application. The message identifiers will be used to retrieve message payloads using :ref:`as2-2-0-receiver-ws` web service.

.. _as2-2-0-list-message-soap:

SOAP
````
Service endpoint: :samp:`http://{<HERMES_HOST>}:{<HERMES_PORT>}/corvus/httpd/as2/receiver_list`

**Request message**

The elements in the SOAP body use the namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP request is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <tns:as2_from xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[as2_from]</tns:as2_from>
            <tns:as2_to xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[as2_to]</tns:as2_to>
            <tns:numOfMessages xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[numOfMessages]</tns:numOfMessages>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>

Descriptions of the elements in the SOAP body are as follows:

+-------------------------+-----------+---------------------------------------------------------------------------------------------+
| Element                 | Mandatory | Description                                                                                 |
+=========================+===========+=============================================================================================+
| ``<as2_from>``,         | Yes       | The values of the ``From`` and ``To`` fields in AS2 messages sent through the               |
| ``<as2_to>``,           |           | partnership by Hermes. These fields are used to identify the sending partnership.           |
| ``<as2_to>``            |           |                                                                                             |
|                         |           | **These are required to query messages associated with the specified partnership.**         |
+-------------------------+-----------+---------------------------------------------------------------------------------------------+
| ``<numOfMessages>``     | No        | The maximum number of message identifiers retrieved by this request.                        |
+-------------------------+-----------+---------------------------------------------------------------------------------------------+

**Response message**

The elements inside the SOAP body use the namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP response is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <messageIds xmlns="http://service.as2.edi.cecid.hku.hk/">
                <messageId>[downloadable_message_id]</messageId>
                <messageId>[downloadable_message_id]</messageId>
            </messageIds>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>

Each ``<downloadable_message_id>`` element in the response message represents the identifier of an AS2 message received by Hermes.

.. _as2-2-0-list-message-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh

    $ curl -X GET http://<HOST>:<PORT>/corvus/api/message/receive/as2?partnership_id=<partnership_id>

**REST reponse message**

.. code-block:: json

    {
        "message_ids": [
            {
                "id": "<message_id>",
                "timestamp": 1234567890,
                "status": "<status>"
            }
        ]
    }

Note that a message is considered to be downloaded only when the message body has been downloaded by :ref:`as2-2-0-receiver-ws` web service. If your application never calls the :ref:`as2-2-0-receiver-ws` web service to download the messages, the same set of message identifiers will always be retrieved.

For the details specification of this REST API, please refer to `HERMES RESTful OpenAPI Specification <https://app.swaggerhub.com/apis/cecid-dev/Hermes2/1.0.0>`_.

.. _as2-2-0-receiver-ws:

Download received message payload
---------------------------------

This web service is used by the application of the receiving party to retrieve the message payloads of received AS2 messages. After the payloads have been downloaded, the message will be marked as received, and the message identifier of the message will no longer be retrieved by the AS2 receiver list service.

.. image:: /_static/images/web_service/h2o-ws-recv.png

.. _as2-2-0-receiver-soap:

SOAP
````

Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/receiver.`

**Request message**

The elements in the SOAP body the namespace URI ``http://service.as2.edi.cecid.hku.hk/`` and namespace prefix ``tns``.

A sample SOAP request is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <tns:messageId xmlns:tns="http://service.as2.edi.cecid.hku.hk/">[id_of_message_to_download]</tns:messageId>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>

**Response message**

The element inside the SOAP body is using namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP response is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <hasMessage xmlns="http://service.as2.edi.cecid.hku.hk/">[true_if_payload_in_message]</hasMessage>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>
   .<!-- Attached payloads... -->

If a payload is associated with the message identifier, then ``<hasMessage>`` will have the value ``true``.
If the received AS2 message has payloads, the response message will have one or more SOAP attachments. Each SOAP attachment has a content type, which is set by the sender application. 

.. _as2-2-0-receiver-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh

    $ curl -X POST --data '{"id":"<message_id"}' http://<HOST>:<PORT>/corvus/api/message/receive/as2

**Response message**

.. code-block:: json

    {  
        "id": "<id>",  
        "as2_from": "<as2_from>",  
        "as2_to": "<as2_to>",
        "timestamp": 1234567890,
        "status": "<status>",
        "payloads": [ 
            {
                "payload": "<payload>"
            } 
        ] 
    }

For the details specification of this REST API, please refer to `HERMES RESTful OpenAPI Specification <https://app.swaggerhub.com/apis/cecid-dev/Hermes2/1.0.0>`_.

.. _as2-2-0-get-status-ws:

Get message status
------------------

This web service is used by the application of the sending party to retrieve the message status of a sent or received AS2 message respectively.

.. _as2-2-0-get-status-soap:

SOAP
````

Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/status.`

**Request message**

The elements in the SOAP body use the namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP request is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <tns:messageId xmlns:tns="http://service.as2.edi.cecid.hku.hk/">[id_of_message_to_download]</tns:messageId>
        </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>

**Response message**

The element ``<messageInfo>`` inside the SOAP body is using the namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP response is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <messageInfo xmlns="http://service.as2.edi.cecid.hku.hk/">
                <status>[status]</status>
                <statusDescription>[statusDescription]</statusDescription>
                <mdnMessageId>[mdnMessageId]</mdnMessageId>
                <mdnStatus>[mdnStatus]</mdnStatus>
                <mdnStatusDescription>[mdnStatusDescription]</mdnStatusDescription>
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

.. _as2-2-0-get-status-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh

    $ curl -X GET http://<HOST>:<PORT>/corvus/api/message/send/as2?id=<message_id>
   
**Response message**
      
.. code-block:: json

    {
        "message_id": "<message_id>", 
        "status": "<status>"
    }

For the details specification of this REST API, please refer to `HERMES RESTful OpenAPI Specification <https://app.swaggerhub.com/apis/cecid-dev/Hermes2/1.0.0>`_.

.. _as2-2-0-query-message-ws:

Query message with parameters
-----------------------------

This web service is used by the application of the sending or receiving party to query messages according to specific parameters.

.. image:: /_static/images/web_service/MessageHistory.png

.. _as-2-0-query-message-soap:

SOAP
````

Service endpoint: :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/msg_history`

**Request message**

The elements in the SOAP body use the namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP request is shown below:

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

**Response message**

The element ``<messageList>`` in the SOAP body use the namespace URI ``http://service.as2.edi.cecid.hku.hk/``.

A sample SOAP response is shown below:

.. code-block:: xml

    <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
        <SOAP-ENV:Header/>
        <SOAP-ENV:Body>
            <messageList xmlns="http://service.as2.edi.cecid.hku.hk/">
                <messageElement>
                    <messageId>[message_id]</messageId>
                    <messageBox>[message_box_containing_this_message] </messageBox>
                </messageElement>
                <messageElement>
                    <messageId>[message_id]</messageId>
                    <messageBox>[message_box_containing_this_message]</messageBox>
                </messageElement>
                <messageElement>...</messageElement>
                <messageElement>...</messageElement>
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

.. _as2-2-0-query-message-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh

    $ curl -X GET http://<HOST>:<PORT>/corvus/api/message/history/as2?message_id=<message_id>&message_box=<message_box>&as2_from=<as2_from>&as2_to=<as2_to>&status=<status>&limit=<limit>
   
**Response message**
      
.. code-block:: json

    {
        "message_ids": [
            {
                "id": "<message_Id>",
                "as2_from": "<as2_from>",
                "as2_to": "<as2_to>",
                "message_box": "<message_box>",
                "timestamp": 1234567890,
                "status": "<status>" 
            } 
        ] 
    }

For the details specification of this REST API, please refer to `HERMES RESTful OpenAPI Specification <https://app.swaggerhub.com/apis/cecid-dev/Hermes2/1.0.0>`_.

.. _as2-2-0-add-partnership-ws:

Add partnership
---------------

The AS2 Add Partnership web service is used by the application of the sending and receiving party to create partnership. For further details about AS2 partnership, please refer to :doc:`as2_partnership`.

.. _as2-2-0-add-partnership-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh
    
    $ curl -X POST -- data '{"id":"<partnership_id>", "as2_from":"<as2_from>", "as2_to":"<as2_to>", "disabled":<true/false>, "sync_reply": "string", "subject": <subject>, "recipient_address": <recipient_address>, "hostname_verified": <Yes/No>, "receipt_address": <receipt_address>, "receipt_requested": <Yes/No>, "outbound_sign_required": <Yes/No>, "outbound_encrypt_required": <Yes/No>,\
                             "outbound_compress_required": <Yes/No>, "receipt_sign_required": <Yes/No>, "inbound_sign_required": <Yes/No>, "inbound_encrypt_required": <Yes/No>, "retries": <no_of_retries>, "retry_interval": <retry_interval>, "sign_algorithm": <sha1/md5>, "encrypt_algorithm": <3des/rc2>, "mic_algorithm": <sha1/md5>, "encrypt_certicate": <cert_path>, "verify_certicate": <cert_path> }' \
      http://<SENDER_HOST>:<SENDER_PORT>/corvus/api/partnership/as2

**Response message**
      
.. code-block:: json

    {
        "id": "<partnership_id>"
    }

.. _as2-2-0-delete-partnership-ws:

Delete partnership
------------------

The AS2 delete Partnership web service is used by the application of the sending and receiving party to delete partnership.

.. _as2-2-0-delete-partnership-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh
    
    $ curl -X DELETE http://<HOST>:<PORT>/corvus/api/partnership/as2/<partnership_id>

**Response message**

.. code-block:: json

    {
        "id": "<partnership_id>",
        "success": true
    }

.. _as2-2-0-update-partnership-ws:

Update partnership
------------------

The ebMS update Partnership web service is used by the application of the sending and receiving party to update partnership. For further details about AS2 partnership, please refer to :doc:`as2_partnership`.

.. _as2-2-0-update-partnership-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh
    
    $ curl -X POST -- data '{"id":"<partnership_id>", "as2_from":"<as2_from>", "as2_to":"<as2_to>", "disabled":<true/false>, "sync_reply": "string", "subject": <subject>, "recipient_address": <recipient_address>, "hostname_verified": <Yes/No>, "receipt_address": <receipt_address>, "receipt_requested": <Yes/No>, "outbound_sign_required": <Yes/No>, "outbound_encrypt_required": <Yes/No>,\
                             "outbound_compress_required": <Yes/No>, "receipt_sign_required": <Yes/No>, "inbound_sign_required": <Yes/No>, "inbound_encrypt_required": <Yes/No>, "retries": <no_of_retries>, "retry_interval": <retry_interval>, "sign_algorithm": <sha1/md5>, "encrypt_algorithm": <3des/rc2>, "mic_algorithm": <sha1/md5>, "encrypt_certicate": <cert_path>, "verify_certicate": <cert_path> }' \
      http://<SENDER_HOST>:<SENDER_PORT>/corvus/api/partnership/as2

**Response message**
      
.. code-block:: json

    {
        "id": "<partnership_id>"
    }


.. _as2-2-0-get-partnership-ws:

Get partnerships
----------------

The AS2 get Partnership web service is used by the application of the sending and receiving party to get all partnership details.

.. _as2-2-0-get-partnerships-rest:

REST [1]_
``````````

**Request message**

.. code-block:: sh
    
    $ curl -X GET http://<HOST>:<PORT>/corvus/api/partnership/as2

**Response message**

.. code-block:: json

    {
        "partnerships": [
            {
                "id": "<partnership_id>",
                "as2_from": "<as2_from>",
                "as2_to": "<as2_to>",
                "disabled": true,
                "sync_reply": "<sync_reply>",
                "subject": "<subject>",
                "recipient_address": "<recipient_address>",
                "hostname_verified": "<yes_or_no>",
                "receipt_address": "<receipt_address>",
                "receipt_requested": "<yes_or_no>",
                "outbound_sign_required": "<yes_or_no>",
                "outbound_encrypt_required": "<yes_or_no>",
                "outbound_compress_required": "<yes_or_no>",
                "receipt_sign_required": "<yes_or_no>",
                "inbound_sign_required": "<yes_or_no>",
                "inbound_encrypt_required": "<yes_or_no>",
                "retries": 2,
                "retry_interval": 10,
                "sign_algorithm": "<sha1_or_md5>",
                "encrypt_algorithm": "<3des_or_rc2>",
                "mic_algorithm": "<sha1_or_md5>",
                "encrypt_certicate": "<cert_path>",
                "verify_certicate": "<cert_path>"
            } 
        ] 
    }

.. [1]
.. note:: 
   * To make an REST API request, the simplest way is to use ``curl`` as a command line REST client, or Postman as a GUI based client is a useful tool too. 
   * To enhance the security of Hermes REST API, HTTP Basic Authenication is enabled for the Rest API. Please place the base64 encoded username:password in the HTTP Header as below :

     :samp:`HTTP Header:Authorization` = :samp:`basic base64encode[username:pwd]` 
     
     where the username and password are defined in :file:`tomcat-users.xml`

See also
--------
* :doc:`first_step`
* :doc:`ebms_partnership`
* :doc:`as2_partnership`
* `HERMES RESTful OpenAPI Specification <https://app.swaggerhub.com/apis/cecid-dev/Hermes2/1.0.0>`_