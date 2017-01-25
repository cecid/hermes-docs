.. java:import:: org.w3c.dom Element

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequestException

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesAdaptor

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesResponse

.. java:import:: hk.hku.cecid.piazza.commons.module ActiveTaskModule

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: hk.hku.cecid.edi.as2 AS2PlusProcessor

AS2ConfigService
================

.. java:package:: hk.hku.cecid.edi.as2.service
   :noindex:

.. java:type:: public class AS2ConfigService extends WebServicesAdaptor

   This is a AS2 Configuration Web Service. The XML SOAP Message should be liked this.

   .. parsed-literal::

      <active-module-status> true | false </active-module-status>
      <inmessage-interval>15000 </inmessage-interval>
      <inmessage-maxthread>0</inmessage-maxthread>
      <outmessage-interval>15000</outmessage-interval>
      <outmessage-maxthread>0</outmessage-maxthread>
      <outpayload-interval>15000</outpayload-interval>
      <outpayload-maxthread>0</outpayload-maxthread>

   :author: Twinsen Tsang.

Methods
-------
isCacheEnabled
^^^^^^^^^^^^^^

.. java:method:: protected boolean isCacheEnabled()
   :outertype: AS2ConfigService

replaceNullToEmpty
^^^^^^^^^^^^^^^^^^

.. java:method:: public String replaceNullToEmpty(String value)
   :outertype: AS2ConfigService

serviceRequested
^^^^^^^^^^^^^^^^

.. java:method:: public void serviceRequested(WebServicesRequest request, WebServicesResponse response) throws SOAPRequestException
   :outertype: AS2ConfigService

