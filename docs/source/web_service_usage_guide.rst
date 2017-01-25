Web Service Usage Guide
=======================

Maintaining partnerships
------------------------

A partnership must be registered on Hermes 2 to send messages since partnerships contain information about your trading partner. A separate partnership is required to receive messages.

If you would like more information, please refer to the articles :ref:`what-is-an-ebms-2-0-partnership` and :ref:`what-is-an-as2-partnership`.

Let's take a look at the program parameters.

:samp:`as2-partnership [partnership-xml] [config-xml] [log-path]`

+-----------------+-----------------------------------------------------------------------------+
| partnership-xml | The filepath of the partnership configuration file.                         |
|                 |                                                                             |
|                 | Default is :file:`{<HERMES2_HOME>}/config/as2-partnership.xml`.             |
+-----------------+-----------------------------------------------------------------------------+
| config-xml      | The filepath of the message configuration file.                             |
|                 |                                                                             |
|                 | Default is :file:`{<HERMES2_HOME>}/config/as2-partnership/as2-request.xml`. |
+-----------------+-----------------------------------------------------------------------------+
| log-path        | The filepath of the logger to log query result or error.                    |
|                 |                                                                             |
|                 | Default is :file:`{<HERMES2_HOME>}/logs/as2-partnership.log`.               |
+-----------------+-----------------------------------------------------------------------------+

:samp:`ebms-partnership [partnership-xml] [config-xml] [log-path]`

+-----------------+-------------------------------------------------------------------------------+
| partnership-xml | The filepath of the partnership configuration file.                           |
|                 |                                                                               |
|                 | Default is :file:`{<HERMES2_HOME>}/config/ebms-partnership.xml`.              |
+-----------------+-------------------------------------------------------------------------------+
| config-xml      | The filepath of the message configuration file.                               |
|                 |                                                                               |
|                 | Default is :file:`{<HERMES2_HOME>}/config/ebms-partnership/ebms-request.xml`. |
+-----------------+-------------------------------------------------------------------------------+
| log-path        | The filepath of the logger to log query result or error.                      |
|                 |                                                                               |
|                 | Default is :file:`{<HERMES2_HOME>}/logs/ebms-partnership.log`.                |
+-----------------+-------------------------------------------------------------------------------+

config-xml
^^^^^^^^^^

Here is sample content of the config-xml files. These files are named :file:`ebms-request.xml` and :file:`as2-request.xml`, and placed under :file:`{<HERMES2_HOME>}/config/ebms-partnership` and :file:`{<HERMES2_HOME>}/config/as2-partnership` respectively. 

**Configuration file for ebMS:**

.. image:: /_static/images/web_service/ebms-partnership-request.png

**Configuration file for AS2:**

.. image:: /_static/images/web_service/as2-partnership-request.png


partnership-xml
^^^^^^^^^^^^^^^

Sample content of the partnership-xml files are shown below. For more details, please refer to the articles :doc:`ebms_partnership` and :doc:`as2_partnership`. 

**Sample ebMS partnership:**

.. image:: /_static/images/web_service/ebms-partnership-xml.png

**Sample AS2 partnership:**

.. image:: /_static/images/web_service/as2-partnership-xml.png

ebMS
----

We have created two sample programs, :program:`ebms-send` and :program:`ebms-history`, to demonstrate how to communicate with Hermes 2 web services.

Sending an ebMS message
^^^^^^^^^^^^^^^^^^^^^^^

:program:`ebms-send` is a sample program to demonstrate how to upload an ebMS message to Hermes 2 using the sender web service in the ebMS plugin. You can pack your payload as a SOAP message and send it to this service at the endpoint :samp:`http://{<HOST>}:<PORT>/corvus/httpd/ebms/sender`.

The elements in a SOAP request are shown below:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:cpaId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [CPA_id] </tns:cpaId>
   <tns:service xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Service] </tns:service>
   <tns:action xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Action] </tns:action>
   <tns:convId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Conversation_Id] </tns:convId>
   <tns:fromPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [From_Party_ID] </tns:fromPartyId>
   <tns:fromPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [From_Party_Type] </tns:fromPartyType>
   <tns:toPartyId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [To_Party_ID] </tns:toPartyId>
   <tns:toPartyType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [To_Party_Type] </tns:toPartyType>
   <tns:refToMessageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Reference_Message_Id] </refToMessageId>
   <tns:serviceType xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> [Service_Type] </tns:serviceType>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

