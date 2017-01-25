.. java:import:: hk.hku.cecid.ebms.spa EbmsUtility

.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.pkg MessageHeader

.. java:import:: hk.hku.cecid.ebms.pkg MessageHeader.PartyId

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao InboxDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao InboxDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao OutboxDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao OutboxDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao RepositoryDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao RepositoryDVO

.. java:import:: hk.hku.cecid.ebms.spa.task MessageValidationException

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.util DataFormatter

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io IOException

.. java:import:: java.sql Timestamp

.. java:import:: java.util Iterator

.. java:import:: java.util Date

.. java:import:: javax.xml.soap MessageFactory

.. java:import:: javax.xml.soap MimeHeaders

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPMessage

EbxmlMessageDAOConvertor
========================

.. java:package:: hk.hku.cecid.ebms.spa.handler
   :noindex:

.. java:type:: public class EbxmlMessageDAOConvertor

   The EbxmlMessageDAOConvertor construct the necessary DAO Data from EbxmlMessage.

   :author: Donahue Sze

Constructors
------------
EbxmlMessageDAOConvertor
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EbxmlMessageDAOConvertor(EbxmlMessage ebxmlMessage, String messageBox, String messageType)
   :outertype: EbxmlMessageDAOConvertor

   Create a new instance of Ebxml Message to DAO Data Convertor

   :param ebxmlMessage: Ebxml Message to be converted
   :param messageBox: Message box the message will be stored
   :param messageType: The type of the message

Methods
-------
getEbxmlMessage
^^^^^^^^^^^^^^^

.. java:method:: public static EbxmlMessage getEbxmlMessage(String messageId, String messageBox) throws MessageValidationException
   :outertype: EbxmlMessageDAOConvertor

getInboxDVO
^^^^^^^^^^^

.. java:method:: public InboxDVO getInboxDVO() throws DAOException
   :outertype: EbxmlMessageDAOConvertor

   Get the inbox DAO data

   :throws DAOException:
   :return: The inbox DAO data

getMessageDVO
^^^^^^^^^^^^^

.. java:method:: public MessageDVO getMessageDVO() throws DAOException
   :outertype: EbxmlMessageDAOConvertor

   Get the message dao data

   :throws DAOException:
   :return: The message dao data

getOutboxDVO
^^^^^^^^^^^^

.. java:method:: public OutboxDVO getOutboxDVO() throws DAOException
   :outertype: EbxmlMessageDAOConvertor

   Get the outbox DAO data

   :throws DAOException:
   :return: The outbox DAO data

getRepositoryDVO
^^^^^^^^^^^^^^^^

.. java:method:: public RepositoryDVO getRepositoryDVO() throws DAOException
   :outertype: EbxmlMessageDAOConvertor

   Get the repository DAO data

   :throws DAOException:
   :return: The repository DAO data

