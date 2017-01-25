.. java:import:: java.util Properties

DAO
===

.. java:package:: hk.hku.cecid.piazza.commons.dao
   :noindex:

.. java:type:: public interface DAO

   The Data Access Object is the primary object of the DAO pattern. The Data Access Object abstracts the underlying data access implementation for the Business Object to enable transparent access to the data source. The Business Object also delegates data load and store operations to the Data Access Object.

   :author: Hugo Y. K. Lam

Methods
-------
create
^^^^^^

.. java:method:: public void create(DVO data) throws DAOException
   :outertype: DAO

   Creates the given DAO data, which is managed by this DAO, in the underlying data source.

   :param data: the DAO data.
   :throws DAOException: if unable to create the data.

createDVO
^^^^^^^^^

.. java:method:: public DVO createDVO()
   :outertype: DAO

   Creates a data value object for this DAO.

   :return: a new data value object for this DAO.

daoCreated
^^^^^^^^^^

.. java:method:: public void daoCreated() throws DAOException
   :outertype: DAO

   Invoked after the dao has been created successfully.

getFactory
^^^^^^^^^^

.. java:method:: public DAOFactory getFactory()
   :outertype: DAO

   Gets the DAO factory of this DAO.

   :return: the DAO factory.

getParameters
^^^^^^^^^^^^^

.. java:method:: public Properties getParameters()
   :outertype: DAO

   Gets the parameters of this DAO.

   :return: the parameters of this DAO.

getTransaction
^^^^^^^^^^^^^^

.. java:method:: public Transaction getTransaction() throws DAOException
   :outertype: DAO

   Gets the transaction of this DAO.

   :throws DAOException:
   :return: the transaction of this DAO or null if there is none.

persist
^^^^^^^

.. java:method:: public boolean persist(DVO data) throws DAOException
   :outertype: DAO

   Persists the given DAO data, which is managed by this DAO, to the underlying data source.

   :param data: the DAO data.
   :throws DAOException: if unable to persist the data.
   :throws ClassCastException: if the DAO data is not DataSourceDVO.
   :return: true if the data is found and persisted.

remove
^^^^^^

.. java:method:: public boolean remove(DVO data) throws DAOException
   :outertype: DAO

   Removes the given DAO data, which is managed by this DAO, from the underlying data source.

   :param data: the DAO data.
   :throws DAOException: if unable to remove the data.
   :return: true if the data is found and removed.

retrieve
^^^^^^^^

.. java:method:: public boolean retrieve(DVO data) throws DAOException
   :outertype: DAO

   Retrieves the given DAO data, which is managed by this DAO, from the underlying data source.

   :param data: the DAO data.
   :throws DAOException: if unable to retrieve the data.
   :throws ClassCastException: if the DAO data is not DataSourceDVO.
   :return: true if the data is found and retrieved.

setTransaction
^^^^^^^^^^^^^^

.. java:method:: public void setTransaction(Transaction transaction) throws DAOException
   :outertype: DAO

   Sets a transaction to this DAO.

   :param transaction: the transaction of this DAO.
   :throws DAOException: if the transaction is not supported by this DAO.

