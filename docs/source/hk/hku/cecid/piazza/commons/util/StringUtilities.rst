.. java:import:: java.text SimpleDateFormat

.. java:import:: java.util ArrayList

.. java:import:: java.util Date

.. java:import:: java.util Locale

.. java:import:: java.util TimeZone

StringUtilities
===============

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public final class StringUtilities

   A StringUtilities is a convenient class for handling some common text processing.

   :author: Hugo Y. K. Lam

Fields
------
LINE_SEPARATOR
^^^^^^^^^^^^^^

.. java:field:: public static final String LINE_SEPARATOR
   :outertype: StringUtilities

Methods
-------
addLeadingCharacter
^^^^^^^^^^^^^^^^^^^

.. java:method:: public static String addLeadingCharacter(String s, char c, int len)
   :outertype: StringUtilities

   Adds specified leading characters to the specified length. Nothing will be done if the length of the given string is equal to or greater than the specified length.

   :param s: the source string.
   :param c: the leading character(s) to be added.
   :param len: the length of the target string.
   :return: the string after adding the specified leading character(s).

addLeadingSpace
^^^^^^^^^^^^^^^

.. java:method:: public static String addLeadingSpace(String s, int len)
   :outertype: StringUtilities

   Adds leading spaces to the given string to the specified length. Nothing will be done if the length of the given string is equal to or greater than the specified length.

   :param s: the source string.
   :param len: the length of the target string.
   :return: the string after adding leading spaces.

addLeadingZero
^^^^^^^^^^^^^^

.. java:method:: public static String addLeadingZero(String s, int len)
   :outertype: StringUtilities

   Adds leading zeros to the given string to the specified length. Nothing will be done if the length of the given string is equal to or greater than the specified length.

   :param s: the source string.
   :param len: the length of the target string.
   :return: the string after adding leading zeros.

addPrefix
^^^^^^^^^

.. java:method:: public static String addPrefix(String s, String prefix)
   :outertype: StringUtilities

   Adds a prefix to a given string if it does not start with.

   :param s: the string to be added.
   :param prefix: the prefix.
   :return: the string with the specified prefix.

addSuffix
^^^^^^^^^

.. java:method:: public static String addSuffix(String s, String suffix)
   :outertype: StringUtilities

   Adds a suffix to a given string if it does not end with.

   :param s: the string to be added.
   :param suffix: the suffix.
   :return: the string with the specified suffix.

appendCharacter
^^^^^^^^^^^^^^^

.. java:method:: public static String appendCharacter(String s, char c, int len)
   :outertype: StringUtilities

   Appends specified characters to the given string to the specified length. Nothing will be done if the length of the given string is equal to or greater than the specified length.

   :param s: the source string.
   :param c: the character(s) to be appended.
   :param len: the length of the target string.
   :return: @return the string after appending the specified character(s).

appendSpace
^^^^^^^^^^^

.. java:method:: public static String appendSpace(String s, int len)
   :outertype: StringUtilities

   Appends spaces to the given string to the specified length. Nothing will be done if the length of the given string is equal to or greater than the specified length.

   :param s: the source string.
   :param len: the length of the target string.
   :return: @return the string after appending spaces.

appendZero
^^^^^^^^^^

.. java:method:: public static String appendZero(String s, int len)
   :outertype: StringUtilities

   Appends zeros to the given string to the specified length. Nothing will be done if the length of the given string is equal to or greater than the specified length.

   :param s: the source string.
   :param len: the length of the target string.
   :return: the string after appending zeros.

concat
^^^^^^

.. java:method:: public static String concat(String[] tokens, String delim)
   :outertype: StringUtilities

   Concatenates a string array (string tokens) into a string with the specified delimiter string.

   :param tokens: a string array to be concatenated.
   :param delim: the delimiter.
   :return: the concatenated string.

concat
^^^^^^

.. java:method:: public static String concat(String[] tokens, String tokenPrefix, String tokenSuffix, String delim)
   :outertype: StringUtilities

   Concatenates a string array (string tokens) into a string with the specified delimiter string, token's prefix, and token's suffix.

   :param tokens: a string array to be concatenated.
   :param tokenPrefix: the token's prefix to be concatenated.
   :param tokenSuffix: the token's suffix to be concatenated.
   :param delim: the delimiter.
   :return: the concatenated string.

contains
^^^^^^^^

.. java:method:: public static boolean contains(String[] tokens, String target)
   :outertype: StringUtilities

   Checks if a given string array contains the specified search string.

   :param tokens: a string array to be searched.
   :param target: the target search string.
   :return: true if the given string array contains the specified search string, false otherwise.

