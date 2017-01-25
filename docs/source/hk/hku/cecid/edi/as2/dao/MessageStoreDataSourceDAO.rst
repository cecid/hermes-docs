.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDAO

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceProcess

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceTransaction

MessageStoreDataSourceDAO
=========================

.. java:package:: hk.hku.cecid.edi.as2.dao
   :noindex:

.. java:type:: public class MessageStoreDataSourceDAO extends DataSourceDAO implements MessageStoreDAO

   :author: Donahue Sze

Methods
-------
createDVO
^^^^^^^^^

.. java:method:: public DVO createDVO()
   :outertype: MessageStoreDataSourceDAO

storeMessage
^^^^^^^^^^^^

.. java:method:: public void storeMessage(MessageDVO primalMsgDVO, MessageDVO msgDVO, RepositoryDVO repoDVO, RawRepositoryDVO rawRepoDVO) throws DAOException
   :outertype: MessageStoreDataSourceDAO

storeMessage
^^^^^^^^^^^^

.. java:method:: public void storeMessage(MessageDVO messageDVO, RepositoryDVO repositoryDVO) throws DAOException
   :outertype: MessageStoreDataSourceDAO

storeMessage
^^^^^^^^^^^^

.. java:method:: public void storeMessage(MessageDVO[] messageDVO, RepositoryDVO[] repositoryDVO) throws DAOException
   :outertype: MessageStoreDataSourceDAO

storeReceipt
^^^^^^^^^^^^

.. java:method:: public void storeReceipt(MessageDVO receiptMessageDVO, RepositoryDVO receiptRepositoryDVO, MessageDVO originalMessageDVO) throws DAOException
   :outertype: MessageStoreDataSourceDAO

