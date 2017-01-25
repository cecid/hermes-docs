.. java:import:: java.util Date

.. java:import:: java.util Map

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data Data

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data AS2ConfigData

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

AS2ConfigSender
===============

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class AS2ConfigSender extends SOAPSender

   The \ ``AS2ConfigSender``\  is a client sender sending SOAP web services request to B2BCollector \ ``AS2``\  plugin for configurating the performance factor. The web service parameters are defined in the below:

   .. parsed-literal::

      <active-module-status> true | false </active-module-status>
      <inmessage-interval>15000</inmessage-interval>
      <inmessage-maxthread>0</inmessage-maxthread>
      <outmessage-interval>15000</outmessage-interval>
      <outmessage-maxthread>0</outmessage-maxthread>
      <outpayload-interval>15000</outpayload-interval>
      <outpayload-maxthread>0</outpayload-maxthread>

   :author: Twinsen Tsang

Constructors
------------
AS2ConfigSender
^^^^^^^^^^^^^^^

.. java:constructor:: public AS2ConfigSender(FileLogger l, AS2ConfigData data)
   :outertype: AS2ConfigSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param data: The AS2 Configuration parameters.

Methods
-------
getStatus
^^^^^^^^^

.. java:method:: public String getStatus()
   :outertype: AS2ConfigSender

   :return: Get the result status for the last successful web services call.

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: AS2ConfigSender

   The SOAPRequest in the creation stage should be liked this.

   :throws Exceptions:

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: AS2ConfigSender

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: AS2ConfigSender

   Get the SOAP Body and analyze the result of configuration.

   The result of SOAP body:

   .. parsed-literal::

      <status>success | fail</status>

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: AS2ConfigSender

   [@EVENT] The method \ ``onStart``\  log all new configuration.

