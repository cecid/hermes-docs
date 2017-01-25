.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

SQLBuilder
==========

.. java:package:: hk.hku.cecid.piazza.commons.dao.ds
   :noindex:

.. java:type:: public class SQLBuilder

   SQLBuilder is a tool which can construct prepared SQL statements from the specified table, keys, and columns.

   :author: Hugo Y. K. Lam

Constructors
------------
SQLBuilder
^^^^^^^^^^

.. java:constructor:: public SQLBuilder(String table, String key, String[] columns)
   :outertype: SQLBuilder

   Creates a new instance of SQLBuilder.

   :param table: the table name.
   :param key: the comma delimited set of keys of the table.
   :param columns: the columns of the table.

SQLBuilder
^^^^^^^^^^

.. java:constructor:: public SQLBuilder(String table, String[] keys, String[] columns)
   :outertype: SQLBuilder

   Creates a new instance of SQLBuilder.

   :param table: the table name.
   :param keys: the keys of the table.
   :param columns: the columns of the table.

Methods
-------
getColumns
^^^^^^^^^^

.. java:method:: public String[] getColumns()
   :outertype: SQLBuilder

   Gets the columns.

   :return: the columns.

getDeleteStatement
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getDeleteStatement()
   :outertype: SQLBuilder

   Gets the DELETE statement.

   :return: the DELETE statement.

getInsertStatement
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getInsertStatement()
   :outertype: SQLBuilder

   Gets the INSERT statement.

   :return: the INSERT statement.

getInsertStatement
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getInsertStatement(String[] cols)
   :outertype: SQLBuilder

   Gets the INSERT statement.

   :param cols: the columns to be updated.
   :return: the INSERT statement.

getKeys
^^^^^^^

.. java:method:: public String[] getKeys()
   :outertype: SQLBuilder

   Gets the keys.

   :return: the keys.

getSelectStatement
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getSelectStatement()
   :outertype: SQLBuilder

   Gets the SELECT statement.

   :return: the SELECT statement.

getTable
^^^^^^^^

.. java:method:: public String getTable()
   :outertype: SQLBuilder

   Gets the table name.

   :return: the table name.

getUpdateStatement
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getUpdateStatement()
   :outertype: SQLBuilder

   Gets the UPDATE statement.

   :return: the UPDATE statement.

getUpdateStatement
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getUpdateStatement(String[] cols)
   :outertype: SQLBuilder

   Gets the UPDATE statement.

   :param cols: the columns to be updated.
   :return: the UPDATE statement.

isValid
^^^^^^^

.. java:method:: public boolean isValid()
   :outertype: SQLBuilder

   Checks if this SQL builder is valid. It is valid if and only if the table, columns, and keys have been defined.

   :return: true if this SQL builder is valid.

