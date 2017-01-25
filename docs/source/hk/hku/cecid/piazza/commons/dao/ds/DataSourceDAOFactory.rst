.. java:import:: hk.hku.cecid.piazza.commons.dao DAO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOFactory

.. java:import:: hk.hku.cecid.piazza.commons.dao Transaction

.. java:import:: javax.naming InitialContext

.. java:import:: javax.sql DataSource

DataSourceDAOFactory
====================

.. java:package:: hk.hku.cecid.piazza.commons.dao.ds
   :noindex:

.. java:type:: public class DataSourceDAOFactory extends DAOFactory

   The DataSourceDAOFactory has implemented the DAOFactory and provides an implementation for accessing the data source by Java DataSource. Notice that the DAO created by the createDAO() method is a DataSourceDAO object since this factory is a DataSourceDAOFactory.

   :author: Hugo Y. K. Lam

Constructors
------------
DataSourceDAOFactory
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public DataSourceDAOFactory()
   :outertype: DataSourceDAOFactory

   Creates a new instance of DataSourceDAOFactory.

Methods
-------
createTransaction
^^^^^^^^^^^^^^^^^

.. java:method:: public Transaction createTransaction() throws DAOException
   :outertype: DataSourceDAOFactory

   Creates a data source transaction.

   :throws TransactionException: if unable to create the data source transaction.
   :return: a new data source transaction.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.dao.DAOFactory.createTransaction()`

getDataSource
^^^^^^^^^^^^^

.. java:method:: protected DataSource getDataSource()
   :outertype: DataSourceDAOFactory

   Gets the underlying DataSource object.

   :return: the underlying DataSource object.

initDAO
^^^^^^^

.. java:method:: protected void initDAO(DAO dao) throws DAOException
   :outertype: DataSourceDAOFactory

   Initializes the given DAO.

   :param dao: the DAO.
   :throws DAOException: if unable to initialize the DAO.

initFactory
^^^^^^^^^^^

.. java:method:: public void initFactory() throws DAOException
   :outertype: DataSourceDAOFactory

   Initializes this DAOFactory.

setDataSource
^^^^^^^^^^^^^

.. java:method:: protected void setDataSource(DataSource source)
   :outertype: DataSourceDAOFactory

   Sets the underlying DataSource object.

   :param source: the underlying DataSource object.

