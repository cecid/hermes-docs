.. java:import:: hk.hku.cecid.piazza.commons.module Component

.. java:import:: java.io PrintStream

ConsoleLogger
=============

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public class ConsoleLogger extends Component implements Logger

   ConsoleLogger is a logger which logs messages to System.out and System.err.

   :author: Hugo Y. K. Lam

Constructors
------------
ConsoleLogger
^^^^^^^^^^^^^

.. java:constructor:: public ConsoleLogger()
   :outertype: ConsoleLogger

   Creates a new instance of ConsoleLogger.

Methods
-------
debug
^^^^^

.. java:method:: public void debug(Object msg)
   :outertype: ConsoleLogger

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.debug(java.lang.Object)`

debug
^^^^^

.. java:method:: public void debug(Object msg, Throwable throwable)
   :outertype: ConsoleLogger

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.debug(java.lang.Object,java.lang.Throwable)`

error
^^^^^

.. java:method:: public void error(Object msg)
   :outertype: ConsoleLogger

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.error(java.lang.Object)`

error
^^^^^

.. java:method:: public void error(Object msg, Throwable throwable)
   :outertype: ConsoleLogger

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.error(java.lang.Object,java.lang.Throwable)`

fatal
^^^^^

.. java:method:: public void fatal(Object msg)
   :outertype: ConsoleLogger

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.fatal(java.lang.Object)`

fatal
^^^^^

.. java:method:: public void fatal(Object msg, Throwable throwable)
   :outertype: ConsoleLogger

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.fatal(java.lang.Object,java.lang.Throwable)`

getInstance
^^^^^^^^^^^

.. java:method:: public static ConsoleLogger getInstance()
   :outertype: ConsoleLogger

   Gets the default instance.

   :return: the default instance.

info
^^^^

.. java:method:: public void info(Object msg)
   :outertype: ConsoleLogger

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.info(java.lang.Object)`

info
^^^^

.. java:method:: public void info(Object msg, Throwable throwable)
   :outertype: ConsoleLogger

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.info(java.lang.Object,java.lang.Throwable)`

warn
^^^^

.. java:method:: public void warn(Object msg)
   :outertype: ConsoleLogger

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.warn(java.lang.Object)`

warn
^^^^

.. java:method:: public void warn(Object msg, Throwable throwable)
   :outertype: ConsoleLogger

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.warn(java.lang.Object,java.lang.Throwable)`

