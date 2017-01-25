.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io File

.. java:import:: java.io ObjectInputStream

.. java:import:: java.io ObjectOutputStream

.. java:import:: java.io Serializable

.. java:import:: java.lang.reflect Constructor

.. java:import:: java.lang.reflect Method

.. java:import:: java.net URL

.. java:import:: java.net URLDecoder

.. java:import:: java.util Vector

Convertor
=========

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public final class Convertor

   A Convertor is mainly responsible for data format conversion.

   :author: Hugo Y. K. Lam

Methods
-------
convertObject
^^^^^^^^^^^^^

.. java:method:: public static Object convertObject(Object source, Class target)
   :outertype: Convertor

   Converts the given source Object to an instance of the specified target class. The constructor of the target class which has an argument of the source object type will be looked up first. It it succeeds, the source Object will be passed in as the argument. Otherwise, the constructor which has a String argument will be looked up and the source object will be passed in as a String by calling its toString method. Null will be returned if the conversion cannot be performed.

   :param source: the source Object.
   :param target: the target class.
   :return: an instance of the target class representing the given source Object.

deepCopy
^^^^^^^^

.. java:method:: public static Object deepCopy(Serializable obj)
   :outertype: Convertor

   Performs a deep copy of the given serializable Object.

   :param obj: the serializable Object to be copied.
   :return: a copy of the given Object.

toFile
^^^^^^

.. java:method:: public static File toFile(URL url)
   :outertype: Convertor

   Converts a java.net.URL into a java.io.File.

   :param url: the java.net.URL to be converted.
   :return: a java.io.File representing the given URL.

toSQLDate
^^^^^^^^^

.. java:method:: public static java.sql.Date toSQLDate(java.util.Date date)
   :outertype: Convertor

   Converts a java.util.Date to a java.sql.Date.

   :param date: The java.util.Date to be converted.
   :return: a java.sql.Date representing the given date.

toTimestamp
^^^^^^^^^^^

.. java:method:: public static java.sql.Timestamp toTimestamp(java.util.Date date)
   :outertype: Convertor

   Converts a java.util.Date to a java.sql.Timestamp.

   :param date: The java.util.Date to be converted.
   :return: a java.sql.Timestamp representing the given date.

toVector
^^^^^^^^

.. java:method:: public static Vector toVector(Object obj)
   :outertype: Convertor

   Converts the given Object to a Vector. If the given Object is already a Vector, the Object will be directly returned. Otherwise, the Oobject will be added to a new Vector and the Vector will be returned.

   :param obj: The Object to be converted.
   :return: The Vector converted by the given Object.

translateProperties
^^^^^^^^^^^^^^^^^^^

.. java:method:: public static void translateProperties(javax.servlet.http.HttpServletRequest request, Object bean)
   :outertype: Convertor

   Translates the request parameters in the given HttpServletRequest to the properties in the given bean Object.

   :param request: the HttpServletRequest which contains the request parameters to be translated.
   :param bean: the bean Object into which the request parameters to be translated.

