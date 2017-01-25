.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: java.io PrintWriter

.. java:import:: java.sql Connection

.. java:import:: java.sql DriverManager

.. java:import:: java.sql SQLException

.. java:import:: java.sql SQLFeatureNotSupportedException

.. java:import:: java.util.logging Logger

.. java:import:: javax.sql DataSource

.. java:import:: org.apache.commons.dbcp2.cpdsadapter DriverAdapterCPDS

.. java:import:: org.apache.commons.dbcp2.datasources SharedPoolDataSource

SimpleDSDAOFactory
==================

.. java:package:: hk.hku.cecid.piazza.commons.dao.ds
   :noindex:

.. java:type:: public class SimpleDSDAOFactory extends DataSourceDAOFactory

   SimpleDSDAOFactory is a subclass of DataSourceDAOFactory and provides an implementation for accessing the data source by a simple DataSource object which is backed by the DriverManager and provides no pooling.

   Notice that the DAO created by the createDAO() method shall be an instance of DataSourceDAO since this factory is a DataSourceDAOFactory.

   :author: Hugo Y. K. Lam

Constructors
------------
SimpleDSDAOFactory
^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SimpleDSDAOFactory()
   :outertype: SimpleDSDAOFactory

   Creates a new instance of SimpleDSDAOFactory.

Methods
-------
initFactory
^^^^^^^^^^^

.. java:method:: public void initFactory() throws DAOException
   :outertype: SimpleDSDAOFactory

   Initializes this DAOFactory.

