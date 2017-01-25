.. java:import:: java.util List

.. java:import:: java.util Date

.. java:import:: hk.hku.cecid.piazza.commons.dao DAO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

MessageDAO
==========

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public interface MessageDAO extends DAO

   :author: Donahue Sze, Twinsen Tsang (modifiers)

Methods
-------
addMessage
^^^^^^^^^^

.. java:method:: public void addMessage(MessageDVO data) throws DAOException
   :outertype: MessageDAO

deleteMessage
^^^^^^^^^^^^^

.. java:method:: public void deleteMessage(MessageDVO data) throws DAOException
   :outertype: MessageDAO

findInboxPendingMessagesByTimestamp
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findInboxPendingMessagesByTimestamp(MessageDVO messageDVO) throws DAOException
   :outertype: MessageDAO

findInboxReadyMaxSequenceNoByCpa
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int findInboxReadyMaxSequenceNoByCpa(MessageDVO data) throws DAOException
   :outertype: MessageDAO

findMaxSequenceGroupByMessageBoxAndCpa
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int findMaxSequenceGroupByMessageBoxAndCpa(MessageDVO data) throws DAOException
   :outertype: MessageDAO

findMaxSequenceNoByMessageBoxAndCpa
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int findMaxSequenceNoByMessageBoxAndCpa(MessageDVO data) throws DAOException
   :outertype: MessageDAO

findMessage
^^^^^^^^^^^

.. java:method:: public boolean findMessage(MessageDVO data) throws DAOException
   :outertype: MessageDAO

findMessageByCpa
^^^^^^^^^^^^^^^^

.. java:method:: public List findMessageByCpa(MessageDVO data, int numberOfMessage) throws DAOException
   :outertype: MessageDAO

findMessagesBeforeTime
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesBeforeTime(int time_period) throws DAOException
   :outertype: MessageDAO

findMessagesByHistory
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesByHistory(MessageDVO data, int numberOfMessage, int offset) throws DAOException
   :outertype: MessageDAO

findMessagesByTime
^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesByTime(int time_period, MessageDVO data, int numberOfMessage, int offset) throws DAOException
   :outertype: MessageDAO

findNumOfMessagesByMessageBoxAndCpaAndSequenceGroup
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int findNumOfMessagesByMessageBoxAndCpaAndSequenceGroup(MessageDVO data) throws DAOException
   :outertype: MessageDAO

findNumberOfMessagesByHistory
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int findNumberOfMessagesByHistory(MessageDVO data) throws DAOException
   :outertype: MessageDAO

findOrderedMessageByMessageBoxAndCpaAndSequenceGroupAndSequenceNo
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean findOrderedMessageByMessageBoxAndCpaAndSequenceGroupAndSequenceNo(MessageDVO data) throws DAOException
   :outertype: MessageDAO

findOrderedMessagesByMessageBoxAndCpaAndStatus
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findOrderedMessagesByMessageBoxAndCpaAndStatus(MessageDVO data) throws DAOException
   :outertype: MessageDAO

findOutboxPendingMessagesByTimestamp
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findOutboxPendingMessagesByTimestamp(MessageDVO messageDVO) throws DAOException
   :outertype: MessageDAO

findOutboxProcessingMessagesByTimestamp
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findOutboxProcessingMessagesByTimestamp(MessageDVO messageDVO) throws DAOException
   :outertype: MessageDAO

findRefToMessage
^^^^^^^^^^^^^^^^

.. java:method:: public boolean findRefToMessage(MessageDVO data) throws DAOException
   :outertype: MessageDAO

updateMessage
^^^^^^^^^^^^^

.. java:method:: public boolean updateMessage(MessageDVO data) throws DAOException
   :outertype: MessageDAO

updateTimedOutMessageStatus
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int updateTimedOutMessageStatus(String status, Date currentTime) throws DAOException
   :outertype: MessageDAO

   Update the status of all timed-out message to \ ``status``\ . A message is considered as timed-out if the timeout timestamp is earlier than the \ ``currentTime``\ .

   :throws DAOException: When \ ``status``\  is null or Error in persistence connectivity.

   **See also:** :java:ref:`hk.hku.cecid.ebms.spa.dao.MessageDVO.getTimeoutTimestamp()`, :java:ref:`hk.hku.cecid.ebms.spa.dao.MessageDVO.setTimeoutTimestamp(java.sql.Timestamp)`

