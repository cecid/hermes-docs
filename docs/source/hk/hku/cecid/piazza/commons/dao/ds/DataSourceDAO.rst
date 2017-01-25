.. java:import:: hk.hku.cecid.piazza.commons.dao DAO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOFactory

.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

.. java:import:: hk.hku.cecid.piazza.commons.dao Transaction

.. java:import:: java.util ArrayList

.. java:import:: java.util Arrays

.. java:import:: java.util Enumeration

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: java.util Map

.. java:import:: java.util Properties

DataSourceDAO
=============

.. java:package:: hk.hku.cecid.piazza.commons.dao.ds
   :noindex:

.. java:type:: public abstract class DataSourceDAO implements DAO

   The abstract DataSourceDAO class encapsulates a DataSourceDAOFactory object. It basically provides methods, such as getTransaction() and createTransaction(), for any subclasses to get or create a transaction for accessing the underlying data source. It also provides some convenient methods for the subclasses to access, like querying and updating, the data source.

   When using the convenient methods, some basic parameters need to be defined. The parameters should be stored in the Properties object which can be retrieved by calling getProperties().

   The key-value pairs of the parameters must be in the following format:

   +----------------------------------------+------------------------------+-------------------------------------+
   | \ **Key**\                             | \ **Value**\                 | \ **Used by**\                      |
   +----------------------------------------+------------------------------+-------------------------------------+
   | finder:key                             | The key finder SQL statement | findByKey()                         |
   +----------------------------------------+------------------------------+-------------------------------------+
   | finder: \ *{alias name}*\              | The finder SQL statement     | find()                              |
   +----------------------------------------+------------------------------+-------------------------------------+
   | column: \ *{name in the data source}*\ | The column's key in the DVO  | getColumnCodeName(), executeQuery() |
   +----------------------------------------+------------------------------+-------------------------------------+
   | sql: \ *{alias name}*\                 | The SQL statement            | getSQL(), update()                  |
   +----------------------------------------+------------------------------+-------------------------------------+

   :author: Hugo Y. K. Lam

Constructors
------------
DataSourceDAO
^^^^^^^^^^^^^

.. java:constructor:: protected DataSourceDAO()
   :outertype: DataSourceDAO

   Creates a new instance of DataSourceDAO.

Methods
-------
create
^^^^^^

.. java:method:: public void create(DVO data) throws DAOException
   :outertype: DataSourceDAO

   Creates the given value object in the data source.

   :param data: the value object.
   :throws DAOException: if unable to create the data.
   :throws ClassCastException: if the value object is not DataSourceDVO.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.dao.DAO.create(hk.hku.cecid.piazza.commons.dao.DVO)`

createTransaction
^^^^^^^^^^^^^^^^^

.. java:method:: protected DataSourceTransaction createTransaction() throws DAOException
   :outertype: DataSourceDAO

   Creates a new DataSourceTransaction object from the underlying data source factory.

   :throws DAOException: if unable to create the transaction.
   :return: a new DataSourceTransaction object.

daoCreated
^^^^^^^^^^

.. java:method:: public void daoCreated()
   :outertype: DataSourceDAO

   Initializes this DAO.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.dao.DAO.daoCreated()`

executeQuery
^^^^^^^^^^^^

.. java:method:: protected List executeQuery(String sql) throws DAOException
   :outertype: DataSourceDAO

   Executes a SQL query on the data source and returns a List of DVO which matches.

   :param sql: the SQL query statement.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a List of DVO resulted from the specified SQL query. An empty List will be returned if there is no matching data.

executeQuery
^^^^^^^^^^^^

.. java:method:: protected List executeQuery(DataSourceTransaction tx, String sql) throws DAOException
   :outertype: DataSourceDAO

   Executes a SQL query on the data source and returns a List of DVO which matches.

   :param tx: the DataSourceTransaction to be used in execution.
   :param sql: the SQL query statement.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a List of DVO resulted from the specified SQL query. An empty List will be returned if there is no matching data.

