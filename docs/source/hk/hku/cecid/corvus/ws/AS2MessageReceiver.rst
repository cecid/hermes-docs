.. java:import:: java.io File

.. java:import:: java.io FileOutputStream

.. java:import:: java.io IOException

.. java:import:: java.util Date

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap AttachmentPart

.. java:import:: javax.xml.soap SOAPException

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data AS2MessageData

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data Payload

.. java:import:: hk.hku.cecid.piazza.commons.io NIOHandler

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

AS2MessageReceiver
==================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class AS2MessageReceiver extends MessageReceiver

Constructors
------------
AS2MessageReceiver
^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AS2MessageReceiver(FileLogger l, AS2MessageData m)
   :outertype: AS2MessageReceiver

Methods
-------
getMessageIdToRetreive
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getMessageIdToRetreive()
   :outertype: AS2MessageReceiver

   :return: the message id to retreive.

getOutputDirectory
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getOutputDirectory()
   :outertype: AS2MessageReceiver

   :return: the output directory of the received payload.

getResponsePayloads
^^^^^^^^^^^^^^^^^^^

.. java:method:: @Override public Payload[] getResponsePayloads() throws SOAPException, IOException
   :outertype: AS2MessageReceiver

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: AS2MessageReceiver

   Initialize the message using the properties in the MessageProps.

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: AS2MessageReceiver

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: AS2MessageReceiver

   Retrieve the payload from the message. The default receiver stores the payload as a files at the particular place specified in the configuration.

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: AS2MessageReceiver

   Initialize the SOAP Message.

setMessageIdToRetreive
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setMessageIdToRetreive(String messageId)
   :outertype: AS2MessageReceiver

   :param messageId: the message id to retreive the payload / message.

setOutputDirectory
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setOutputDirectory(String path)
   :outertype: AS2MessageReceiver

   Set the output directory of received payload if any.

