.. java:import:: java.util Date

.. java:import:: java.util List

.. java:import:: java.util ArrayList

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data AS2MessageData

.. java:import:: hk.hku.cecid.corvus.ws.data AS2PartnershipData

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

AS2ReceiverListSender
=====================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class AS2ReceiverListSender extends MessageSender

   The \ ``AS2ReceiverListSender``\  is a client sender sending SOAP web services request to B2BCollector \ ``AS2``\  plugin for query whether if there is any message that are available. The web service parameters are defined in the below:

   .. parsed-literal::

      <part name="as2From" type="s:string" />
      <part name="as2To" type="s:string" />
      <part name="numOfMessages" type="s:int" />

   :author: Twinsen Tsang

Constructors
------------
AS2ReceiverListSender
^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AS2ReceiverListSender(FileLogger l, AS2MessageData m, AS2PartnershipData p)
   :outertype: AS2ReceiverListSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param m: The message data for party information and send/recv configuration.
   :param p: The partnership data.

Methods
-------
getAvailableMessages
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List getAvailableMessages()
   :outertype: AS2ReceiverListSender

   This method should be called after the event \ :java:ref:`onResponse()`\

   :return: a list of message id that are ready to download.

getNumOfMessageToRetrieve
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int getNumOfMessageToRetrieve()
   :outertype: AS2ReceiverListSender

   :return: number of message to retrieve for one soap call.

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: AS2ReceiverListSender

   Initialize the message using the properties in the MessageProps.

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: AS2ReceiverListSender

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: AS2ReceiverListSender

   [@EVENT] Record all the AS2 message that ready to download. Developer should invocate \ :java:ref:`getAvailableMessages()`\  to get a list of all ready AS2 message.

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: AS2ReceiverListSender

   Initialize the SOAP Message.

setNumOfMessageToRetrieve
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setNumOfMessageToRetrieve(int numMsgs)
   :outertype: AS2ReceiverListSender

   Set number of message to retrieve for one soap call.

   :param numMsgs: number of message to retrieve for one soap call.

