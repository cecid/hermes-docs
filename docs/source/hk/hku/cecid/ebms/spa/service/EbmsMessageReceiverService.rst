.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageServerDAO

.. java:import:: hk.hku.cecid.ebms.spa.handler EbxmlMessageDAOConvertor

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageClassifier

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPFaultException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequestException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPResponse

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesAdaptor

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesResponse

.. java:import:: java.util ArrayList

.. java:import:: java.util Iterator

.. java:import:: javax.xml.namespace QName

.. java:import:: javax.xml.soap AttachmentPart

.. java:import:: javax.xml.soap SOAPBodyElement

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPFactory

.. java:import:: javax.xml.soap SOAPMessage

EbmsMessageReceiverService
==========================

.. java:package:: hk.hku.cecid.ebms.spa.service
   :noindex:

.. java:type:: public class EbmsMessageReceiverService extends WebServicesAdaptor

   AS2MessageReceiverListService

   :author: Donahue Sze

Fields
------
NAMESPACE
^^^^^^^^^

.. java:field:: public static String NAMESPACE
   :outertype: EbmsMessageReceiverService

Methods
-------
isCacheEnabled
^^^^^^^^^^^^^^

.. java:method:: protected boolean isCacheEnabled()
   :outertype: EbmsMessageReceiverService

serviceRequested
^^^^^^^^^^^^^^^^

.. java:method:: public void serviceRequested(WebServicesRequest request, WebServicesResponse response) throws SOAPRequestException, DAOException, SOAPException
   :outertype: EbmsMessageReceiverService

