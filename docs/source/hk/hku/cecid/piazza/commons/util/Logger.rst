Logger
======

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public interface Logger

   Logger is a common interface of a logger.

   :author: Hugo Y. K. Lam

Methods
-------
debug
^^^^^

.. java:method:: public void debug(Object msg)
   :outertype: Logger

   Logs a debug message.

   :param msg: the message to be logged.

debug
^^^^^

.. java:method:: public void debug(Object msg, Throwable throwable)
   :outertype: Logger

   Logs a debug message.

   :param msg: the message to be logged.
   :param throwable: the associated exception.

error
^^^^^

.. java:method:: public void error(Object msg)
   :outertype: Logger

   Logs an error message.

   :param msg: the message to be logged.

error
^^^^^

.. java:method:: public void error(Object msg, Throwable throwable)
   :outertype: Logger

   Logs an error message.

   :param msg: the message to be logged.
   :param throwable: the associated exception.

fatal
^^^^^

.. java:method:: public void fatal(Object msg)
   :outertype: Logger

   Logs a fatal error message.

   :param msg: the message to be logged.

fatal
^^^^^

.. java:method:: public void fatal(Object msg, Throwable throwable)
   :outertype: Logger

   Logs a fatal error message.

   :param msg: the message to be logged.
   :param throwable: the associated exception.

info
^^^^

.. java:method:: public void info(Object msg)
   :outertype: Logger

   Logs an informative message.

   :param msg: the message to be logged.

info
^^^^

.. java:method:: public void info(Object msg, Throwable throwable)
   :outertype: Logger

   Logs an informative message.

   :param msg: the message to be logged.
   :param throwable: the associated exception.

warn
^^^^

.. java:method:: public void warn(Object msg)
   :outertype: Logger

   Logs a warning error message.

   :param msg: the message to be logged.

warn
^^^^

.. java:method:: public void warn(Object msg, Throwable throwable)
   :outertype: Logger

   Logs a warning error message.

   :param msg: the message to be logged.
   :param throwable: the associated exception.