For more information on the elements in the SOAP body of a send request, please refer to :ref:`ebms-2-0-sender-web-service`.

Before sending an ebMS message, make sure that a partnership is registered. Please refer to the section `Maintaining Partnerships`_ for more information.

Let’s take a look at the program parameters.

:samp:`ebms-send [partnership-xml] [config-xml] [log-path] [payload-path]`

+--------------------+------------------------------------------------------------------------+
| partnership-xml    | The filepath of the partnership configuration file.                    |
|                    |                                                                        |
|                    | Default is :file:`{<HERMES2_HOME>}/config/ebms-partnership.xml`.       |
+--------------------+------------------------------------------------------------------------+
| config-xml         | The filepath of the message configuration file.                        |
|                    |                                                                        |
|                    | Default is :file:`{<HERMES2_HOME>}/config/ebms-send/ebms-request.xml`. |
+--------------------+------------------------------------------------------------------------+
| log-path           | The filepath of the logger to log query result or error.               |
|                    |                                                                        |
|                    | Default is :file:`{<HERMES2_HOME>}/logs/ebms-send.log`.                |
+--------------------+------------------------------------------------------------------------+
| payload (optional) | The filepath of the payload attached in the message.                   |
|                    |                                                                        |
|                    | Default is :file:`{<HERMES2_HOME>}/config/ebms-send/testpayload`.      |
+--------------------+------------------------------------------------------------------------+

config-xml
""""""""""

Here is sample content of the config-xml file. This file is named :file:`ebms-request.xml`, and placed under :file:`{<HERMES2_HOME>}/config/ebms-send`.

.. image:: /_static/images/web_service/ebms-send-request.png

The following table explains the use of each element:

+----------------------+--------------------------------------------------------------------------+
| ``<sendEndpoint>``   | Refers to the address of the ebMS send service.                          |
|                      |                                                                          |
|                      | It should be :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/sender`   |
+----------------------+--------------------------------------------------------------------------+
| ``<conversationId>`` | Identifies which conversation this message belongs to.                   |
|                      |                                                                          |
|                      | **This is required for Hermes 2 to create a valid message.**             |
+----------------------+--------------------------------------------------------------------------+
| ``<fromPartyId>``    | Identifies the sender and receiver.                                      |
|                      |                                                                          |
| ``<fromPartyType>``  | **These are required for Hermes 2 to retrieve the message destination.** |
|                      |                                                                          |
| ``<toPartyId>``      |                                                                          |
|                      |                                                                          |
| ``<toPartyType>``    |                                                                          |
+----------------------+--------------------------------------------------------------------------+
| ``<refToMessageId>`` | The message id that is targeted to respond to.                           |
+----------------------+--------------------------------------------------------------------------+
| ``<serviceType>``    | A type identifier for the ebXML service defined in the partnership.      |
+----------------------+--------------------------------------------------------------------------+

You only need to change ``<sendEndpoint>`` to contain the correct address.

partnership-xml
"""""""""""""""

Another configuration file needed is partnership-xml, which is named :file:`ebms-partnership.xml` and placed under :file:`{<HERMES2_HOME>}/config` by default.

Sample content is shown below:

.. image:: /_static/images/web_service/ebms-partnership-xml.png

The mandatory elements are necessary to construct a SOAP message according to the WSDL. For more information, please read the article :doc:`ebms_partnership`.

Once you have configured these parameters correctly, the program can be executed. A message id will be displayed if the program has successfully executed.

Here is sample output from the program:

.. image:: /_static/images/web_service/ebms-send-screen.png

ebMS history query
^^^^^^^^^^^^^^^^^^

:program:`ebms-history` demonstrates the use of the message history web service (:program:`msg-history`) in the ebMS plugin. There are several criteria defined for message history queries. By passing these criteria to Hermes 2 through SOAP messages, the target results can be retrieved.

