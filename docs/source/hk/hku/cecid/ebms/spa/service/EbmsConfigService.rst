.. java:import:: org.w3c.dom Element

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequestException

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesAdaptor

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesResponse

.. java:import:: hk.hku.cecid.piazza.commons.module ActiveTaskModule

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

EbmsConfigService
=================

.. java:package:: hk.hku.cecid.ebms.spa.service
   :noindex:

.. java:type:: public class EbmsConfigService extends WebServicesAdaptor

Methods
-------
isCacheEnabled
^^^^^^^^^^^^^^

.. java:method:: protected boolean isCacheEnabled()
   :outertype: EbmsConfigService

replaceNullToEmpty
^^^^^^^^^^^^^^^^^^

.. java:method:: public String replaceNullToEmpty(String value)
   :outertype: EbmsConfigService

serviceRequested
^^^^^^^^^^^^^^^^

.. java:method:: public void serviceRequested(WebServicesRequest request, WebServicesResponse response) throws SOAPRequestException
   :outertype: EbmsConfigService

