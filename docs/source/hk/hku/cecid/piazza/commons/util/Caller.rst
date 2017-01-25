Caller
======

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public class Caller

   A Caller represents the class calling the method which generates this Caller. It retrieves information from the stack trace and is a relatively expensive operation. As a result, it should be used only when there is an absolute need.

   :author: Hugo Y. K. Lam

Constructors
------------
Caller
^^^^^^

.. java:constructor:: public Caller()
   :outertype: Caller

   Creates a new instance of Caller.

Caller
^^^^^^

.. java:constructor:: public Caller(int backSteps)
   :outertype: Caller

   Creates a new instance of Caller.

   :param backSteps: number of steps backward from the point of the immediate caller in the trace.

Methods
-------
getClassName
^^^^^^^^^^^^

.. java:method:: public String getClassName()
   :outertype: Caller

   Gets the name of the calling class.

   :return: the name of the calling class.

getFileName
^^^^^^^^^^^

.. java:method:: public String getFileName()
   :outertype: Caller

   Gets the file name of the calling class.

   :return: the file name of the calling class.

getLineNumber
^^^^^^^^^^^^^

.. java:method:: public int getLineNumber()
   :outertype: Caller

   Gets the line number in the source file of the caller class at which the call is made.

   :return: the line number in the source file.

getMethodName
^^^^^^^^^^^^^

.. java:method:: public String getMethodName()
   :outertype: Caller

   Gets the method name of the method, which makes the call, in the caller class.

   :return: the method name.

getName
^^^^^^^

.. java:method:: public static String getName()
   :outertype: Caller

   Gets the name of the calling class.

   :return: the name of the calling class.

isUnknown
^^^^^^^^^

.. java:method:: public boolean isUnknown()
   :outertype: Caller

   Checks if the calling class is undetermined.

   :return: true if the calling class is undetermined.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: Caller

   Returns a string representation of this Caller.

   :return: a string representation of this Caller.

   **See also:** :java:ref:`java.lang.Object.toString()`

