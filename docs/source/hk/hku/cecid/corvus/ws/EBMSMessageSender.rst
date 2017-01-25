.. java:import:: java.util Date

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSMessageData

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSPartnershipData

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data Payload

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

EBMSMessageSender
=================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class EBMSMessageSender extends MessageSender

   The \ ``EBMSMessageSender``\  is a client sender sending SOAP web services request to B2BCollector \ ``EbMS``\  plugin for transmission a ebMS message to other parnter. The web service parameters are defined in the below:

   .. parsed-literal::

      <part name="cpaId" type="s:string" />
      <part name="service" type="s:string" />
      <part name="action" type="s:string" />
      <part name="convId" type="s:string" />
      <part name="fromPartyId" type="s:string" />
      <part name="fromPartyType" type="s:string" />
      <part name="toPartyId" type="s:string" />
      <part name="toPartyType" type="s:string" />
      <part name="refToMessageId" type="s:string" />
      <part name="serviceType" type="s:string" />

   :author: Twinsen Tsang

   **See also:** :java:ref:`hk.hku.cecid.corvus.ws.data.EBMSMessageData`, :java:ref:`hk.hku.cecid.corvus.ws.data.EBMSPartnershipData`

Fields
------
NS_URI
^^^^^^

.. java:field:: protected static final String NS_URI
   :outertype: EBMSMessageSender

   The Namespace URI

Constructors
------------
EBMSMessageSender
^^^^^^^^^^^^^^^^^

.. java:constructor:: public EBMSMessageSender(FileLogger l, EBMSMessageData m, EBMSPartnershipData p) throws MessageSenderException
   :outertype: EBMSMessageSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param m: The message data for party information and send/recv configuration.
   :param p: The partnership data.

Methods
-------
getResponseMessageId
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getResponseMessageId()
   :outertype: EBMSMessageSender

   Get the message id of last successful web service query. This should be called only after \ :java:ref:`onResponse()`\

   :return: the message id

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: EBMSMessageSender

   Initialize the message using the properties in the MessageProps.

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: EBMSMessageSender

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: EBMSMessageSender

   [@EVENT] Retrieve the id of newly created message from the SOAP message.

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: EBMSMessageSender

   Initialize the SOAP Message.

