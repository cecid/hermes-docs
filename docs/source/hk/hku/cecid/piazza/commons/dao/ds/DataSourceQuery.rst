.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io InputStream

.. java:import:: java.sql PreparedStatement

.. java:import:: java.sql ResultSet

.. java:import:: java.sql ResultSetMetaData

.. java:import:: java.util ArrayList

.. java:import:: java.util Hashtable

.. java:import:: java.util List

DataSourceQuery
===============

.. java:package:: hk.hku.cecid.piazza.commons.dao.ds
   :noindex:

.. java:type::  class DataSourceQuery extends DataSourceProcess

   DataSourceQuery is a data source DAO process which handles a SQL query process.

   :author: Hugo Y. K. Lam

Constructors
------------
DataSourceQuery
^^^^^^^^^^^^^^^

.. java:constructor::  DataSourceQuery(DataSourceDAO dao, DataSourceTransaction transaction, String sql, Object[] params)
   :outertype: DataSourceQuery

   Creates a new instance of DataSourceQuery.

   :param dao: the DAO to which this process correspond.
   :param transaction: the transaction for this process.
   :param sql: the SQL query statement.
   :param params: the parameter values used by the specified SQL statement. The number, format, and sequence of the parameter values should match the statement. null if there is no parameter for the statement.

Methods
-------
doTransaction
^^^^^^^^^^^^^

.. java:method:: protected void doTransaction(DataSourceTransaction tx) throws DAOException
   :outertype: DataSourceQuery

   Executes the query and stores the result as a list of DataSourceDVO or raw data list.

   :throws DAOException: if unable to execute the query.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.dao.ds.DataSourceProcess.doTransaction(DataSourceTransaction)`

isRawResult
^^^^^^^^^^^

.. java:method:: public boolean isRawResult()
   :outertype: DataSourceQuery

   Checks if the result data is in raw format.

   :return: true if the result data is in raw format.

   **See also:** :java:ref:`.setRawResult(boolean)`

setRawResult
^^^^^^^^^^^^

.. java:method:: public void setRawResult(boolean isRawResult)
   :outertype: DataSourceQuery

   Sets whether the result data should be in raw format. If true, the result data will be a list of DataSourceDVO. Otherwise, it will be a list of list which contains the data values in order with the query.

   :param isRawResult: true if the result data should be in raw format.

