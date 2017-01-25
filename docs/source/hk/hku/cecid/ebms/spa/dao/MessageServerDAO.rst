.. java:import:: hk.hku.cecid.piazza.commons.dao DAO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

MessageServerDAO
================

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public interface MessageServerDAO extends DAO

   :author: Donahue Sze

Methods
-------
clearMessage
^^^^^^^^^^^^

.. java:method:: public void clearMessage(MessageDVO data) throws DAOException
   :outertype: MessageServerDAO

storeMessage
^^^^^^^^^^^^

.. java:method:: public void storeMessage(MessageDVO messageDVO, RepositoryDVO repositoryDVO) throws DAOException
   :outertype: MessageServerDAO

storeOutboxMessage
^^^^^^^^^^^^^^^^^^

.. java:method:: public void storeOutboxMessage(MessageDVO messageDVO, RepositoryDVO repositoryDVO, OutboxDVO outboxDVO, MessageDVO primalMsgDVO) throws DAOException
   :outertype: MessageServerDAO

