.. java:import:: java.net InetAddress

.. java:import:: java.net UnknownHostException

.. java:import:: java.util ArrayList

.. java:import:: java.util Calendar

.. java:import:: java.util Date

.. java:import:: java.util Iterator

.. java:import:: java.util TimeZone

Utility
=======

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class Utility

   Utility class for use by both clients and server.

   :author: kcyee

Methods
-------
fromUTCString
^^^^^^^^^^^^^

.. java:method:: public static Date fromUTCString(String dateTime)
   :outertype: Utility

   Convert a string of data type "dateTime" as specified by XML-Schema Part 2: Datatypes section 3.2.7 to local date/time. Only date/time represented as CCYY-MM-DDThh:mm:ssZ is supported.

   :param dateTime: Date/time string in UTC.
   :return: local time representation of the given UTC time string.

generateMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public static String generateMessageId(Date date, EbxmlMessage ebxmlMessage) throws Exception
   :outertype: Utility

   Generate globally unique message ID according to the specified date and the information in ebXML message. Required fields are:

   ..

   * To/PartyId element [ebMSS 3.1.1.1]
   * CPAId [ebMSS 3.1.2]
   * Service element [ebMSS 3.1.4]
   * Action element [ebMSS 3.1.5]

   :param date: Date to be used to generate message ID.
   :param ebxmlMessage: ebXML message containing required fields.
   :throws Exception:
   :return: Message ID derived from the given information.

generateMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public static String generateMessageId(Date date, String toPartyId, String cpaId, String service, String action)
   :outertype: Utility

   Generate message ID from the specified date, ToPartyId, CPAId, service name and action string.

   :param date: Date from which message ID is generated.
   :param toPartyId: Party ID of the recipient [ebMSS 3.1.1.1].
   :param cpaId: CPAId [ebMSS 3.1.2].
   :param service: Service name [ebMSS 3.1.4].
   :param action: Action name [ebMSS 3.1.5].
   :return: Message ID derived from the given information.

toUTCString
^^^^^^^^^^^

.. java:method:: public static String toUTCString(Date date)
   :outertype: Utility

   Get timestamp of the specified date in type "dateTime" as specified in XML-Schema Part 2: Datatypes section 3.2.7. Local time is converted to UTC time.

   :param date: Local date to be converted to UTC time.
   :return: UTC time string in CCYY-MM-DDThh:mm:ssZ format

