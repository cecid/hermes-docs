.. java:import:: java.io File

.. java:import:: java.util Date

.. java:import:: javax.activation DataHandler

.. java:import:: javax.activation FileDataSource

.. java:import:: javax.xml.soap AttachmentPart

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data AS2MessageData

.. java:import:: hk.hku.cecid.corvus.ws.data AS2PartnershipData

.. java:import:: hk.hku.cecid.corvus.ws.data Payload

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

AS2MessageSender
================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class AS2MessageSender extends MessageSender

   The \ ``AS2MessageSender``\  is a client sender sending SOAP web services request to B2BCollector \ ``AS2``\  plugin for transmission a AS2 message to other parnter. The web service parameters are defined in the below:

   .. parsed-literal::

      <part name="as2_from" type="s:string" />
      <part name="as2_to" type="s:string" />
      <part name="type" type="s:string" />

   :author: Twinsen Tsang

Fields
------
NS_URI
^^^^^^

.. java:field:: protected static final String NS_URI
   :outertype: AS2MessageSender

   The Namespace URI

Constructors
------------
AS2MessageSender
^^^^^^^^^^^^^^^^

.. java:constructor:: public AS2MessageSender(FileLogger l, AS2MessageData m, AS2PartnershipData p) throws MessageSenderException
   :outertype: AS2MessageSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param m: The message data for party information and send/recv configuration.
   :param p: The partnership data.

Methods
-------
addRequestPayload
^^^^^^^^^^^^^^^^^

.. java:method:: @Override public boolean addRequestPayload(Payload[] payloads)
   :outertype: AS2MessageSender

getResponseMessageId
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getResponseMessageId()
   :outertype: AS2MessageSender

   Get the message id of last successful web service query. This should be called only after \ :java:ref:`onResponse()`\

   :return: the message id

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: AS2MessageSender

   Initialize the message using the properties in the MessageProps.

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: AS2MessageSender

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: AS2MessageSender

   Record the message id.

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: AS2MessageSender

   Initialize the SOAP Message.

