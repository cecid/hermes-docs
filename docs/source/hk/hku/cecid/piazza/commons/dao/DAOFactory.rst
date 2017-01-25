.. java:import:: hk.hku.cecid.piazza.commons.module Component

.. java:import:: hk.hku.cecid.piazza.commons.util Instance

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: java.net URL

.. java:import:: java.util Properties

DAOFactory
==========

.. java:package:: hk.hku.cecid.piazza.commons.dao
   :noindex:

.. java:type:: public abstract class DAOFactory extends Component

   The DAO pattern can be made highly flexible by adopting the Abstract Factory and the Factory Method Patterns.

   The Factory Method pattern can be used to produce a number of DAOs needed by the application when the underlying storage is not subject to change from one implementation to another. When it is subject to change, the Abstract Factory pattern can in turn build on and use the Factory Method Implementation. In this case, it provides an abstract DAO factory object that can construct various types of concrete DAO factories, each factory supporting a different type of persistent storage implementation. Once you obtain the concrete DAO factory for a specific implementation, you use it to produce DAOs supported and implemented in that implementation.

   :author: Hugo Y. K. Lam

Constructors
------------
DAOFactory
^^^^^^^^^^

.. java:constructor:: protected DAOFactory()
   :outertype: DAOFactory

   Creates a new instance of DAOFactory.

Methods
-------
createDAO
^^^^^^^^^

.. java:method:: public DAO createDAO(Class inf) throws DAOException
   :outertype: DAOFactory

   Creates a new DAO.

   :param inf: the DAO interface class.
   :throws DAOException: if there is any problem in looking up the DAO with the interface specified.
   :return: the DAO retrieved by the interface specified.

createDAO
^^^^^^^^^

.. java:method:: public DAO createDAO(String daoname) throws DAOException
   :outertype: DAOFactory

   Creates a new DAO.

   :param daoname: the DAO name.
   :throws DAOException: if there is any problem in looking up the DAO with the name specified.
   :return: the DAO retrieved by the name specified.

   **See also:** :java:ref:`.initDAO(DAO)`

createDAOFactory
^^^^^^^^^^^^^^^^

.. java:method:: public static DAOFactory createDAOFactory(String name, String provider, Properties params, ClassLoader loader) throws DAOException
   :outertype: DAOFactory

   Creates a DAO Factory.

   :param name: the DAO Factory name.
   :param provider: the provider of the DAO Factory.
   :param params: the parameters for creating the DAO Factory.
   :param loader: the class loader for loading the factory class.
   :throws DAOException: if there is any error when creating the DAO Factory using the specified parameters.
   :return: the DAO Factory created by the parameters specified.

createTransaction
^^^^^^^^^^^^^^^^^

.. java:method:: public Transaction createTransaction() throws DAOException
   :outertype: DAOFactory

   Creates a new transaction.

   :throws DAOException: if unable to create a new transaction.
   :return: a new transaction.

getParameter
^^^^^^^^^^^^

.. java:method:: protected String getParameter(String key) throws DAOException
   :outertype: DAOFactory

   Gets a parameter from the parameters of this DAOFactory.

   :param key: the parameter key.
   :throws DAOException: if there is no parameter matching the specified key.
   :return: the parameter value associated with the specified key.

getParameter
^^^^^^^^^^^^

.. java:method:: protected String getParameter(String key, String def)
   :outertype: DAOFactory

   Gets a parameter from the parameters of this DAOFactory.

   :param key: the parameter key.
   :param def: the default value.
   :return: the parameter value associated with the specified key. The default value will be returned if there is no parameter matching the specified key.

init
^^^^

.. java:method:: protected void init() throws DAOException
   :outertype: DAOFactory

   Initializes the DAO Factory.

   :throws DAOException: when there is any error in the initialization.

   **See also:** :java:ref:`.initFactory()`

initDAO
^^^^^^^

.. java:method:: protected abstract void initDAO(DAO dao) throws DAOException
   :outertype: DAOFactory

   Invoked by the createDAO() method for initializing the given DAO.

   :param dao: the DAO.
   :throws DAOException: if unable to initialize the DAO.

   **See also:** :java:ref:`.createDAO(Class)`, :java:ref:`.createDAO(String)`

initFactory
^^^^^^^^^^^

.. java:method:: protected abstract void initFactory() throws DAOException
   :outertype: DAOFactory

   Invoked by the init() method for initializing the implementing factory.

   :throws DAOException: if unable to initialize the factory.

   **See also:** :java:ref:`.init()`

