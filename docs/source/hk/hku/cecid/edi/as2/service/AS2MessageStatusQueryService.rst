.. java:import:: hk.hku.cecid.edi.as2 AS2PlusProcessor

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDAO

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDVO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequestException

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesAdaptor

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesResponse

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: org.w3c.dom Element

AS2MessageStatusQueryService
============================

.. java:package:: hk.hku.cecid.edi.as2.service
   :noindex:

.. java:type:: public class AS2MessageStatusQueryService extends WebServicesAdaptor

   AS2MessageStatusQueryService

   :author: Donahue Sze

Methods
-------
isCacheEnabled
^^^^^^^^^^^^^^

.. java:method:: protected boolean isCacheEnabled()
   :outertype: AS2MessageStatusQueryService

replaceNullToEmpty
^^^^^^^^^^^^^^^^^^

.. java:method:: public String replaceNullToEmpty(String value)
   :outertype: AS2MessageStatusQueryService

serviceRequested
^^^^^^^^^^^^^^^^

.. java:method:: public void serviceRequested(WebServicesRequest request, WebServicesResponse response) throws SOAPRequestException, DAOException
   :outertype: AS2MessageStatusQueryService

