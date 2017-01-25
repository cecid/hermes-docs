.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.pkg MessageHeader

.. java:import:: hk.hku.cecid.ebms.pkg MessageOrder

.. java:import:: hk.hku.cecid.ebms.pkg PayloadContainer

.. java:import:: hk.hku.cecid.ebms.pkg MessageHeader.PartyId

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa EbmsUtility

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageServerDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao OutboxDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao RepositoryDVO

.. java:import:: hk.hku.cecid.ebms.spa.listener EbmsRequest

.. java:import:: hk.hku.cecid.ebms.spa.listener EbmsResponse

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.rest RestRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesRequest

.. java:import:: hk.hku.cecid.piazza.commons.util Generator

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.soap SOAPException

OutboundMessageProcessor
========================

.. java:package:: hk.hku.cecid.ebms.spa.handler
   :noindex:

.. java:type:: public class OutboundMessageProcessor

   :author: Donahue Sze

Fields
------
outboundMessageProcessor
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static OutboundMessageProcessor outboundMessageProcessor
   :outertype: OutboundMessageProcessor

outboundMessageProcessor_initFlag
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static boolean outboundMessageProcessor_initFlag
   :outertype: OutboundMessageProcessor

Methods
-------
getInstance
^^^^^^^^^^^

.. java:method:: public static synchronized OutboundMessageProcessor getInstance()
   :outertype: OutboundMessageProcessor

processOutgoingMessage
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void processOutgoingMessage(EbmsRequest request, EbmsResponse response) throws MessageServiceHandlerException
   :outertype: OutboundMessageProcessor

resendAsNew
^^^^^^^^^^^

.. java:method:: public EbxmlMessage resendAsNew(String primalMessageId) throws Exception
   :outertype: OutboundMessageProcessor