getLength
^^^^^^^^^

.. java:method:: public static int getLength(String s)
   :outertype: StringUtilities

   Gets the length of the given string.

   :param s: the string.
   :return: the length of the given string or 0 if it is null.

isAllDigit
^^^^^^^^^^

.. java:method:: public static boolean isAllDigit(String s)
   :outertype: StringUtilities

   Checks if a given string contains only digits.

   :param s: a string to be checked.
   :return: true if the given string contains only digits, false otherwise.

isEmptyString
^^^^^^^^^^^^^

.. java:method:: public static boolean isEmptyString(String s)
   :outertype: StringUtilities

   Checks if a given string is null or empty after trimmed.

   :param s: the string to be checked.
   :return: true if the given string is null or empty after trimmed, false otherwise.

isWrappedWith
^^^^^^^^^^^^^

.. java:method:: public static boolean isWrappedWith(String s, String prefix, String suffix)
   :outertype: StringUtilities

   Checks if the given string is wrapped with the specified prefix and suffix.

   :param s: the string to be checked.
   :param prefix: the prefix.
   :param suffix: the suffix.
   :return: true if the given string is wrapped with the prefix and suffix.

parseBoolean
^^^^^^^^^^^^

.. java:method:: public static boolean parseBoolean(String s)
   :outertype: StringUtilities

   Parses the given string and returns the boolean value it represents.

   :param s: the string to be parsed.
   :return: true if and only if the given string equals, ignoring case, "true".

parseBoolean
^^^^^^^^^^^^

.. java:method:: public static boolean parseBoolean(String s, boolean def)
   :outertype: StringUtilities

   Parses the given string and returns the boolean value it represents.

   :param s: the string to be parsed.
   :param def: the default boolean value when \ ``s``\  is null.
   :return: true if and only if the given string equals, ignoring case, "true".

parseDouble
^^^^^^^^^^^

.. java:method:: public static double parseDouble(String s)
   :outertype: StringUtilities

   Parses the given string and returns the double value it represents.

   :param s: the string to be parsed.
   :return: the double value the string represents or Double.NaN if unable to parse the string.

parseDouble
^^^^^^^^^^^

.. java:method:: public static double parseDouble(String s, double def)
   :outertype: StringUtilities

   Parses the given string and returns the double value it represents.

   :param s: the string to be parsed.
   :return: the double value the string represents or the default value if unable to parse the string.

parseInt
^^^^^^^^

.. java:method:: public static int parseInt(String s)
   :outertype: StringUtilities

   Parses the given string and returns the integer value it represents.

   :param s: the string to be parsed.
   :return: the integer value the string represents or Integer.MIN_VALUE if unable to parse the string.

parseInt
^^^^^^^^

.. java:method:: public static int parseInt(String s, int def)
   :outertype: StringUtilities

   Parses the given string and returns the integer value it represents.

   :param s: the string to be parsed.
   :return: the integer value the string represents or the default value if unable to parse the string.

parseLong
^^^^^^^^^

.. java:method:: public static long parseLong(String s)
   :outertype: StringUtilities

   Parses the given string and returns the long value it represents.

   :param s: the string to be parsed.
   :return: the long value the string represents or Long.MIN_VALUE if unable to parse the string.

parseLong
^^^^^^^^^

.. java:method:: public static long parseLong(String s, long def)
   :outertype: StringUtilities

   Parses the given string and returns the long value it represents.

   :param s: the string to be parsed.
   :return: the long value the string represents or the default value if unable to parse the string.

removeLeadingCharacter
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static String removeLeadingCharacter(String s, char c)
   :outertype: StringUtilities

   Removes specified leading characters from the given string, if any.

   :param s: the source string.
   :param c: the leading character(s) to be removed.
   :return: the string after removing the specified leading character(s).

removeLeadingSpace
^^^^^^^^^^^^^^^^^^

.. java:method:: public static String removeLeadingSpace(String s)
   :outertype: StringUtilities

   Removes leading spaces from the given string, if any.

   :param s: the source string.
   :return: the string after removing leading spaces.

removeLeadingZero
^^^^^^^^^^^^^^^^^

.. java:method:: public static String removeLeadingZero(String s)
   :outertype: StringUtilities

   Removes leading zeros from the given string, if any.

   :param s: the source string.
   :return: the string after removing leading zeros.

repeat
^^^^^^

