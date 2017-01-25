Transaction
===========

.. java:package:: hk.hku.cecid.piazza.commons.dao
   :noindex:

.. java:type:: public interface Transaction

   The Transaction interface allows operations to be performed against the transaction in the target Transaction object. A Transaction object is created by a corresponding DAO factory. Before any transaction starts, the Transaction object should be notified by the invocation of its begin() method. When the transaction is finished, either commit() or rollback should be invoked and the resources it acquired should be released accordingly.

   :author: Hugo Y. K. Lam

Methods
-------
begin
^^^^^

.. java:method:: public void begin() throws DAOException
   :outertype: Transaction

   Begins the transaction.

   :throws DAOException: if unable to begin the transaction.

commit
^^^^^^

.. java:method:: public void commit() throws DAOException
   :outertype: Transaction

   Commits the transaction.

   :throws DAOException: if unable to commit the transaction.

rollback
^^^^^^^^

.. java:method:: public void rollback() throws DAOException
   :outertype: Transaction

   Rolls back the transaction.

   :throws DAOException: unable to roll back the transaction.

