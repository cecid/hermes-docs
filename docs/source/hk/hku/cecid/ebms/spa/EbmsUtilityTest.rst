.. java:import:: java.text DecimalFormat

.. java:import:: java.util Date

.. java:import:: java.util Calendar

.. java:import:: java.util TimeZone

.. java:import:: junit.framework TestCase

.. java:import:: hk.hku.cecid.ebms.spa EbmsUtility

EbmsUtilityTest
===============

.. java:package:: hk.hku.cecid.ebms.spa
   :noindex:

.. java:type:: public class EbmsUtilityTest extends TestCase

   The \ ``EbmsUtilityTest``\  is the testcase for \ ``EbmsUtility``\ .

   :author: Twinsen Tsang

Methods
-------
getLocalTimezone
^^^^^^^^^^^^^^^^

.. java:method:: public String getLocalTimezone()
   :outertype: EbmsUtilityTest

   Get the local timezone represenetation from the UTC. The returned format is "GMT+hh:mm".  For example, if you are located in Asia/Hong Kong, the returned string should be "GMT+08:00".

setUp
^^^^^

.. java:method:: public void setUp() throws Exception
   :outertype: EbmsUtilityTest

tearDown
^^^^^^^^

.. java:method:: public void tearDown() throws Exception
   :outertype: EbmsUtilityTest

testDate2UTC_Pos0
^^^^^^^^^^^^^^^^^

.. java:method:: public void testDate2UTC_Pos0() throws Exception
   :outertype: EbmsUtilityTest

   Test for converting from a java date object to UTC conformed representation string. Testing for the scenario the dateTime is represented as java calendar and under the timezone same as the machine running.

testDate2UTC_Pos1
^^^^^^^^^^^^^^^^^

.. java:method:: public void testDate2UTC_Pos1() throws Exception
   :outertype: EbmsUtilityTest

   Test for converting from a java date object to UTC conformed representation string. Testing for the scenario the dateTime is represented as java calendar and under the timezone under UTC.

testDate2UTC_Pos2
^^^^^^^^^^^^^^^^^

.. java:method:: public void testDate2UTC_Pos2() throws Exception
   :outertype: EbmsUtilityTest

   Test for converting from a java date object to UTC conformed representation string. Testing for the scenario the dateTime is represented as java calendar and under the timezone under GMT-12:00 (boundary case)

testDate2UTC_Pos3
^^^^^^^^^^^^^^^^^

.. java:method:: public void testDate2UTC_Pos3() throws Exception
   :outertype: EbmsUtilityTest

   Test for converting from a java date object to UTC conformed representation string. Testing for the scenario the dateTime is represented as java calendar and under the timezone under GMT+13:00 (boundary case)

testGMT2Date_Pos0
^^^^^^^^^^^^^^^^^

.. java:method:: public void testGMT2Date_Pos0() throws Exception
   :outertype: EbmsUtilityTest

   Test for converting from GMT datetime representation to java date object.

testGetCurrentUTCDateTime_Pos0
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testGetCurrentUTCDateTime_Pos0() throws Exception
   :outertype: EbmsUtilityTest

   :throws Exception:

testMartinKalenIssue1
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testMartinKalenIssue1() throws Exception
   :outertype: EbmsUtilityTest

   Test for the scenario issued by Martin Kalen from the google group. QUOTED FROM martin said:

   .. parsed-literal::

      Hermes sends ebMS ACK messages with a non-standard timezone part of
      the timestamp (timezone info is not according to ebXML-specification,
      see background below)

      Background on #1:
      The recent fix for Hermes UTC timestamps uses the Java
      SimpleDateFormat "Z"-pattern for timezone, which is unfortunately
      incompatible with the ebXML specification for time zone refering to
      the XML schema data-type "dateTime" specified here:
      http://www.w3.org/TR/xmlschema-2/#dateTime

      Snippets from the spec:
      "dateTime consists of finite-length sequences of characters of the
      form: '-'? yyyy '-' mm '-' dd 'T' hh ':' mm ':' ss ('.' s+)?
      (zzzzzz)?"
      "zzzzzz (if present) represents the timezone"

      From 3.2.7.3 Timezones The lexical representation of a timezone is a string of the form:
      (('+' | '-') hh ':' mm) | 'Z'"
      In Java the ':' character is missing between the "hh" and "mm" parts.
      More details on the Java SimpleDateFormat vs XSD dateTime
      incompatibility can be found here:

   Detail: http://groups.google.com/group/cecid-hermes2/browse_thread/thread/46cca8b51ca21524

