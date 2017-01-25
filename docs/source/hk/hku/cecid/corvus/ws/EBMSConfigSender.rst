.. java:import:: java.util Date

.. java:import:: java.util Map

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data Data

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSConfigData

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

EBMSConfigSender
================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class EBMSConfigSender extends SOAPSender

   The \ ``EBMSConfigSender``\  is a client sender sending SOAP web services request to B2BCollector \ ``EBMS``\  plugin for configurating the performance factor. The web service parameters are defined in the below:

   .. parsed-literal::

      <active-module-status> true | false </active-module-status>
      <incollector-interval>15000</incollector-interval>
      <incollector-maxthread>0</incollector-maxthread>
      <outcollector-interval>15000</outcollector-interval>
      <outcollector-maxthread>0</outcollector-maxthread>
      <mailcollector-interval>15000</mailcollector-interval>
      <mailcollector-maxthread>0</mailcollector-maxthread>

   :author: Twinsen Tsang

Constructors
------------
EBMSConfigSender
^^^^^^^^^^^^^^^^

.. java:constructor:: public EBMSConfigSender(FileLogger l, EBMSConfigData data)
   :outertype: EBMSConfigSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param data: The EBMS Configuration parameters.

Methods
-------
getStatus
^^^^^^^^^

.. java:method:: public String getStatus()
   :outertype: EBMSConfigSender

   :return: Get the result status for the last successful web services call.

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: EBMSConfigSender

   The SOAPRequest in the creation stage should be liked this.

   :throws Exceptions:

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: EBMSConfigSender

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: EBMSConfigSender

   Get the SOAP Body and analyze the result of configuration.

   The result of SOAP body:

   .. parsed-literal::

      <status>success | fail</status>

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: EBMSConfigSender

   [@EVENT] The method \ ``onStart``\  log all new configuration.