The message history service endpoint is :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/msg_history`.

The required elements in a SOAP request are as follows:

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

Let’s take a look at the program parameters.


:samp:`ebms-history [config-xml] [log-path]`

+------------+------------------------------------------------------------+
| config-xml | The filepath of the message configuration file.            |
|            |                                                            |
|            | Default is :file:`./config/ebms-history/ebms-request.xml`. |
+------------+------------------------------------------------------------+
| log-path   | The filepath of the logger to log query result or error.   |
|            |                                                            |
|            | Default is :file:`./logs/ebms-history.log`.                |
+------------+------------------------------------------------------------+
 
config-xml
""""""""""

Here is sample content of the config-xml. This config-xml is named :file:`ebms-request.xml,` and placed under :file:`{<HERMES2_HOME>}/config/ebms-history.` There are several elements listed as search criteria. You can use the wildcard ``%`` in the values, and you can comment out unwanted elements.
   
.. image:: /_static/images/web_service/ebms-history-request.png

Program operation
^^^^^^^^^^^^^^^^^

If the query has successfully executed, the result will be similar to the following: 

.. image:: /_static/images/web_service/ebms-history-screen1.png

After the messages are displayed by the program, you can perform further action by choosing your target message. If the message is placed under **OUTBOX**, the program will query its current status. If the message is placed under **INBOX**, the program will download the payload(s) if available.

Retrieving message payloads
^^^^^^^^^^^^^^^^^^^^^^^^^^^

There is a receiver web service provided by the ebMS plugin to retrieve messages. The receiver service endpoint is :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/ebms/receiver`.

The required elements in a SOAP request are the following:


.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <MessageId></tns:messageId>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

The message id is the only criteria needed to retrieve the payload of the target message. However, the payload is only available once. If the payload of a message has already been downloaded, the program will not be able to retrieve it again.

The program will ask for a directory to store the payload, which will be stored with the name :file:`ebms.{<MessageId>}.Payload.{<IndexofPayload>}`.

.. image:: /_static/images/web_service/ebms-history-screen2-in.png

Check outgoing message status
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To check the status of outgoing messages, the program uses the status web service provided in the ebMS plugin. This service cannot check the status of incoming messages.

The required elements in a SOAP request are the following:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/"> <MessageId></tns:messageId>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

The program lists the message status along with a simple description:

.. image:: /_static/images/web_service/ebms-history-screen2-out.png

AS2
---

We created similar sample programs for AS2 as well. The programs :program:`as2-send` and :program:`as2-history` are used to demonstrate how to communicate with Hermes 2 web services through AS2 SOAP messages.


Sending an AS2 message
^^^^^^^^^^^^^^^^^^^^^^

:program:`as2-send` is a sample program to demonstrate how to upload a message to Hermes 2 using the sender web service in the AS2 plugin. You can pack your payload as a SOAP message and send it to this service with the endpoint :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/sender`.

The required elements in a SOAP request are shown below:

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

``<as2_from>`` and ``<as2_to>`` contain the partnership information and ``<type>`` contains the content type of the payload.

Before sending an AS2 message, check that a partnership is registered. Please refer to the section `Maintaining Partnerships`_ for more information.

Let’s take a look at the program parameters.

:samp:`as2-send [partnership-xml] [config-xml] [log-path] [payload-path]`.

+--------------------+----------------------------------------------------------------------+
| partnership-xml    | The filepath of the partnership configuration file.                  |
|                    |                                                                      |
|                    | Default is :file:`{<HERMES2_HOME>}/config/as2-partnership.xml`.      |
+--------------------+----------------------------------------------------------------------+
| config-xml         | The filepath of the message configuration file.                      |
|                    |                                                                      |
|                    | Default is :file:`{<HERMES2_HOME>}/config/as2-send/as2-request.xml`. |
+--------------------+----------------------------------------------------------------------+
| log-path           | The filepath of the logger to log query result or error.             |
|                    |                                                                      |
|                    | Default is :file:`{<HERMES2_HOME>}/logs/as2-send.log`.               |
+--------------------+----------------------------------------------------------------------+
| payload (optional) | The filepath of the payload attached in the message.                 |
|                    |                                                                      |
|                    | Default is :file:`{<HERMES2_HOME>}/config/as2-send/testpayload`.     |
+--------------------+----------------------------------------------------------------------+

config-xml
""""""""""

Below is sample content of the config-xml file. This file is named :file:`as2-request.xml`, and placed under :file:`{<HERMES2_HOME>}/config/as2-send`. 

.. image:: /_static/images/web_service/as2-send-request.png

The elements are explained in the table below:

+------------------------+-----------------------------------------------------------------------------------------+
| ``<sendEndpoint>`` | Refers to the address of the AS2 sender web service.                                    |
|                        |                                                                                         |
|                        | It should be :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/sender`.                  |
+------------------------+-----------------------------------------------------------------------------------------+
| ``<type>``         | Specify the content type. For more information, please refer to AS2 Sender Web Service. |
|                        |                                                                                         |
|                        | Only ``<sendEndpoint>`` has to be changed to contain the correct address.           |
+------------------------+-----------------------------------------------------------------------------------------+

