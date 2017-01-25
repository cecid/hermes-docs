.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

ModuleException
===============

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public class ModuleException extends RuntimeException

   ModuleException represents a module's runtime exception.

   :author: Hugo Y. K. Lam

Constructors
------------
ModuleException
^^^^^^^^^^^^^^^

.. java:constructor:: public ModuleException()
   :outertype: ModuleException

   Creates a new instance of ModuleException.

ModuleException
^^^^^^^^^^^^^^^

.. java:constructor:: public ModuleException(String message)
   :outertype: ModuleException

   Creates a new instance of ModuleException.

   :param message: the error message.

ModuleException
^^^^^^^^^^^^^^^

.. java:constructor:: public ModuleException(Throwable cause)
   :outertype: ModuleException

   Creates a new instance of ModuleException.

   :param cause: the cause of this exception.

ModuleException
^^^^^^^^^^^^^^^

.. java:constructor:: public ModuleException(String message, Throwable cause)
   :outertype: ModuleException

   Creates a new instance of ModuleException.

   :param message: the error message.
   :param cause: the cause of this exception.

Methods
-------
toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: ModuleException

   Returns a string representation of this exception.

   :return: a string representation of this exception.

   **See also:** :java:ref:`java.lang.Object.toString()`

