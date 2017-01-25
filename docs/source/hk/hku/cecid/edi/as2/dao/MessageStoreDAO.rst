.. java:import:: hk.hku.cecid.piazza.commons.dao DAO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

MessageStoreDAO
===============

.. java:package:: hk.hku.cecid.edi.as2.dao
   :noindex:

.. java:type:: public interface MessageStoreDAO extends DAO

   :author: Donahue Sze

Methods
-------
storeMessage
^^^^^^^^^^^^

.. java:method:: public void storeMessage(MessageDVO primalMsgDVO, MessageDVO msgDVO, RepositoryDVO repoDVO, RawRepositoryDVO rawRepoDVO) throws DAOException
   :outertype: MessageStoreDAO

storeMessage
^^^^^^^^^^^^

.. java:method:: public void storeMessage(MessageDVO[] messageDVO, RepositoryDVO[] repositoryDVO) throws DAOException
   :outertype: MessageStoreDAO

storeMessage
^^^^^^^^^^^^

.. java:method:: public void storeMessage(MessageDVO messageDVO, RepositoryDVO repositoryDVO) throws DAOException
   :outertype: MessageStoreDAO

storeReceipt
^^^^^^^^^^^^

.. java:method:: public void storeReceipt(MessageDVO receiptMessageDVO, RepositoryDVO receiptRepositoryDVO, MessageDVO originalMessageDVO) throws DAOException
   :outertype: MessageStoreDAO

