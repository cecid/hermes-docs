.. java:import:: java.sql Timestamp

.. java:import:: java.text DecimalFormat

.. java:import:: java.text SimpleDateFormat

.. java:import:: java.util Date

.. java:import:: java.util TimeZone

.. java:import:: java.util Calendar

.. java:import:: java.util.regex Pattern

.. java:import:: java.util.regex Matcher

.. java:import:: java.util Locale

.. java:import:: hk.hku.cecid.piazza.commons.util DataFormatter

.. java:import:: hk.hku.cecid.piazza.commons.util UtilitiesException

EbmsUtility
===========

.. java:package:: hk.hku.cecid.ebms.spa
   :noindex:

.. java:type:: public class EbmsUtility

   An utility for converting from java datetime to UTC conformed datetime and vice versa.

   ..

   #. Fixed a bug that it parses UTC datetime with 'Z' timezone incorrectly becasue it used wrong timezone (GMT, but not UTC). (Thank Martin Kalen for figure out this)
   #. Added datetime / calendar two UTC convertion.

   :author: Twinsen Tsang, (modifier Philip Wong)

Methods
-------
GMT2Calender
^^^^^^^^^^^^

.. java:method:: public static Calendar GMT2Calender(String dateTime) throws UtilitiesException
   :outertype: EbmsUtility

   Convert an GMT representation of string \ ``dateTime``\  to java calendar object.

   :param dateTime: A string representing a GMT datetime.
   :throws UtilitiesException: When unable to convert the dateTime format.
   :return: The millisecond representing the \ ``dateTime``\

GMT2Date
^^^^^^^^

.. java:method:: public static Date GMT2Date(String dateTime) throws UtilitiesException
   :outertype: EbmsUtility

   Convert an GMT representation of string \ ``dateTime``\  to java Date object.

   :param dateTime: A string representing a GMT datetime.
   :throws UtilitiesException: When unable to convert the dateTime format.
   :return: A java date object representing the \ ``dateTime``\

GMT2MS
^^^^^^

.. java:method:: public static long GMT2MS(String dateTime) throws UtilitiesException
   :outertype: EbmsUtility

   Convert an GMT representation of string \ ``dateTime``\  to millisecond.

   :param dateTime: A string representing a GMT datetime.
   :throws UtilitiesException: When unable to convert the dateTime format.
   :return: The millisecond representing the \ ``dateTime``\

GMT2Timestamp
^^^^^^^^^^^^^

.. java:method:: public static Timestamp GMT2Timestamp(String dateTime) throws UtilitiesException
   :outertype: EbmsUtility

   Convert an GMT representation of string \ ``dateTime``\  to java Timestamp object.

   :param dateTime: A string representing a GMT datetime.
   :throws UtilitiesException: When unable to convert the dateTime format.
   :return: A java timestamp object representing the \ ``dateTime``\

UTC2Calendar
^^^^^^^^^^^^

.. java:method:: public static Calendar UTC2Calendar(String dateTime) throws UtilitiesException
   :outertype: EbmsUtility

   Convert an UTC representation of string \ ``dateTime``\  to java calendar object. Followings are UTC conformed patterns:

   ..

   * 2007-07-16T13:24:56
   *
   * 2007-07-16T13:24:56Z
   *
   * 2007-07-16T13:24:56.789
   *
   * 2007-07-16T13:24:56.789Z
   *
   * 2007-07-16T13:24:56+02:00
   *
   * 2007-07-16T13:24:56-02:00
   *
   * 2007-07-16T13:24:56.789+02:00
   *
   * 2007-07-16T13:24:56.789-02:00
   *

   :param dateTime: A string representing a UTC datetime.
   :throws UtilitiesException: When unable to convert the dateTime format.
   :return: A java clendar object representing the \ ``dateTime``\

UTC2Date
^^^^^^^^

