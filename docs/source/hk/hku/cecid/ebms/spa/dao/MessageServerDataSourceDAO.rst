.. java:import:: hk.hku.cecid.ebms.spa.handler MessageClassifier

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDAO

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceProcess

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceTransaction

MessageServerDataSourceDAO
==========================

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public class MessageServerDataSourceDAO extends DataSourceDAO implements MessageServerDAO

   :author: Donahue Sze

Methods
-------
clearMessage
^^^^^^^^^^^^

.. java:method:: public void clearMessage(MessageDVO data) throws DAOException
   :outertype: MessageServerDataSourceDAO

createDVO
^^^^^^^^^

.. java:method:: public DVO createDVO()
   :outertype: MessageServerDataSourceDAO

storeMessage
^^^^^^^^^^^^

.. java:method:: public void storeMessage(MessageDVO messageDVO, RepositoryDVO repositoryDVO) throws DAOException
   :outertype: MessageServerDataSourceDAO

storeOutboxMessage
^^^^^^^^^^^^^^^^^^

.. java:method:: public void storeOutboxMessage(MessageDVO messageDVO, RepositoryDVO repositoryDVO, OutboxDVO outboxDVO, MessageDVO primalMsgDVO) throws DAOException
   :outertype: MessageServerDataSourceDAO

