.. java:import:: hk.hku.cecid.edi.as2 AS2PlusProcessor

.. java:import:: hk.hku.cecid.edi.as2.dao AS2DAOHandler

.. java:import:: hk.hku.cecid.edi.as2.dao PartnershipDAO

.. java:import:: hk.hku.cecid.edi.as2.dao PartnershipDVO

.. java:import:: hk.hku.cecid.edi.as2.module OutgoingMessageProcessor

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: hk.hku.cecid.edi.as2.util AS2Util

.. java:import:: hk.hku.cecid.piazza.commons.activation InputStreamDataSource

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOFactory

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPFaultException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequestException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPResponse

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesAdaptor

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesResponse

.. java:import:: java.io InputStream

.. java:import:: java.util Iterator

.. java:import:: java.util.zip InflaterInputStream

.. java:import:: javax.xml.soap AttachmentPart

.. java:import:: javax.xml.soap SOAPBodyElement

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPMessage

AS2MessageSenderService
=======================

.. java:package:: hk.hku.cecid.edi.as2.service
   :noindex:

.. java:type:: public class AS2MessageSenderService extends WebServicesAdaptor

   AS2MessageSenderService

   :author: Hugo Y. K. Lam

Fields
------
NAMESPACE
^^^^^^^^^

.. java:field:: public static final String NAMESPACE
   :outertype: AS2MessageSenderService

Methods
-------
isCacheEnabled
^^^^^^^^^^^^^^

.. java:method:: protected boolean isCacheEnabled()
   :outertype: AS2MessageSenderService

serviceRequested
^^^^^^^^^^^^^^^^

.. java:method:: public void serviceRequested(WebServicesRequest request, WebServicesResponse response) throws SOAPRequestException, DAOException
   :outertype: AS2MessageSenderService