.. java:method:: public static Date UTC2Date(String dateTime) throws UtilitiesException
   :outertype: EbmsUtility

   Convert an UTC representation of string \ ``dateTime``\  to java Date object. Followings are UTC conformed patterns:

   ..

   * 2007-07-16T13:24:56
   *
   * 2007-07-16T13:24:56Z
   *
   * 2007-07-16T13:24:56.789
   *
   * 2007-07-16T13:24:56.789Z
   *
   * 2007-07-16T13:24:56+02:00
   *
   * 2007-07-16T13:24:56-02:00
   *
   * 2007-07-16T13:24:56.789+02:00
   *
   * 2007-07-16T13:24:56.789-02:00
   *

   :param dateTime: A string representing a UTC datetime.
   :throws UtilitiesException: When unable to convert the dateTime format.
   :return: A java date object representing the \ ``dateTime``\ .

UTC2MS
^^^^^^

.. java:method:: public static long UTC2MS(String dateTime) throws UtilitiesException
   :outertype: EbmsUtility

   Convert an UTC representation of string \ ``dateTime``\  to millisecond. Followings are UTC conformed patterns:

   ..

   * 2007-07-16T13:24:56
   *
   * 2007-07-16T13:24:56Z
   *
   * 2007-07-16T13:24:56.789
   *
   * 2007-07-16T13:24:56.789Z
   *
   * 2007-07-16T13:24:56+02:00
   *
   * 2007-07-16T13:24:56-02:00
   *
   * 2007-07-16T13:24:56.789+02:00
   *
   * 2007-07-16T13:24:56.789-02:00
   *

   :param dateTime: A string representing a UTC datetime.
   :throws UtilitiesException: When unable to convert the dateTime format.
   :return: The millisecond representing by \ ``dateTime``\ .

UTC2Timestamp
^^^^^^^^^^^^^

.. java:method:: public static Timestamp UTC2Timestamp(String dateTime) throws UtilitiesException
   :outertype: EbmsUtility

   Convert an UTC representation of string \ ``dateTime``\  to java Timestamp object. Followings are UTC conformed patterns:

   ..

   * 2007-07-16T13:24:56
   *
   * 2007-07-16T13:24:56Z
   *
   * 2007-07-16T13:24:56.789
   *
   * 2007-07-16T13:24:56.789Z
   *
   * 2007-07-16T13:24:56+02:00
   *
   * 2007-07-16T13:24:56-02:00
   *
   * 2007-07-16T13:24:56.789+02:00
   *
   * 2007-07-16T13:24:56.789-02:00
   *

   :param dateTime: A string representing a UTC datetime.
   :throws UtilitiesException: When unable to convert the dateTime format.
   :return: A java timestamp object representing the \ ``dateTime``\ .

calendar2UTC
^^^^^^^^^^^^

.. java:method:: public static String calendar2UTC(Calendar dateTime) throws UtilitiesException
   :outertype: EbmsUtility

   Convert a calendar \ ``dateTime``\  to UTC conformed representation of string.

   :param dateTime: A java calendar representing the time you want to convert.
   :throws UtilitiesException: When unable to convert the \ ``dateTime``\  to UTC.
   :return: an UTC conformed representation with time specified by \ ``dateTime``\

date2UTC
^^^^^^^^

.. java:method:: public static String date2UTC(Date dateTime, TimeZone timeZone) throws UtilitiesException
   :outertype: EbmsUtility

   Convert a date \ ``dateTime``\  to UTC conformed representation of string. (e.g. 2007-07-16T13:24:56.789+13:00)

   :param dateTime: A java date representing the time you want to convert.
   :param timeZone: The timezone of the \ ``dateTime``\ . If it is null, it use the default timezone in the machine.
   :throws UtilitiesException: When unable to convert the \ ``dateTime``\  to UTC.
   :return: an UTC conformed representation with time specified by \ ``dateTime``\

getCurrentUTCDateTime
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static String getCurrentUTCDateTime()
   :outertype: EbmsUtility

   :return: Get the current datetime with respect to the default timezone in UTC conformed representation.

