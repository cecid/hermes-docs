.. java:import:: java.io File

.. java:import:: java.io FileOutputStream

.. java:import:: java.util Date

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSMessageData

.. java:import:: hk.hku.cecid.corvus.ws.data Payload

.. java:import:: hk.hku.cecid.piazza.commons.io NIOHandler

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

EBMSMessageReceiver
===================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class EBMSMessageReceiver extends MessageReceiver

   The \ ``EBMSMessageReceiver``\  is a client sender sending SOAP web services request to B2BCollector \ ``EbMS``\  plugin for retrieving a ebMS message according to provided message id. The web service parameters are defined in the below:

   .. parsed-literal::

      <part name="messageId" type="s:string" /> *

   :author: Jumbo Cheung

   **See also:** :java:ref:`hk.hku.cecid.corvus.ws.data.EBMSMessageData`

Constructors
------------
EBMSMessageReceiver
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EBMSMessageReceiver(FileLogger l, EBMSMessageData m)
   :outertype: EBMSMessageReceiver

Methods
-------
getOutputDirectory
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getOutputDirectory()
   :outertype: EBMSMessageReceiver

   :return: the output directory of the received payload.

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: EBMSMessageReceiver

   Initialize the message using the properties in the MessageProps.

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: EBMSMessageReceiver

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: EBMSMessageReceiver

   Retrieve the payload from the message. The default receiver stores the payload as a files at the particular place specified in the configuration.

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: EBMSMessageReceiver

   Initialize the SOAP Message.

setOutputDirectory
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setOutputDirectory(String path)
   :outertype: EBMSMessageReceiver

   Set the output directory of received payload if any.

