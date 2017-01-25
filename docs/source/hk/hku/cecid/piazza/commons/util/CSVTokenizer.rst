.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: java.io IOException

.. java:import:: java.io Reader

.. java:import:: java.util ArrayList

.. java:import:: java.util StringTokenizer

.. java:import:: java.util.regex Matcher

.. java:import:: java.util.regex Pattern

CSVTokenizer
============

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public class CSVTokenizer

   CSVTokenizer is a tokenizer which can parses a given CSV and represent its content as multiple rows and columns.

   :author: Hugo Y. K. Lam

Constructors
------------
CSVTokenizer
^^^^^^^^^^^^

.. java:constructor:: public CSVTokenizer(Reader csv) throws IOException
   :outertype: CSVTokenizer

   Creates a new instance of CSVTokenizer.

   :param csv: the CSV content.
   :throws IOException: if unable to read the content from the given reader.

CSVTokenizer
^^^^^^^^^^^^

.. java:constructor:: public CSVTokenizer(String csv)
   :outertype: CSVTokenizer

   Creates a new instance of CSVTokenizer.

   :param csv: the CSV content.

Methods
-------
getColumn
^^^^^^^^^

.. java:method:: public String getColumn(int pos)
   :outertype: CSVTokenizer

   Gets a column's value.

   :param pos: the position of the column.
   :return: the specified column's value.

getColumnCount
^^^^^^^^^^^^^^

.. java:method:: public int getColumnCount()
   :outertype: CSVTokenizer

   Gets the number of columns in the current row.

   :return: the number of columns.

hasMoreRows
^^^^^^^^^^^

.. java:method:: public boolean hasMoreRows()
   :outertype: CSVTokenizer

   Checks if there are any more rows in this tokenizer.

   :return: true if there are more rows in this tokenizer.

nextRow
^^^^^^^

.. java:method:: public void nextRow()
   :outertype: CSVTokenizer

   Proceeds to tokenize the next row.

