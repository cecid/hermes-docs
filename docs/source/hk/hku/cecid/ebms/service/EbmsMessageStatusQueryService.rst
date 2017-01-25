.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDVO

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageClassifier

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequestException

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesAdaptor

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesResponse

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: org.w3c.dom Element

EbmsMessageStatusQueryService
=============================

.. java:package:: hk.hku.cecid.ebms.service
   :noindex:

.. java:type:: public class EbmsMessageStatusQueryService extends WebServicesAdaptor

   EbmsMessageStatusQueryService

   :author: Donahue Sze

Methods
-------
isCacheEnabled
^^^^^^^^^^^^^^

.. java:method:: protected boolean isCacheEnabled()
   :outertype: EbmsMessageStatusQueryService

replaceNullToEmpty
^^^^^^^^^^^^^^^^^^

.. java:method:: public String replaceNullToEmpty(String value)
   :outertype: EbmsMessageStatusQueryService

serviceRequested
^^^^^^^^^^^^^^^^

.. java:method:: public void serviceRequested(WebServicesRequest request, WebServicesResponse response) throws SOAPRequestException, DAOException
   :outertype: EbmsMessageStatusQueryService