executeQuery
^^^^^^^^^^^^

.. java:method:: protected List executeQuery(String sql, Object[] paras) throws DAOException
   :outertype: DataSourceDAO

   Executes a SQL query on the data source and returns a List of DVO which matches.

   :param sql: the SQL query statement.
   :param paras: the parameter values used by the specified SQL statement. The number, format, and sequence of the parameter values should match the statement. null if there is no parameter for the statement.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a List of DVO resulted from the specified SQL query. An empty List will be returned if there is no matching data.

executeQuery
^^^^^^^^^^^^

.. java:method:: protected List executeQuery(DataSourceTransaction tx, String sql, Object[] paras) throws DAOException
   :outertype: DataSourceDAO

   Executes a SQL query on the data source and returns a List of DVO which matches.

   :param tx: the DataSourceTransaction to be used in execution.
   :param sql: the SQL query statement.
   :param paras: the parameter values used by the specified SQL statement. The number, format, and sequence of the parameter values should match the statement. null if there is no parameter for the statement.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a List of DVO resulted from the specified SQL query. An empty List will be returned if there is no matching data.

executeRawQuery
^^^^^^^^^^^^^^^

.. java:method:: protected List executeRawQuery(String sql, Object[] paras) throws DAOException
   :outertype: DataSourceDAO

   Executes a SQL query on the data source and returns a List of raw data which matches.

   :param sql: the SQL query statement.
   :param paras: the parameter values used by the specified SQL statement. The number, format, and sequence of the parameter values should match the statement. null if there is no parameter for the statement.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a List of DVO resulted from the specified SQL query. An empty List will be returned if there is no matching data.

executeRawQuery
^^^^^^^^^^^^^^^

.. java:method:: protected List executeRawQuery(DataSourceTransaction tx, String sql, Object[] paras) throws DAOException
   :outertype: DataSourceDAO

   Executes a SQL query on the data source and returns a List of raw data which matches.

   :param tx: the DataSourceTransaction to be used in execution.
   :param sql: the SQL query statement.
   :param paras: the parameter values used by the specified SQL statement. The number, format, and sequence of the parameter values should match the statement. null if there is no parameter for the statement.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a List of DVO resulted from the specified SQL query. An empty List will be returned if there is no matching data.

executeUpdate
^^^^^^^^^^^^^

.. java:method:: protected int executeUpdate(String sql) throws DAOException
   :outertype: DataSourceDAO

   Executes a SQL update on the data source and returns an integer indicating the update result.

   :param sql: the SQL update statement.
   :throws DAOException: if errors found when updating data to the data source.
   :return: an integer indicating the update results. Same as the value returned by java.sql.Statement.executeUpdate().

executeUpdate
^^^^^^^^^^^^^

.. java:method:: protected int executeUpdate(DataSourceTransaction tx, String sql) throws DAOException
   :outertype: DataSourceDAO

   Executes a SQL update on the data source and returns an integer indicating the update result.

   :param tx: the DataSourceTransaction to be used in execution.
   :param sql: the SQL update statement.
   :throws DAOException: if errors found when updating data to the data source.
   :return: an integer indicating the update results. Same as the value returned by java.sql.Statement.executeUpdate().

executeUpdate
^^^^^^^^^^^^^

.. java:method:: protected int executeUpdate(String sql, Object[] paras) throws DAOException
   :outertype: DataSourceDAO

   Executes a SQL update on the data source and returns an integer indicating the update result.

   :param sql: the SQL update statement.
   :param paras: the parameter values used by the specified SQL statement. The number, format, and sequence of the parameter values should match the statement. null if there is no parameter for the statement.
   :throws DAOException: if errors found when updating data to the data source.
   :return: an integer indicating the update results. Same as the value returned by java.sql.Statement.executeUpdate().

executeUpdate
^^^^^^^^^^^^^

