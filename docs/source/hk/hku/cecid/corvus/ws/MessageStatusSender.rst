.. java:import:: java.util Date

.. java:import:: java.util ArrayList

.. java:import:: java.util Map

.. java:import:: java.util HashMap

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data MessageStatusRequestData

.. java:import:: hk.hku.cecid.corvus.ws.data MessageStatusResponseData

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

MessageStatusSender
===================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class MessageStatusSender extends SOAPSender

   The \ ``MessageStatusSender``\  is the SOAP Message client that query the message status record through the\ *Message status engine (MS-E)*\ .  From the description in (MS-E), a series of parameters have been defined and required to send to the MS-E.

   ..

   #. partnershipId
   #. channelType (OUTGOING | INCOMING)
   #. channelId
   #. folderName
   #. fileName
   #. fromTimestamp (in UTC format)
   #. toTimestamp (in UTC format)
   #. numOfRecords
   #. conversationId
   #. messageId
   #. messageType
   #. messageStatus
   #. protocol
   #. locale (EN)
   #. levelOfDetails (0 | 1)
   #. offset

   Creation Date: 12/03/2007

   :author: Twinsen Tsang

Fields
------
MSE_REQUEST_TYPE
^^^^^^^^^^^^^^^^

.. java:field:: public static final String MSE_REQUEST_TYPE
   :outertype: MessageStatusSender

   The complex type object for the message status request.

MSE_RESPONSE_TYPE
^^^^^^^^^^^^^^^^^

.. java:field:: public static final String MSE_RESPONSE_TYPE
   :outertype: MessageStatusSender

   The complex type object for the message response request.

Constructors
------------
MessageStatusSender
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public MessageStatusSender(FileLogger l, MessageStatusRequestData m)
   :outertype: MessageStatusSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param m: The message status properties including the querying parameter.

Methods
-------
getMessageStatusList
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public ArrayList getMessageStatusList()
   :outertype: MessageStatusSender

   [@GET] Get the list of message status record. It should be called only after the invocation of \ :java:ref:`onResponse()`\ .

   :return: a list of message status record using the filter from the last web services call query.

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: MessageStatusSender

   Initialize the message using the properties in the \ ``MessageStatusRequestData``\ .

   :throws ClassCastException: the properties set is not a message status request data.

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: MessageStatusSender

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: MessageStatusSender

   [@EVENT] Retrieve the message status record from the message soap message.  It parse the response and transform each \ ``MessageInfo``\  complex type into one \ ``MessageStatusResponseData``\ .

   :throws Exception:

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: MessageStatusSender

   Initialize the SOAP Message.

