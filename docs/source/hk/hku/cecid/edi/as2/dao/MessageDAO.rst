.. java:import:: hk.hku.cecid.piazza.commons.dao DAO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: java.util List

MessageDAO
==========

.. java:package:: hk.hku.cecid.edi.as2.dao
   :noindex:

.. java:type:: public interface MessageDAO extends DAO

   :author: Donahue Sze

Methods
-------
findMessageByOriginalMessageID
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessageByOriginalMessageID(String oriMessageID, String oriMessageBox) throws DAOException
   :outertype: MessageDAO

findMessagesBeforeTime
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesBeforeTime(int months) throws DAOException
   :outertype: MessageDAO

findMessagesByHistory
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesByHistory(MessageDVO data, int numberOfMessage, int offset) throws DAOException
   :outertype: MessageDAO

findMessagesByStatus
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesByStatus(String status, String messageBox) throws DAOException
   :outertype: MessageDAO

findMessagesByTime
^^^^^^^^^^^^^^^^^^

.. java:method:: public List findMessagesByTime(int time_period, MessageDVO data, int numberOfMessage, int offset) throws DAOException
   :outertype: MessageDAO

findNumberOfMessagesByHistory
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int findNumberOfMessagesByHistory(MessageDVO data) throws DAOException
   :outertype: MessageDAO

recoverProcessingMessages
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int recoverProcessingMessages() throws DAOException
   :outertype: MessageDAO