.. java:method:: protected int executeUpdate(DataSourceTransaction tx, String sql, Object[] paras) throws DAOException
   :outertype: DataSourceDAO

   Executes a SQL update on the data source and returns an integer indicating the update result.

   :param tx: the DataSourceTransaction to be used in execution.
   :param sql: the SQL update statement.
   :param paras: the parameter values used by the specified SQL statement. The number, format, and sequence of the parameter values should match the statement. null if there is no parameter for the statement.
   :throws DAOException: if errors found when updating data to the data source.
   :return: an integer indicating the update results. Same as the value returned by java.sql.Statement.executeUpdate()

executeUpdate
^^^^^^^^^^^^^

.. java:method:: protected int[] executeUpdate(String sql, Object[][] paras) throws DAOException
   :outertype: DataSourceDAO

   Executes a SQL update on the data source and returns an array of integers indicating the update results.

   :param sql: the SQL update statement.
   :param paras: the parameter values used by the specified SQL statement. The number, format, and sequence of the parameter values should match the statement. null if there is no parameter for the statement and multiple sets if it is a batch update.
   :throws DAOException: if errors found when updating data to the data source.
   :return: an array of integers indicating the update results. Same as the value returned by java.sql.Statement.executeUpdate().

executeUpdate
^^^^^^^^^^^^^

.. java:method:: protected int[] executeUpdate(DataSourceTransaction tx, String sql, Object[][] paras) throws DAOException
   :outertype: DataSourceDAO

   Executes a SQL update on the data source and returns an array of integers indicating the update results.

   :param tx: the DataSourceTransaction to be used in execution.
   :param sql: the SQL update statement.
   :param paras: the parameter values used by the specified SQL statement. The number, format, and sequence of the parameter values should match the statement. null if there is no parameter for the statement and multiple sets if it is a batch update.
   :throws DAOException: if errors found when updating data to the data source.
   :return: an array of integers indicating the update results. Same as the value returned by java.sql.Statement.executeUpdate().

find
^^^^

.. java:method:: protected List find(String finder, Object[] paras) throws DAOException
   :outertype: DataSourceDAO

   Retrieves data from the data source as a List of DVO by searching with the specified data values.

   :param finder: the name of the finder SQL statement.
   :param paras: the parameter values used by the finder statement.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a List of DVO found by the specified data values. An empty List will be returned if there is no matching data.

findByKey
^^^^^^^^^

.. java:method:: protected DVO findByKey(Object[] keys) throws DAOException
   :outertype: DataSourceDAO

   Retrieves data from the data source by searching with the specified key values.

   :param keys: the key values for querying the data source.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a DVO found by the specified key values. If there are more than one DVO found, the first one will be returned. null will be returned if nothing was found.

getColumnCodeName
^^^^^^^^^^^^^^^^^

.. java:method:: protected String getColumnCodeName(String name)
   :outertype: DataSourceDAO

   Gets the code name of the specified column in the data source.

   :param name: the name of the column.
   :return: the code name of the specified column.

getFactory
^^^^^^^^^^

.. java:method:: public DAOFactory getFactory()
   :outertype: DataSourceDAO

   Gets the DAO factory of this DAO.

   :return: the DAO factory.

getFilter
^^^^^^^^^

.. java:method:: protected String getFilter(String name)
   :outertype: DataSourceDAO

   Gets the filter partial SQL statement with the specified name.

   :param name: the name which refers to the filter partial SQL statement.
   :return: the filter partial SQL statement associated with the specified name.

getFinder
^^^^^^^^^

.. java:method:: protected String getFinder(String name)
   :outertype: DataSourceDAO

   Gets the finder SQL statement with the specified name.

   :param name: the name which refers to the finder SQL statement.
   :return: the finder SQL statement associated with the specified name.

getOrder
^^^^^^^^

.. java:method:: protected String getOrder(String name)
   :outertype: DataSourceDAO

   Gets the order partial SQL statement with the specified name.

   :param name: the name which refers to the order partial SQL statement.
   :return: the order partial SQL statement associated with the specified name.

