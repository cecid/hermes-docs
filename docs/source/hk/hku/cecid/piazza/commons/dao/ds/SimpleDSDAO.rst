.. java:import:: java.util List

.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

SimpleDSDAO
===========

.. java:package:: hk.hku.cecid.piazza.commons.dao.ds
   :noindex:

.. java:type:: public class SimpleDSDAO extends DataSourceDAO

   SimpleDSDAO is a concrete subclass of DataSourceDAO which provides some convenient methods for querying and updating its underlying data source. It should not be used directly when the underlying persistent storage would be changed to any kind that does not support Java DataSource.

   :author: Hugo Y. K. Lam

Constructors
------------
SimpleDSDAO
^^^^^^^^^^^

.. java:constructor:: public SimpleDSDAO()
   :outertype: SimpleDSDAO

   Creates a new instance of SimpleDSDAO.

Methods
-------
createDVO
^^^^^^^^^

.. java:method:: public DVO createDVO()
   :outertype: SimpleDSDAO

   Creates a new instance of SimpleDSDVO.

find
^^^^

.. java:method:: public SimpleDSDVO find(Object[] keys) throws DAOException
   :outertype: SimpleDSDAO

   Retrieves data from the data source by searching with the specified key values.

   :param keys: the key values for querying the data source. The number, format, and sequence of the parameter values should match the key finder statement.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a SimpleDSDVO found by the specified key values. If there are more than one DVO found, the first one will be returned. null will be returned if nothing was found.

find
^^^^

.. java:method:: public List find(String finder, Object[] paras) throws DAOException
   :outertype: SimpleDSDAO

   Retrieves data from the data source as a List of DVO by searching with the specified data values.

   :param finder: the name of the finder SQL statement.
   :param paras: the parameter values used by the specified finder statement. The number, format, and sequence of the parameter values should match the statement. null if there is no parameter for the statement.
   :throws DAOException: if errors found when retrieving data from the data source.
   :return: a List of SimpleDSDVO found by the specified data values. An empty List will be returned if there is no matching data.

update
^^^^^^

.. java:method:: public int update(String sqlname, Object[] paras) throws DAOException
   :outertype: SimpleDSDAO

   Update the data source with the specified data values.

   :param sqlname: the name of the SQL statement to be used.
   :param paras: the data values to be updated to the data source.
   :throws DAOException: if errors found when updating data to the data source.
   :return: an integer indicating the update result. Same as the value returned by java.sql.Statement.executeUpdate().

