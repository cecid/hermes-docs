.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: java.sql PreparedStatement

DataSourceUpdate
================

.. java:package:: hk.hku.cecid.piazza.commons.dao.ds
   :noindex:

.. java:type::  class DataSourceUpdate extends DataSourceProcess

   DataSourceUpdate is a data source DAO process which handles a SQL update process.

   :author: Hugo Y. K. Lam

Constructors
------------
DataSourceUpdate
^^^^^^^^^^^^^^^^

.. java:constructor::  DataSourceUpdate(DataSourceDAO dao, DataSourceTransaction transaction, String sql, Object[][] params)
   :outertype: DataSourceUpdate

   Creates a new instance of DataSourceUpdate.

   :param dao: the DAO to which this process correspond.
   :param transaction: the transaction for this process.
   :param sql: the SQL update statement.
   :param params: the parameter values used by the specified SQL statement. The number, format, and sequence of the parameter values should match the statement. null if there is no parameter for the statement and multiple sets if it is a batch update.

Methods
-------
doTransaction
^^^^^^^^^^^^^

.. java:method:: protected void doTransaction(DataSourceTransaction tx) throws DAOException
   :outertype: DataSourceUpdate

   Executes the update and stores the result as an array of integers which indicates the update results.

   :throws DAOException: if unable to execute the update.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.dao.ds.DataSourceProcess.doTransaction(DataSourceTransaction)`

