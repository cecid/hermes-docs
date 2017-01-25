.. java:import:: java.io File

.. java:import:: java.io FileOutputStream

.. java:import:: java.io InputStreamReader

.. java:import:: java.io BufferedReader

.. java:import:: java.util Date

.. java:import:: java.util List

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSMessageData

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSPartnershipData

.. java:import:: hk.hku.cecid.corvus.ws.data Payload

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.commons.io NIOHandler

EBMSReceiverSender
==================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class EBMSReceiverSender extends EBMSMessageSender

   The \ ``EBMSReceiverSender``\  is a client sender sending SOAP web services request to B2BCollector \ ``EbMS``\  plugin for downloading the EbMS message and it's corresponding payload.

   :author: Twinsen Tsang

Constructors
------------
EBMSReceiverSender
^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EBMSReceiverSender(FileLogger l, EBMSMessageData m, EBMSPartnershipData ps) throws MessageSenderException
   :outertype: EBMSReceiverSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param m: The message data for party information and send/recv configuration.
   :param ps: The partnership data.

Methods
-------
getMessageIdToRetreive
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getMessageIdToRetreive()
   :outertype: EBMSReceiverSender

   :return: the message id to retreive.

getOutputDirectory
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getOutputDirectory()
   :outertype: EBMSReceiverSender

   :return: the output directory of the received payload.

getResponseMessageId
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getResponseMessageId()
   :outertype: EBMSReceiverSender

   :throws Operation: does not support.

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: EBMSReceiverSender

   Initialize the message using the properties in the MessageProps.

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: EBMSReceiverSender

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: EBMSReceiverSender

   Retrieve the payload from the message. The default receiver stores the payload as a files at the particular place specified in the configuration.

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: EBMSReceiverSender

   Initialize the SOAP Message.

setMessageIdToRetreive
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setMessageIdToRetreive(String messageId)
   :outertype: EBMSReceiverSender

   :param messageId: the message id to retreive the payload / message.

setOutputDirectory
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setOutputDirectory(String path)
   :outertype: EBMSReceiverSender

   Set the output directory of received payload if any.

