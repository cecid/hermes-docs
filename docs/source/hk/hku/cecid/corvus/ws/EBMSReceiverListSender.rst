.. java:import:: java.util Date

.. java:import:: java.util List

.. java:import:: java.util ArrayList

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSMessageData

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSPartnershipData

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

EBMSReceiverListSender
======================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class EBMSReceiverListSender extends MessageSender

   The \ ``EBMSReceiverListSender``\  is a client sender sending SOAP web services request to H2O \ ``EbMS``\  plugin for query whether if there is any message that are available. The web service parameters are defined in the below:

   .. parsed-literal::

      <part name="cpaId" type="s:string" />
      <part name="service" type="s:string" />
      <part name="action" type="s:string" />
      <part name="convId" type="s:string" />
      <part name="fromPartyId" type="s:string" />
      <part name="fromPartyType" type="s:string" />
      <part name="toPartyId" type="s:string" />
      <part name="toPartyType" type="s:string" />
      <part name="numOfMessages" type="s:int" />

   :author: Twinsen Tsang

Constructors
------------
EBMSReceiverListSender
^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EBMSReceiverListSender(FileLogger l, EBMSMessageData m, EBMSPartnershipData p)
   :outertype: EBMSReceiverListSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param m: The message data for party information and send/recv configuration.
   :param p: The partnership data.

Methods
-------
getAvailableMessages
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List getAvailableMessages()
   :outertype: EBMSReceiverListSender

   This method should be called after the event \ :java:ref:`onResponse()`\

   :return: a list of message id that are ready to download.

getNumOfMessageToRetrieve
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int getNumOfMessageToRetrieve()
   :outertype: EBMSReceiverListSender

   :return: number of message to retrieve for one soap call.

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: EBMSReceiverListSender

   Initialize the message using the properties in the MessageProps.

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: EBMSReceiverListSender

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: EBMSReceiverListSender

   [@EVENT] Record all the EbMS message that ready to download. Developer should invocate \ :java:ref:`getAvailableMessages()`\  to get a list of all ready EbMS message.

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: EBMSReceiverListSender

   Initialize the SOAP Message.

setNumOfMessageToRetrieve
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setNumOfMessageToRetrieve(int numMsgs)
   :outertype: EBMSReceiverListSender

   Set number of message to retrieve for one soap call.

   :param numMsgs: number of message to retrieve for one soap call.

