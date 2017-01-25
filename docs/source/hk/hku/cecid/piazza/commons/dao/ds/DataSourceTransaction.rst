.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao Transaction

.. java:import:: java.sql Connection

DataSourceTransaction
=====================

.. java:package:: hk.hku.cecid.piazza.commons.dao.ds
   :noindex:

.. java:type:: public class DataSourceTransaction implements Transaction

   DataSourceTransaction is an implementation of a DAO transaction. It should not be created directly and is usually created through DataSourceDAOFactory.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`DataSourceDAOFactory`

Constructors
------------
DataSourceTransaction
^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: protected DataSourceTransaction(DataSourceDAOFactory dsFactory) throws DAOException
   :outertype: DataSourceTransaction

   Creates a new instance of DataSourceTransaction.

   :param dsFactory: the data source factory which creates this transaction.
   :throws DAOException: if the no data source factory specified.

Methods
-------
begin
^^^^^

.. java:method:: public void begin() throws DAOException
   :outertype: DataSourceTransaction

   Begins the transaction.

   :throws DAOException: if unable to begin the transaction or the transaction has already begun.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.dao.Transaction.begin()`

commit
^^^^^^

.. java:method:: public void commit() throws DAOException
   :outertype: DataSourceTransaction

   Commits the transaction.

   :throws DAOException: if unable to commit the transaction.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.dao.Transaction.commit()`

getConnection
^^^^^^^^^^^^^

.. java:method:: public Connection getConnection() throws DAOException
   :outertype: DataSourceTransaction

   Gets the connection that this transaction manages.

   :throws DAOException: if the transaction has not begun or has been ended.
   :return: the connection this transaction manages.

releaseConnection
^^^^^^^^^^^^^^^^^

.. java:method:: public void releaseConnection()
   :outertype: DataSourceTransaction

   Releases the connection that this transaction manages.

rollback
^^^^^^^^

.. java:method:: public void rollback() throws DAOException
   :outertype: DataSourceTransaction

   Rolls back the transaction.

   :throws DAOException: if unable to commit the transaction.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.dao.Transaction.rollback()`

