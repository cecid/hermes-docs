.. java:import:: hk.hku.cecid.edi.as2 AS2Exception

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Header

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2MessageException

.. java:import:: hk.hku.cecid.edi.as2.pkg DispositionNotification

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOFactory

.. java:import:: java.security Principal

.. java:import:: java.util Date

AS2DAOHandler
=============

.. java:package:: hk.hku.cecid.edi.as2.dao
   :noindex:

.. java:type:: public class AS2DAOHandler

   AS2DAOHandler

   :author: Hugo Y. K. Lam

Constructors
------------
AS2DAOHandler
^^^^^^^^^^^^^

.. java:constructor:: public AS2DAOHandler(DAOFactory daoFactory)
   :outertype: AS2DAOHandler

AS2DAOHandler
^^^^^^^^^^^^^

.. java:constructor:: public AS2DAOHandler(DAOFactory daoFactory, Principal principal)
   :outertype: AS2DAOHandler

Methods
-------
createMessageDAO
^^^^^^^^^^^^^^^^

.. java:method:: public MessageDAO createMessageDAO() throws DAOException
   :outertype: AS2DAOHandler

createMessageDVO
^^^^^^^^^^^^^^^^

.. java:method:: public MessageDVO createMessageDVO(AS2Message message, boolean isIncoming) throws AS2MessageException, AS2Exception, DAOException
   :outertype: AS2DAOHandler

createMessageStore
^^^^^^^^^^^^^^^^^^

.. java:method:: public MessageStoreDAO createMessageStore() throws DAOException
   :outertype: AS2DAOHandler

createPartnershipDAO
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public PartnershipDAO createPartnershipDAO() throws DAOException
   :outertype: AS2DAOHandler

createRawRepositoryDAO
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public RawRepositoryDAO createRawRepositoryDAO() throws DAOException
   :outertype: AS2DAOHandler

createRawRepositoryDVO
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public RawRepositoryDVO createRawRepositoryDVO(AS2Message message) throws AS2MessageException, DAOException
   :outertype: AS2DAOHandler

createRepositoryDAO
^^^^^^^^^^^^^^^^^^^

.. java:method:: public RepositoryDAO createRepositoryDAO() throws DAOException
   :outertype: AS2DAOHandler

createRepositoryDVO
^^^^^^^^^^^^^^^^^^^

.. java:method:: public RepositoryDVO createRepositoryDVO(AS2Message message, boolean isIncoming) throws AS2MessageException, DAOException
   :outertype: AS2DAOHandler

findMessageDVO
^^^^^^^^^^^^^^

.. java:method:: public MessageDVO findMessageDVO(String messageId, String messageBox) throws AS2Exception, DAOException
   :outertype: AS2DAOHandler

findPartnership
^^^^^^^^^^^^^^^

.. java:method:: public PartnershipDVO findPartnership(AS2Message message, boolean isIncoming) throws AS2Exception, DAOException
   :outertype: AS2DAOHandler

findPartnership
^^^^^^^^^^^^^^^

.. java:method:: public PartnershipDVO findPartnership(String partnershipId) throws AS2Exception, DAOException
   :outertype: AS2DAOHandler

findPartnership
^^^^^^^^^^^^^^^

.. java:method:: public PartnershipDVO findPartnership(String fromParty, String toParty) throws AS2Exception, DAOException
   :outertype: AS2DAOHandler

findRawRepositoryDVO
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public RawRepositoryDVO findRawRepositoryDVO(String messageId) throws AS2Exception, DAOException
   :outertype: AS2DAOHandler

