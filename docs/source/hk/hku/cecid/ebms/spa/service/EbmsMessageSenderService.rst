.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.pkg MessageHeader

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa EbmsUtility

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDVO

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageServiceHandler

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageServiceHandlerException

.. java:import:: hk.hku.cecid.ebms.spa.listener EbmsRequest

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPFaultException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequestException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPResponse

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesAdaptor

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesResponse

.. java:import:: hk.hku.cecid.piazza.commons.util Generator

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap AttachmentPart

.. java:import:: javax.xml.soap SOAPBodyElement

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPMessage

EbmsMessageSenderService
========================

.. java:package:: hk.hku.cecid.ebms.spa.service
   :noindex:

.. java:type:: public class EbmsMessageSenderService extends WebServicesAdaptor

   EbmsMessageSenderService

   :author: Hugo Y. K. Lam

Fields
------
NAMESPACE
^^^^^^^^^

.. java:field:: public static final String NAMESPACE
   :outertype: EbmsMessageSenderService

Methods
-------
isCacheEnabled
^^^^^^^^^^^^^^

.. java:method:: protected boolean isCacheEnabled()
   :outertype: EbmsMessageSenderService

serviceRequested
^^^^^^^^^^^^^^^^

.. java:method:: public void serviceRequested(WebServicesRequest request, WebServicesResponse response) throws SOAPRequestException, DAOException
   :outertype: EbmsMessageSenderService

