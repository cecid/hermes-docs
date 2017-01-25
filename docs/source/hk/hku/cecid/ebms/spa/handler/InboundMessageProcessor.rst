.. java:import:: hk.hku.cecid.ebms.spa EbmsUtility

.. java:import:: hk.hku.cecid.ebms.pkg Description

.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.pkg ErrorList

.. java:import:: hk.hku.cecid.ebms.pkg Signature

.. java:import:: hk.hku.cecid.ebms.pkg SignatureException

.. java:import:: hk.hku.cecid.ebms.pkg SignatureHandler

.. java:import:: hk.hku.cecid.ebms.pkg.validation EbxmlMessageValidator

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageServerDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao RepositoryDVO

.. java:import:: hk.hku.cecid.ebms.spa.listener EbmsRequest

.. java:import:: hk.hku.cecid.ebms.spa.listener EbmsResponse

.. java:import:: hk.hku.cecid.ebms.spa.task AgreementHandler

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequest

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.security.cert CertificateFactory

.. java:import:: java.security.cert X509Certificate

.. java:import:: java.util ArrayList

.. java:import:: java.util Calendar

.. java:import:: java.util Date

.. java:import:: java.util Iterator

.. java:import:: java.util TimeZone

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

InboundMessageProcessor
=======================

.. java:package:: hk.hku.cecid.ebms.spa.handler
   :noindex:

.. java:type:: public class InboundMessageProcessor

   :author: Donahue Sze Preferences - Java - Code Style - Code Templates

Fields
------
inboundMessageProcessor
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static InboundMessageProcessor inboundMessageProcessor
   :outertype: InboundMessageProcessor

inboundMessageProcessor_initFlag
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static boolean inboundMessageProcessor_initFlag
   :outertype: InboundMessageProcessor

Methods
-------
getInstance
^^^^^^^^^^^

.. java:method:: public static InboundMessageProcessor getInstance()
   :outertype: InboundMessageProcessor

processIncomingMessage
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void processIncomingMessage(EbmsRequest request, EbmsResponse response) throws MessageServiceHandlerException
   :outertype: InboundMessageProcessor

