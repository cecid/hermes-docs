.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

GenericException
================

.. java:package:: hk.hku.cecid.piazza.commons
   :noindex:

.. java:type:: public class GenericException extends Exception

   GenericException represents all kinds of non-runtime exception in the application.

   :author: Hugo Y. K. Lam

Constructors
------------
GenericException
^^^^^^^^^^^^^^^^

.. java:constructor:: public GenericException()
   :outertype: GenericException

   Creates a new instance of GenericException.

GenericException
^^^^^^^^^^^^^^^^

.. java:constructor:: public GenericException(String message)
   :outertype: GenericException

   Creates a new instance of GenericException.

   :param message: the error message.

GenericException
^^^^^^^^^^^^^^^^

.. java:constructor:: public GenericException(Throwable cause)
   :outertype: GenericException

   Creates a new instance of GenericException.

   :param cause: the cause of this exception.

GenericException
^^^^^^^^^^^^^^^^

.. java:constructor:: public GenericException(String message, Throwable cause)
   :outertype: GenericException

   Creates a new instance of GenericException.

   :param message: the error message.
   :param cause: the cause of this exception.

Methods
-------
toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: GenericException

   Returns a string representation of this exception.

   :return: a string representation of this exception.

   **See also:** :java:ref:`java.lang.Object.toString()`

