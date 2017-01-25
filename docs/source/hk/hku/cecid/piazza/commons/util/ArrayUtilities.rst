.. java:import:: java.util ArrayList

.. java:import:: java.util Enumeration

.. java:import:: java.util Iterator

.. java:import:: java.util StringTokenizer

ArrayUtilities
==============

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public final class ArrayUtilities

   ArrayUtilities is a convenient class for handling some common array processing.

   :author: Hugo Y. K. Lam

Methods
-------
forNames
^^^^^^^^

.. java:method:: public static Class[] forNames(String[] classNames) throws ClassNotFoundException
   :outertype: ArrayUtilities

   Returns the Class object array associated with the class or interface with the given string name array.

   :param classNames: the fully qualified names of the desired classes.
   :throws ClassNotFoundException:
   :return: the Class object array for the classes with the specified names.

forObjects
^^^^^^^^^^

.. java:method:: public static Class[] forObjects(Object[] objs)
   :outertype: ArrayUtilities

   Returns the Class object array associated with the class or interface with the given object array.

   :param objs: the objects of the desired classes.
   :return: the Class object array for the classes with the specified objects.

toArray
^^^^^^^

.. java:method:: public static String[] toArray(String s, String delim)
   :outertype: ArrayUtilities

   Tokenizes a string by the specified delimiter(s) and converts it into a string array.

   :param s: the string to be tokenized.
   :param delim: the delimiter(s).
   :return: the tokenized strings as a string array.

toArray
^^^^^^^

.. java:method:: public static Object[] toArray(Iterator it)
   :outertype: ArrayUtilities

   Converts an iterator into an object array.

   :param it: the iterator to be converted.
   :return: an array representation of the iterator.

toArray
^^^^^^^

.. java:method:: public static Object[] toArray(Iterator it, Object[] a)
   :outertype: ArrayUtilities

   Converts an iterator into an object array.

   :param it: the iterator to be converted.
   :param a: the array into which the elements of this list are to be stored, if it is big enough; otherwise, a new array of the same runtime type is allocated for this purpose.
   :return: an array representation of the iterator.

toArray
^^^^^^^

.. java:method:: public static Object[] toArray(Enumeration enumeration)
   :outertype: ArrayUtilities

   Converts an enumeration into an object array.

   :param enumeration: the enumeration to be converted.
   :return: an array representation of the enumeration.

toArray
^^^^^^^

.. java:method:: public static Object[] toArray(Enumeration enumeration, Object[] a)
   :outertype: ArrayUtilities

   Converts an enumeration into an object array.

   :param enumeration: the enumeration to be converted.
   :param a: the array into which the elements of this list are to be stored, if it is big enough; otherwise, a new array of the same runtime type is allocated for this purpose.
   :return: an array representation of the enumeration.

toClasses
^^^^^^^^^

.. java:method:: public static Class[] toClasses(Object[] objs) throws ClassNotFoundException
   :outertype: ArrayUtilities

