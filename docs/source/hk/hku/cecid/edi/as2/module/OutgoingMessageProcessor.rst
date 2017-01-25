.. java:import:: hk.hku.cecid.edi.as2.dao AS2DAOHandler

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDVO

.. java:import:: hk.hku.cecid.edi.as2.dao PartnershipDVO

.. java:import:: hk.hku.cecid.edi.as2.dao RawRepositoryDVO

.. java:import:: hk.hku.cecid.edi.as2.dao RepositoryDVO

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Header

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: hk.hku.cecid.edi.as2.pkg DispositionNotificationOption

.. java:import:: hk.hku.cecid.edi.as2.util AS2Util

.. java:import:: hk.hku.cecid.piazza.commons.activation ByteArrayDataSource

.. java:import:: hk.hku.cecid.piazza.commons.activation InputStreamDataSource

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.module SystemComponent

.. java:import:: hk.hku.cecid.piazza.commons.security KeyStoreManager

.. java:import:: hk.hku.cecid.piazza.commons.security SMimeException

.. java:import:: hk.hku.cecid.piazza.commons.security SMimeMessage

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.util Iterator

.. java:import:: java.util Properties

.. java:import:: java.util Set

.. java:import:: javax.activation DataHandler

.. java:import:: javax.activation DataSource

.. java:import:: javax.mail.internet MimeBodyPart

OutgoingMessageProcessor
========================

.. java:package:: hk.hku.cecid.edi.as2.module
   :noindex:

.. java:type:: public class OutgoingMessageProcessor extends SystemComponent

Methods
-------
calculateMIC
^^^^^^^^^^^^

.. java:method:: public String calculateMIC(SMimeMessage smime, PartnershipDVO partnership) throws SMimeException
   :outertype: OutgoingMessageProcessor

init
^^^^

.. java:method:: @Override protected void init() throws Exception
   :outertype: OutgoingMessageProcessor

resendAsNew
^^^^^^^^^^^

.. java:method:: public AS2Message resendAsNew(String primalMessageId) throws Exception
   :outertype: OutgoingMessageProcessor

storeOutgoingMessage
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public AS2Message storeOutgoingMessage(String messageID, String type, PartnershipDVO partnership, DataSource attachementSource) throws Exception
   :outertype: OutgoingMessageProcessor

storeOutgoingMessage
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public AS2Message storeOutgoingMessage(String messageID, String type, PartnershipDVO partnership, DataSource attachementSource, MessageDVO primalMsgDVO) throws Exception
   :outertype: OutgoingMessageProcessor

