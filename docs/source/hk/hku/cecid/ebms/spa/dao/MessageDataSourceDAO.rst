.. java:import:: java.sql Timestamp

.. java:import:: java.util ArrayList

.. java:import:: java.util Date

.. java:import:: java.util GregorianCalendar

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDAO

MessageDataSourceDAO
====================

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public class MessageDataSourceDAO extends DataSourceDAO implements MessageDAO

   :author: Donahue Sze Window - Preferences - Java - Code Style - Code Templates

Methods
-------
addMessage
^^^^^^^^^^

.. java:method:: public void addMessage(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

createDVO
^^^^^^^^^

.. java:method:: public DVO createDVO()
   :outertype: MessageDataSourceDAO

deleteMessage
^^^^^^^^^^^^^

.. java:method:: public void deleteMessage(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

findInboxPendingMessagesByTimestamp
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findInboxPendingMessagesByTimestamp(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

   Find all the pending messages for inbox collector order by timestamp.

   :param data: The message data value object.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a List of DVO resulted from the specified SQL query. An empty List will be returned if there is no matching data.

findInboxReadyMaxSequenceNoByCpa
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int findInboxReadyMaxSequenceNoByCpa(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

   Find max sequence no. of inbox message in PS or DL status by CPA Only for EbMS Inbox Collector Service

   :param data: The message data value object.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: max sequence no. -1 will be returned if there is no matching data.

findMaxSequenceGroupByMessageBoxAndCpa
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int findMaxSequenceGroupByMessageBoxAndCpa(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

findMaxSequenceNoByMessageBoxAndCpa
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int findMaxSequenceNoByMessageBoxAndCpa(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

   Find max sequence no. of message by CPA and message box

   :param data: The message data value object.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: max sequence no. -1 will be returned if there is no matching data.

findMessage
^^^^^^^^^^^

.. java:method:: public boolean findMessage(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

findMessageByCpa
^^^^^^^^^^^^^^^^

.. java:method:: public List findMessageByCpa(MessageDVO data, int numberOfMessage) throws DAOException
   :outertype: MessageDataSourceDAO

   Find all the message by CPA, status, message type and message box. Only for EbMS Message Collector Service

   :param data: The message data value object.
   :param numberOfMessage: The no. of message return.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a List of DVO resulted from the specified SQL query. An empty List will be returned if there is no matching data.

findMessagesBeforeTime
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesBeforeTime(int time_period) throws DAOException
   :outertype: MessageDataSourceDAO

findMessagesByHistory
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesByHistory(MessageDVO data, int numberOfMessage, int offset) throws DAOException
   :outertype: MessageDataSourceDAO

   Find messages order by descending timestamp by different criteria.

   :param data: The message data value object carrying query criteria.
   :param numberOfMessage: max no. of message in return.
   :param offset: no. of starting record in return.
   :throws DAOException:

findMessagesByTime
^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesByTime(int time_period, MessageDVO data, int numberOfMessage, int offset) throws DAOException
   :outertype: MessageDataSourceDAO

findNumOfMessagesByMessageBoxAndCpaAndSequenceGroup
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int findNumOfMessagesByMessageBoxAndCpaAndSequenceGroup(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

findNumberOfMessagesByHistory
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int findNumberOfMessagesByHistory(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

   Find number of messages by different criteria.

   :param data: The message data value object carrying query criteria.
   :throws DAOException:

findOrderedMessageByMessageBoxAndCpaAndSequenceGroupAndSequenceNo
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean findOrderedMessageByMessageBoxAndCpaAndSequenceGroupAndSequenceNo(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

findOrderedMessagesByMessageBoxAndCpaAndStatus
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findOrderedMessagesByMessageBoxAndCpaAndStatus(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

findOutboxPendingMessagesByTimestamp
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findOutboxPendingMessagesByTimestamp(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

   Find all the pending messages for outbox collector order by timestamp.

   :param data: The message data value object.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a List of DVO resulted from the specified SQL query. An empty List will be returned if there is no matching data.

findOutboxProcessingMessagesByTimestamp
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findOutboxProcessingMessagesByTimestamp(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

   Find all the processing messages for outbox collector order by timestamp.

   :param data: The message data value object.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a List of DVO resulted from the specified SQL query. An empty List will be returned if there is no matching data.

findRefToMessage
^^^^^^^^^^^^^^^^

.. java:method:: public boolean findRefToMessage(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

updateMessage
^^^^^^^^^^^^^

.. java:method:: public boolean updateMessage(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

updateTimedOutMessageStatus
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int updateTimedOutMessageStatus(String status, Date currentTime) throws DAOException
   :outertype: MessageDataSourceDAO

   Update the status of all timed-out message to \ ``status``\ . A message is considered as timed-out if the timeout timestamp is earlier than the \ ``currentTime``\ .

   :throws DAOException: When \ ``status``\  is null or Error in persistence connectivity.

   **See also:** :java:ref:`hk.hku.cecid.ebms.spa.dao.MessageDVO.getTimeoutTimestamp()`, :java:ref:`hk.hku.cecid.ebms.spa.dao.MessageDVO.setTimeoutTimestamp(java.sql.Timestamp)`