partnership-xml
"""""""""""""""

Another configuration file is the partnership-xml, which is named :file:`as2-partnership.xml` and placed under :file:`<HERMES2_HOME>/config` folder by default.

Sample content is shown below:

.. image:: /_static/images/web_service/as2-partnership-xml.png

``<as2From>`` and ``<as2To>`` are required to construct a SOAP message according to the WSDL. For more information, please refer to AS2 Partnership.

Once you have configured these parameters, you can execute the program. A message id will be returned if the program has been successfully executed. Below is sample output from the program.

.. image:: /_static/images/web_service/as2-send-screen.png

AS2 history query
^^^^^^^^^^^^^^^^^

:program:`as2-history` is a demo program that utilizes the message history web service in the AS2 plugin. The web service is called :program:`msg-history`. There are several criteria defined for message history queries. By passing these criteria to Hermes 2 through SOAP messages, you can retrieve your target messages.

The message history web service endpoint is :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/msg_history`.

The required elements in a SOAP request are shown below:


.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageBox xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Message_Box]</tns:messageBox>
   <tns:status xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Message_Status]</tns:status>
   <tns:messageId xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[Message_Id]</tns:messageId>
   <tns:as2From xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[AS2_From_Party]</tns:as2From>
   <tns:as2To xmlns:tns="http://service.ebms.edi.cecid.hku.hk/">[AS2_To_Party]</tns:as2To>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

Using this service, you can search for messages using message properties as well as partnership information.

Let’s take a look at the program parameters.

:samp:`as2-history [config-xml] [log-path]`

+------------+-------------------------------------------------------------------------+
| config-xml | The filepath of the message configuration file.                         |
|            |                                                                         |
|            | Default is :file:`{<HERMES2_HOME>}/config/as2-history/as2-request.xml`. |
+------------+-------------------------------------------------------------------------+
| log-path   | The filepath of the logger to log query result or error.                |
|            |                                                                         |
|            | Default is :file:`{<HERMES2_HOME>}/logs/as2-history.log`.               |
+------------+-------------------------------------------------------------------------+

config-xml
""""""""""

Below is sample content of the config-xml file. This file is named :file:`as2-request.xml`, and placed under :file:`{<HERMES2_HOME>}/config/as2-history`. There are several elements available to use as searching criteria. You can use the wildcard character ``%`` in the values and comment out unwanted elements.

.. image:: /_static/images/web_service/as2-history-request.png

Program operation
^^^^^^^^^^^^^^^^^

If the query has been executed successfully, the result will be similar to following: 

.. image:: /_static/images/web_service/as2-history-screen1.png

Messages are listed in ascending order according to the timestamp of the message (i.e. the earliest message will be listed with index 0). After the results are listed, you can choose your target message. If the message is placed under **OUTBOX**, the program will query its current status. If the message is placed under **INBOX**, the program will download the payload if available.


Retrieve message payload
^^^^^^^^^^^^^^^^^^^^^^^^

There is a receiver service provided by the AS2 plugin for retrieving messages. The receiver service endpoint is :samp:`http://{<HOST>}:{<PORT>}/corvus/httpd/as2/receiver`.

The required elements in a SOAP request are the following:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageId xmlns:tns="http://service.as2.edi.cecid.hku.hk/"> [Message_Id]</tns:messageId>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>

You can input the id of your target message in the SOAP message to retrieve its payload. However, the payload is only available once. If the payload has already been downloaded, the program will not be able to retrieve it again.

.. image:: /_static/images/web_service/as2-history-screen2-in.png

As shown above, the program will ask for a directory to store the payload(s). Each payload will be stored with the name :file:`as2.{<MessageId>}.Payload.{<IndexofPayload>}`.

Check outgoing message status
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To check the status of outgoing messages, the program uses the status web service provided in the AS2 plugin. This service cannot check the status of incoming messages.

The required elements in a SOAP request are the following:

.. code-block:: xml

   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
   <tns:messageId xmlns:tns="http://service.as2.edi.cecid.hku.hk/"> [Message_ID]</tns:messageId>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>



Here is sample output from the program: 

.. image:: /_static/images/web_service/as2-history-screen2-out.png

The program will display the message status along with a simple description.

Reference articles
------------------

* :doc:`first_step`
* :doc:`ebms_partnership`
* :doc:`as2_partnership`
* :doc:`web_service_communication`
