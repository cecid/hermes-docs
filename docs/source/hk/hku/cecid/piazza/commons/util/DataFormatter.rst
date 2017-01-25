.. java:import:: java.text DecimalFormat

.. java:import:: java.text SimpleDateFormat

.. java:import:: java.util Locale

.. java:import:: java.util Properties

DataFormatter
=============

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public final class DataFormatter

   DataFormatter is a convenient class for formatting objects into or from string. Objects like Date, Time, and Decimal will be formatted according to the following default patterns if none is specified or configured beforehand:

   ..

   * date-format: \ ``yyyyMMdd``\
   * time-format: \ ``HHmmss``\
   * datetime-format: \ ``yyyyMMddHHmmss``\
   * timestamp-format: \ ``yyyyMMddHHmmssSSS``\
   * timestamp-suffix: \ ``000``\
   * decimal-format: \ ``0.00``\

   :author: Hugo Y. K. Lam

Constructors
------------
DataFormatter
^^^^^^^^^^^^^

.. java:constructor:: public DataFormatter(Properties config)
   :outertype: DataFormatter

   Creates a new instance of DataFormatter.

   :param config: configuration properties of the data format.

Methods
-------
formatDate
^^^^^^^^^^

.. java:method:: public String formatDate(java.util.Date d)
   :outertype: DataFormatter

   Formats a java.util.Date value into a date String.

   :param d: The value to be formatted.
   :return: The String represenation of the value.

formatDate
^^^^^^^^^^

.. java:method:: public String formatDate(java.util.Date date, String pattern)
   :outertype: DataFormatter

   Formats a given java.util.Date into a String according to the specified pattern.

   :param date: The date to be formatted.
   :param pattern: The pattern to be followed in formatting.
   :return: The formatted String of the date.

formatDate
^^^^^^^^^^

.. java:method:: public String formatDate(java.util.Date date, String pattern, Locale locale)
   :outertype: DataFormatter

   Formats a given java.util.Date into a String according to the specified pattern.

   :param locale: The locale used in formatting.
   :param date: The date to be formatted.
   :param pattern: The pattern to be followed in formatting.
   :return: The formatted String of the date.

formatDateTime
^^^^^^^^^^^^^^

.. java:method:: public String formatDateTime(java.util.Date d)
   :outertype: DataFormatter

   Formats a java.util.Date value into a date-time String.

   :param d: The value to be formatted.
   :return: The String represenation of the value.

formatDecimal
^^^^^^^^^^^^^

.. java:method:: public String formatDecimal(double d)
   :outertype: DataFormatter

   Formats a double value into a String.

   :param d: The value to be formatted.
   :return: The String represenation of the value.

formatDecimal
^^^^^^^^^^^^^

.. java:method:: public String formatDecimal(double d, String pattern)
   :outertype: DataFormatter

   Formats a given double into a String according to the specified pattern.

   :param d: The double to be formatted.
   :param pattern: The pattern to be followed in formatting.
   :return: The formatted String of the double.

formatDecimal
^^^^^^^^^^^^^

.. java:method:: public String formatDecimal(Double d)
   :outertype: DataFormatter

   Formats a Double value into a String.

   :param d: The value to be formatted.
   :return: The String represenation of the value.

formatTime
^^^^^^^^^^

.. java:method:: public String formatTime(java.util.Date d)
   :outertype: DataFormatter

   Formats a java.util.Date value into a time String.

   :param d: The value to be formatted.
   :return: The String represenation of the value.

formatTimestamp
^^^^^^^^^^^^^^^

.. java:method:: public String formatTimestamp(java.util.Date d)
   :outertype: DataFormatter

   Formats a java.util.Date value into a timestamp String.

   :param d: The value to be formatted.
   :return: The String represenation of the value.

getInstance
^^^^^^^^^^^

.. java:method:: public static DataFormatter getInstance()
   :outertype: DataFormatter

   Gets a default instance of DataFormatter.

   :return: a default instance of DataFormatter.

parseDate
^^^^^^^^^

.. java:method:: public java.util.Date parseDate(String s)
   :outertype: DataFormatter

   Parses a date String and formats it into a java.util.Date object.

   :param s: The value to be parsed.
   :return: The Object represenation of the value.

parseDate
^^^^^^^^^

.. java:method:: public java.util.Date parseDate(String date, String pattern)
   :outertype: DataFormatter

   Parses a date string and returns a java.util.Date object.

   :param date: The date string to be parsed.
   :param pattern: The pattern of the date string.
   :return: A java.util.Date object that represents the given date string.

parseDate
^^^^^^^^^

.. java:method:: public java.util.Date parseDate(String date, String pattern, Locale locale)
   :outertype: DataFormatter

   Parses a date string and returns a java.util.Date object.

   :param date: The date string to be parsed.
   :param pattern: The pattern of the date string.
   :param locale: The locale used in parsing the date string.
   :return: A java.util.Date object that represents the given date string.

parseDateTime
^^^^^^^^^^^^^

.. java:method:: public java.util.Date parseDateTime(String s)
   :outertype: DataFormatter

   Parses a date-time String and formats it into a java.util.Date object.

   :param s: The value to be parsed.
   :return: The Object represenation of the value.

parseTime
^^^^^^^^^

.. java:method:: public java.util.Date parseTime(String s)
   :outertype: DataFormatter

   Parses a time String and formats it into a java.util.Date object.

   :param s: The value to be parsed.
   :return: The Object represenation of the value.

parseTimestamp
^^^^^^^^^^^^^^

.. java:method:: public java.util.Date parseTimestamp(String s)
   :outertype: DataFormatter

   Parses a timestamp String and formats it into a java.util.Date object.

   :param s: The value to be parsed.
   :return: The Object represenation of the value.

