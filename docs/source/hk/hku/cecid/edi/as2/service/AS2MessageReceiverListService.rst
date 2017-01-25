.. java:import:: hk.hku.cecid.edi.as2 AS2PlusProcessor

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDAO

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDVO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPFaultException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequestException

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesAdaptor

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesResponse

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: javax.xml.soap SOAPBodyElement

.. java:import:: javax.xml.soap SOAPElement

AS2MessageReceiverListService
=============================

.. java:package:: hk.hku.cecid.edi.as2.service
   :noindex:

.. java:type:: public class AS2MessageReceiverListService extends WebServicesAdaptor

   AS2MessageReceiverListService

   :author: Donahue Sze

Fields
------
NAMESPACE
^^^^^^^^^

.. java:field:: public static final String NAMESPACE
   :outertype: AS2MessageReceiverListService

Methods
-------
isCacheEnabled
^^^^^^^^^^^^^^

.. java:method:: protected boolean isCacheEnabled()
   :outertype: AS2MessageReceiverListService

serviceRequested
^^^^^^^^^^^^^^^^

.. java:method:: public void serviceRequested(WebServicesRequest request, WebServicesResponse response) throws SOAPRequestException, DAOException
   :outertype: AS2MessageReceiverListService