testMartinKalenIssue2
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testMartinKalenIssue2() throws Exception
   :outertype: EbmsUtilityTest

   Test for the scenario issued by Martin Kalen from the google group.

   .. parsed-literal::

         I live in the UTC+02:00 timezone and today at 14:01 my time (=12:01
      UTC time) an incoming ebXML message with the following TTL timestamp
      was considered expired by Hermes: "2007-07-10T12:04:14Z".
      Without the change in EbmsUtility above, Hermes regards the incoming
      timestamp as 12:04 in my timezone which mutates the expected
      12:04:14UTC to 10:04:14UTC = incorrect expiry notification to the
      sender.

   Detail: http://groups.google.com/group/cecid-hermes2/browse_thread/thread/46cca8b51ca21524

testUTC2Calendar_Neg0
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testUTC2Calendar_Neg0() throws Exception
   :outertype: EbmsUtilityTest

   Test the conversation from UTC to java calendar object negatively. Testing for the scenario all invalid UTC format representation.

testUTC2Calendar_Pos0
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testUTC2Calendar_Pos0() throws Exception
   :outertype: EbmsUtilityTest

   Test the conversation from UTC to java calendar object. Testing for the scenario the dateTime is represented as UTC and under the timezone in UTC (GMT+00:00) using 'Z' designator.

testUTC2Calendar_Pos1
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testUTC2Calendar_Pos1() throws Exception
   :outertype: EbmsUtilityTest

   Test the conversation from UTC to java calendar object. Testing for the scenario the dateTime is represented as UTC and under the timezone in UTC (GMT+00:00) using +00:00

testUTC2Calendar_Pos2
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testUTC2Calendar_Pos2() throws Exception
   :outertype: EbmsUtilityTest

   Test the conversation from UTC to java calendar object. Testing for the scenario the dateTime is represented as UTC and under the timezone GMT+08:00 (non zero timezone)

testUTC2Calendar_Pos3
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testUTC2Calendar_Pos3() throws Exception
   :outertype: EbmsUtilityTest

   Test the conversation from UTC to java calendar object. Testing for the scenario the dateTime is represented as UTC and under the timezone GMT+13:00 (boundary case)

testUTC2Calendar_Pos4
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testUTC2Calendar_Pos4() throws Exception
   :outertype: EbmsUtilityTest

   Test the conversation from UTC to java calendar object. Testing for the scenario the dateTime is represented as UTC and under the timezone GMT-12:00 (boundary case)

testUTC2Calendar_Pos5
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testUTC2Calendar_Pos5() throws Exception
   :outertype: EbmsUtilityTest

   Test the conversation from UTC to java calendar object. Testing for the scenario the dateTime is represented as UTC without millisecond and under the timezone UTC.

testUTC2Calendar_Pos6
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testUTC2Calendar_Pos6() throws Exception
   :outertype: EbmsUtilityTest

   Test the conversation from UTC to java calendar object. Testing for the scenario the dateTime is represented as UTC without millisecond and under any timezone other than UTC.

testUTC2Calendar_Pos7
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testUTC2Calendar_Pos7() throws Exception
   :outertype: EbmsUtilityTest

   Test the conversation from UTC to java calendar object. Testing for the scenario the dateTime is represented as UTC without millisecond and 'Z' and under any timezone other than UTC.

testUTC2Calendar_Pos8
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testUTC2Calendar_Pos8() throws Exception
   :outertype: EbmsUtilityTest

   Test the conversation from UTC to java calendar object. Testing for the scenario the dateTime is represented as UTC with 'Z' and under any timezone other than UTC.

validateCalendar
^^^^^^^^^^^^^^^^

.. java:method:: public void validateCalendar(Calendar cal, int expectedYear, int expectedMonth, int expectedDay, int expectedHour, int expectedMins, int expectedSecond, int expectedMillisecond, String expectedTz)
   :outertype: EbmsUtilityTest

   A common method to validate cirtical field for specified \ ``cal``\

   :param cal: The calendar to test against.
   :param expectedYear: The expected year.
   :param expectedMonth: The expected month.
   :param expectedDay: The expected day.
   :param expectedHour: The expected hour.
   :param expectedMins: The expected mins.
   :param expectedSecond: The expected second.
   :param expectedMillisecond: The expected millisecond.
   :param expectedTz: The expected timezone.

validateCalendar
^^^^^^^^^^^^^^^^

.. java:method:: public void validateCalendar(Calendar target, Calendar control)
   :outertype: EbmsUtilityTest

   A common method to validate cirtical field for specified \ ``target``\  by the value in the calendar \ ``control``\ .

   :param target: The target calendar to test for.
   :param control: The reference calendar to test for.

