.. java:import:: java.util Date

.. java:import:: java.util Map

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data Data

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data SFRMStatusQueryData

.. java:import:: hk.hku.cecid.corvus.ws.data SFRMStatusQueryResponseData

SFRMStatusQuerySender
=====================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class SFRMStatusQuerySender extends SOAPSender

   The \ ``SFRMStatusQuerySender``\  is a client sender sending SOAP web services request to Corvus \ ``SFRM``\  plugin for query the status of particular message. The web service parameters are defined in the below:

   .. parsed-literal::

      <messageId> 20070418-124233-75006@147.8.177.42 </messageId>

   Creation Date: 02/05/2007

   :author: Twinsen Tsang

Constructors
------------
SFRMStatusQuerySender
^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SFRMStatusQuerySender(FileLogger l, SFRMStatusQueryData data)
   :outertype: SFRMStatusQuerySender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param data: The SFRM Status query parameter.

Methods
-------
getLastResponseData
^^^^^^^^^^^^^^^^^^^

.. java:method:: public SFRMStatusQueryResponseData getLastResponseData()
   :outertype: SFRMStatusQuerySender

   :return: The SFRM status response data by the last SFRM status query SOAP Call.

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: SFRMStatusQuerySender

   The SOAPRequest in the creation stage should be liked this.

   :throws Exceptions:

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: SFRMStatusQuerySender

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: SFRMStatusQuerySender

   Get the SOAP Body and analyze the result of configuration.

   The result of SOAP body:

   .. parsed-literal::

      <messageInfo>
              <status> The current status of message </status>
          <statusDescription> The current status description of message </statusDescription>
          <numberOfSegments> Maximum number of segments </numberOfSegments>
          <numberOfProcessedSegments> Number of processed segments </numberOfProcessedSegments>
          <lastUpdatedTime>  The last updated timestamp  </lastUpdatedTime>
      </messageInfo>

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: SFRMStatusQuerySender

   [@EVENT] The method \ ``onStart``\  log all new configuration.