getParameters
^^^^^^^^^^^^^

.. java:method:: public Properties getParameters()
   :outertype: DataSourceDAO

   Gets the parameters of this DAO.

   :return: a Properties which stored the parameters for this DAO.

getSQL
^^^^^^

.. java:method:: protected String getSQL(String name)
   :outertype: DataSourceDAO

   Gets the SQL statement with the specified name.

   :param name: the name which refers to the SQL statement.
   :return: the SQL statement associated with the specified name.

getTransaction
^^^^^^^^^^^^^^

.. java:method:: public Transaction getTransaction() throws DAOException
   :outertype: DataSourceDAO

   Gets the transaction of this DAO. This method returns null if this DAO is not under a transaction.

   :throws DAOException: if unable to get the transaction.
   :return: the transaction of this DAO.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.dao.DAO.getTransaction()`

getTransaction
^^^^^^^^^^^^^^

.. java:method:: protected DataSourceTransaction getTransaction(boolean create) throws DAOException
   :outertype: DataSourceDAO

   Gets the transaction of this DAO. This method returns a new transaction if and only if this DAO is not under a transaction and the create parameter is set to true. Notice that a newly created transaction will not be set as the transaction of this DAO. It is only created for convenience of use.

   :param create: true if a new transaction should be created if this DAO is not under a transaction.
   :throws DAOException: if unable get or create a transaction.
   :return: the transaction of this DAO or a new transaction.

isUnderTransaction
^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isUnderTransaction()
   :outertype: DataSourceDAO

   Checks if this DAO is under a transaction.

   :return: true if this DAO is under a transaction.

persist
^^^^^^^

.. java:method:: public boolean persist(DVO data) throws DAOException
   :outertype: DataSourceDAO

   Persists the given value object to the data source.

   :param data: the value object.
   :throws DAOException: if unable to persist the data.
   :throws ClassCastException: if the DAO data is not DataSourceDVO.
   :return: true if the data is found and persisted.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.dao.DAO.persist(hk.hku.cecid.piazza.commons.dao.DVO)`

remove
^^^^^^

.. java:method:: public boolean remove(DVO data) throws DAOException
   :outertype: DataSourceDAO

   Removes the given value object from the data source.

   :param data: the value object.
   :throws DAOException: if unable to remove the data.
   :throws ClassCastException: if the value object is not DataSourceDVO.
   :return: true if the data is found and removed.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.dao.DAO.remove(hk.hku.cecid.piazza.commons.dao.DVO)`

retrieve
^^^^^^^^

.. java:method:: public boolean retrieve(DVO data) throws DAOException
   :outertype: DataSourceDAO

   Retrieves the given value object from the data source.

   :param data: the value object.
   :throws DAOException: if unable to retrieve the data.
   :throws ClassCastException: if the value object is not DataSourceDVO.
   :return: true if the data is found and retrieved.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.dao.DAO.retrieve(hk.hku.cecid.piazza.commons.dao.DVO)`

setFactory
^^^^^^^^^^

.. java:method::  void setFactory(DataSourceDAOFactory factory)
   :outertype: DataSourceDAO

   Sets the DAO factory of this DAO.

   :param factory: the DAO factory.

setTransaction
^^^^^^^^^^^^^^

.. java:method:: public void setTransaction(Transaction tx) throws DAOException
   :outertype: DataSourceDAO

   Sets the transaction of this DAO.

   :param tx: the transaction of this DAO.
   :throws DAOException: if the given transaction is not supported.

update
^^^^^^

.. java:method:: protected int update(String sqlname, Object[] paras) throws DAOException
   :outertype: DataSourceDAO

   Updates the data source with the specified data values.

   :param sqlname: the name of the SQL statement to be used.
   :param paras: the data values to be updated to the data source.
   :throws DAOException: if errors found when updating data to the data source.
   :return: an integer indicating the update result. Same as the value returned by java.sql.Statement.executeUpdate()

