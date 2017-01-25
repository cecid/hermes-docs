.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: java.io InputStream

.. java:import:: java.sql PreparedStatement

.. java:import:: java.sql SQLException

.. java:import:: java.util.regex Matcher

.. java:import:: java.util.regex Pattern

DataSourceProcess
=================

.. java:package:: hk.hku.cecid.piazza.commons.dao.ds
   :noindex:

.. java:type:: public abstract class DataSourceProcess

   DataSourceProcess represents a data source transaction process. Subclasses are required to implement the doTransaction() method for the transaction process.

   This process will only manage, for example commit or rollback, the transaction encapsulated if its DataSourceDAO is not under a transaction and it is not explicitly instructed, in construction, to use a specified transaction.

   :author: Hugo Y. K. Lam

Constructors
------------
DataSourceProcess
^^^^^^^^^^^^^^^^^

.. java:constructor:: public DataSourceProcess(DataSourceDAO dao)
   :outertype: DataSourceProcess

   Creates a new instance of DataSourceProcess.

   :param dao: the DAO to which this process correspond.

DataSourceProcess
^^^^^^^^^^^^^^^^^

.. java:constructor:: public DataSourceProcess(DataSourceDAO dao, DataSourceTransaction transaction)
   :outertype: DataSourceProcess

   Creates a new instance of DataSourceProcess.

   :param dao: the DAO to which this process correspond.
   :param transaction: the transaction in which this process should execute.

Methods
-------
doTransaction
^^^^^^^^^^^^^

.. java:method:: protected abstract void doTransaction(DataSourceTransaction tx) throws DAOException
   :outertype: DataSourceProcess

   Executes the transaction process.

   :param tx: the DataSourceTransaction object in which this process executes.
   :throws DAOException: if any error occurred in the execution.

getDAO
^^^^^^

.. java:method:: protected DataSourceDAO getDAO()
   :outertype: DataSourceProcess

   Gets the DAO to which this process correspond.

   :return: the DAO to which this process correspond.

getParameterCount
^^^^^^^^^^^^^^^^^

.. java:method:: protected int getParameterCount(PreparedStatement pStmt, String sql)
   :outertype: DataSourceProcess

   Counts the number of parameters required by the prepared statement. If a parameter meta data is not available, it counts the occurrences of '?' in the given SQL statement.

   :param pStmt: the prepared statement.
   :param sql: the SQL statement.
   :return: the numbder of parameters.

getResult
^^^^^^^^^

.. java:method:: public Object getResult()
   :outertype: DataSourceProcess

   Gets the result of this process.

   :return: the result of this process.

isCommitted
^^^^^^^^^^^

.. java:method:: public boolean isCommitted()
   :outertype: DataSourceProcess

   Checks if this process has committed the transaction.

   :return: true if this process has committed the transaction.

isRolledBack
^^^^^^^^^^^^

.. java:method:: public boolean isRolledBack()
   :outertype: DataSourceProcess

   Checks if this process has rolled back the transaction.

   :return: true if this process has rolled back the transaction.

isStarted
^^^^^^^^^

.. java:method:: public boolean isStarted()
   :outertype: DataSourceProcess

   Checks if this process has already been started.

   :return: true if the this process has already been started.

setParameter
^^^^^^^^^^^^

.. java:method:: protected void setParameter(PreparedStatement pStmt, int pos, Object param) throws SQLException
   :outertype: DataSourceProcess

   Sets a parameter to the prepared statement.

   :param pStmt: the prepared statement.
   :param pos: the position of the parameter.
   :param param: the parameter.
   :throws SQLException: if unable to set the parameter.

setResult
^^^^^^^^^

.. java:method:: protected void setResult(Object result)
   :outertype: DataSourceProcess

   Sets the result of this process.

   :param result: the result of this process.

start
^^^^^

.. java:method:: public synchronized void start() throws DAOException
   :outertype: DataSourceProcess

   Starts executing this process. A process can only be started if it has not yet been started.

   :throws DAOException: if there is any error in the execution or the process has already been started.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: DataSourceProcess

   Returns a string representation of this process.

   :return: a string representation of this process.

   **See also:** :java:ref:`java.lang.Object.toString()`

