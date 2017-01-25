.. java:import:: java.io File

.. java:import:: java.io FileOutputStream

.. java:import:: java.io InputStreamReader

.. java:import:: java.io BufferedReader

.. java:import:: java.util Date

.. java:import:: java.util List

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data AS2MessageData

.. java:import:: hk.hku.cecid.corvus.ws.data AS2PartnershipData

.. java:import:: hk.hku.cecid.corvus.ws.data Payload

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.commons.io NIOHandler

AS2ReceiverSender
=================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class AS2ReceiverSender extends AS2MessageSender

   The \ ``AS2ReceiverSender``\  is a client sender sending SOAP web services request to Hermes Messaging Gateway \ ``AS2``\  plugin for down-loading the AS2 message and it's corresponding payload.

   :author: Twinsen Tsang

Constructors
------------
AS2ReceiverSender
^^^^^^^^^^^^^^^^^

.. java:constructor:: public AS2ReceiverSender(FileLogger l, AS2MessageData m, AS2PartnershipData ps) throws MessageSenderException
   :outertype: AS2ReceiverSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param m: The message data for party information and send/recv configuration.
   :param ps: The partnership data.

Methods
-------
getMessageIdToRetreive
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getMessageIdToRetreive()
   :outertype: AS2ReceiverSender

   :return: the message id to retreive.

getOutputDirectory
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getOutputDirectory()
   :outertype: AS2ReceiverSender

   :return: the output directory of the received payload.

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: AS2ReceiverSender

   Initialize the message using the properties in the MessageProps.

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: AS2ReceiverSender

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: AS2ReceiverSender

   Retrieve the payload from the message. The default receiver stores the payload as a files at the particular place specified in the configuration.

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: AS2ReceiverSender

   Initialize the SOAP Message.

setMessageIdToRetreive
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setMessageIdToRetreive(String messageId)
   :outertype: AS2ReceiverSender

   :param messageId: the message id to retreive the payload / message.

setOutputDirectory
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setOutputDirectory(String path)
   :outertype: AS2ReceiverSender

   Set the output directory of received payload if any.

