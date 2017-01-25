.. java:import:: java.util Date

.. java:import:: java.util Map

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data Data

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSStatusQueryData

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSStatusQueryResponseData

EBMSStatusQuerySender
=====================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class EBMSStatusQuerySender extends SOAPSender

   The \ ``EBMSStatusQuerySender``\  is a client sender sending SOAP web services request to Corvus \ ``EBMS``\  plugin for query the status of particular message. The web service parameters are defined in the below:

   .. parsed-literal::

      <messageId> 20070418-124233-75006@147.8.177.42 </messageId>

   Creation Date: 02/05/2007

   :author: Twinsen Tsang

Constructors
------------
EBMSStatusQuerySender
^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EBMSStatusQuerySender(FileLogger l, EBMSStatusQueryData data)
   :outertype: EBMSStatusQuerySender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param data: The EBMS Status query parameter.

Methods
-------
getLastResponseData
^^^^^^^^^^^^^^^^^^^

.. java:method:: public EBMSStatusQueryResponseData getLastResponseData()
   :outertype: EBMSStatusQuerySender

   :return: The EBMS status response data by the last SFRM status query SOAP Call.

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: EBMSStatusQuerySender

   The SOAPRequest in the creation stage should be liked this.

   :throws Exceptions:

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: EBMSStatusQuerySender

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: EBMSStatusQuerySender

   Get the SOAP Body and analyze the result of configuration.

   The result of SOAP body:

   .. parsed-literal::

         <status> The current status of message </status>
      <statusDescription> The current status description of message </statusDescription>
      <ackMessageId> The message id of acknowledgment / receipt if any </ackMessageId>
      <ackStatus> The status of acknowledgment / receipt if any </ackStatus>
      <ackStatusDescription> The status description of acknowledgment / receipt if any </ackStatusDescription>

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: EBMSStatusQuerySender

   [@EVENT] The method \ ``onStart``\  log all new configuration.

