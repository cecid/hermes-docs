.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDAO

.. java:import:: java.sql Timestamp

.. java:import:: java.util ArrayList

.. java:import:: java.util GregorianCalendar

.. java:import:: java.util Iterator

.. java:import:: java.util List

MessageDataSourceDAO
====================

.. java:package:: hk.hku.cecid.edi.as2.dao
   :noindex:

.. java:type:: public class MessageDataSourceDAO extends DataSourceDAO implements MessageDAO

   :author: Donahue Sze

Methods
-------
createDVO
^^^^^^^^^

.. java:method:: public DVO createDVO()
   :outertype: MessageDataSourceDAO

findMessageByOriginalMessageID
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessageByOriginalMessageID(String oriMessageID, String oriMessageBox) throws DAOException
   :outertype: MessageDataSourceDAO

findMessagesBeforeTime
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesBeforeTime(int time_period) throws DAOException
   :outertype: MessageDataSourceDAO

findMessagesByHistory
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesByHistory(MessageDVO data, int numberOfMessage, int offset) throws DAOException
   :outertype: MessageDataSourceDAO

findMessagesByStatus
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesByStatus(String status, String messageBox) throws DAOException
   :outertype: MessageDataSourceDAO

findMessagesByTime
^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesByTime(int time_period, MessageDVO data, int numberOfMessage, int offset) throws DAOException
   :outertype: MessageDataSourceDAO

findNumberOfMessagesByHistory
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int findNumberOfMessagesByHistory(MessageDVO data) throws DAOException
   :outertype: MessageDataSourceDAO

recoverProcessingMessages
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int recoverProcessingMessages() throws DAOException
   :outertype: MessageDataSourceDAO