.. java:method:: public static String repeat(String s, int occurs)
   :outertype: StringUtilities

   Repeats a given string in the specified number of times, then concatenates and returns it.

   :param s: a string to be repeated and concatenated.
   :param occurs: the number of times of the given string to be repeated.
   :return: the concatenated string.

toArray
^^^^^^^

.. java:method:: public static String[] toArray(String s, String delim, int size)
   :outertype: StringUtilities

   Converts the tokenized string into a string array.

   :param s: the string to be tokenized.
   :param delim: the delimiters.
   :param size: the size of the converted array.
   :return: the string array.

toArray
^^^^^^^

.. java:method:: public static String[] toArray(String s, int occurs)
   :outertype: StringUtilities

   Converts a given string into a string array.

   :param s: the string to be converted.
   :param occurs: the number of occurrences.
   :return: the string array.

toArray
^^^^^^^

.. java:method:: public static String[] toArray(String s)
   :outertype: StringUtilities

   Converts a given string into a string array. The resulted array will contain only one element, which is the specified string parameter.

   :param s: the string to be converted.
   :return: the string array.

toCharArray
^^^^^^^^^^^

.. java:method:: public static char[] toCharArray(String s)
   :outertype: StringUtilities

   Converts the given string into an array of characters.

   :param s: the string to be converted.
   :return: an array of characters representing the given string or an empty array if the given string is null or empty.

toGMTString
^^^^^^^^^^^

.. java:method:: public static String toGMTString(Date d)
   :outertype: StringUtilities

   Returns a string representation of the given Date object of the form: d MMM yyyy hh:mm:ss GMT

   :param d: the date.
   :return: the GMT string representation of the given date.

toHexString
^^^^^^^^^^^

.. java:method:: public static String toHexString(byte[] b) throws Exception
   :outertype: StringUtilities

   To Convert the byte array to the String in Hexdecimal format

   :param b: byte array to convert
   :throws Exception:
   :return: String in hexdecimal representation

toString
^^^^^^^^

.. java:method:: public static String toString(Throwable e)
   :outertype: StringUtilities

   Returns a string representation of the given throwable object, empty string if it is null. The resulted string contains a cause trace of the given throwable object.

   :param e: the throwable object for getting its string representation.
   :return: a string represenation of the given Object.

toString
^^^^^^^^

.. java:method:: public static String toString(Object obj)
   :outertype: StringUtilities

   Returns a string representation of the given object, empty string if it is null.

   :param obj: the object for getting its string representation.
   :return: a string represenation of the given Object.

tokenize
^^^^^^^^

.. java:method:: public static String[] tokenize(String str, String delim)
   :outertype: StringUtilities

   Tokenizes a given string according to the specified delimiters. The characters in the delim argument are the delimiters for separating tokens. Delimiter characters themselves will not be treated as tokens.

   :param str: a string to be parsed.
   :param delim: the delimiters.
   :return: the tokens in a string array.

tokenize
^^^^^^^^

.. java:method:: public static String[] tokenize(String str, int fixedLength)
   :outertype: StringUtilities

   Tokenizes a given string according to a fixed length. If the last token's length is less than the fixed length specified, it will be ignored.

   :param str: a string to be parsed.
   :param fixedLength: the fixed length.
   :return: the tokens in a string array.

trim
^^^^

.. java:method:: public static String trim(String s)
   :outertype: StringUtilities

   Trims a given string. An empty string will be returned if the given string is null.

   :param s: the string to be trimmed.
   :return: the trimmed string.

trim
^^^^

.. java:method:: public static String trim(String s, String prefix, String suffix)
   :outertype: StringUtilities

   Trims the given string. If the given string starts with the specified prefix and ends with the specified suffix, both the prefix and the suffix will be trimmed out.

   :param s: the string to be trimmed.
   :param prefix: the prefix.
   :param suffix: the suffix.
   :return: the trimmed string.

trimAndVerifySize
^^^^^^^^^^^^^^^^^

.. java:method:: public static String trimAndVerifySize(String s, int size)
   :outertype: StringUtilities

   Trims a given string and then verifies its size against the specified size. If the sizes do not match, null will be returned.

   :param s: the string to be trimmed and verified.
   :param size: the size for the verification.
   :return: the trimmed string or null if the size verification failed.

wraps
^^^^^

.. java:method:: public static String wraps(String s, String prefix, String suffix)
   :outertype: StringUtilities

   Wraps a given string with the specified prefix and suffix, if it is not alreay wrapped.

   :param s: the string to be wrapped.
   :param prefix: the prefix.
   :param suffix: the suffix.
   :return: the wrapped string.

