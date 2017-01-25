.. java:import:: java.io File

.. java:import:: java.io FileOutputStream

.. java:import:: java.io IOException

.. java:import:: java.io OutputStream

.. java:import:: java.io PrintStream

.. java:import:: hk.hku.cecid.piazza.commons.module Component

.. java:import:: hk.hku.cecid.piazza.commons.util Logger

.. java:import:: hk.hku.cecid.piazza.commons.util UtilitiesException

FileLogger
==========

.. java:package:: hk.hku.cecid.corvus.util
   :noindex:

.. java:type:: public class FileLogger extends Component implements Logger

   The file logger is a simple logger that log everything to the desired file. \ **Dependency**\  : Piazza Common  The sample usage is shown on the below:

   .. parsed-literal::

       FileLogger log = new FileLogger("../logs/testlog.txt");
      log.debug("Test debug statement");
      log.error("Test error statement");
      log.fatal("Test fatal statement");
      log.info ("Test info  statement");
      log.warn ("Test warn  statement");

   The output in the file logger should be liked these:

   .. parsed-literal::

      [Debug] Test debug statement
      [Error] Test error statement
      [Fatal] Test fatal statement
      [Info]  Test info statement
      [Warn]  Test warn statement

   \ **SPA Component Guideline:**\ .

   :author: Twinsen Tsang

Constructors
------------
FileLogger
^^^^^^^^^^

.. java:constructor:: public FileLogger(String filepath) throws UtilitiesException
   :outertype: FileLogger

   Constructor.

   :param filepath: The filepath for logging.
   :throws UtiltiesException: Throw if any IO Operations fail like can not open file or print stream.

FileLogger
^^^^^^^^^^

.. java:constructor:: public FileLogger(File f) throws UtilitiesException
   :outertype: FileLogger

   Constructor.   The file logger open a file output stream for writing the log to the file. It use the default log file name \ *"log.txt"*\  for logging if the file object is a directory.

   :param f: The file object specified.
   :throws UtilitiesException: Throw if any IO Operations fail like can not open file or print stream.

Methods
-------
debug
^^^^^

.. java:method:: public void debug(Object msg)
   :outertype: FileLogger

   Override debug print method.

   :param msg: debugging object to be printed.

debug
^^^^^

.. java:method:: public void debug(Object msg, Throwable t)
   :outertype: FileLogger

   Override debug with exception print method.

   :param msg: debugging object to be printed.

error
^^^^^

.. java:method:: public void error(Object msg)
   :outertype: FileLogger

   Override error print method.

   :param msg: errorging object to be printed.

error
^^^^^

.. java:method:: public void error(Object msg, Throwable t)
   :outertype: FileLogger

   Override error with exception print method.

   :param msg: errorging object to be printed.

fatal
^^^^^

.. java:method:: public void fatal(Object msg)
   :outertype: FileLogger

   Override fatal print method.

   :param msg: fatalging object to be printed.

fatal
^^^^^

.. java:method:: public void fatal(Object msg, Throwable t)
   :outertype: FileLogger

   Override fatal with exception print method.

   :param msg: fatalging object to be printed.

finalize
^^^^^^^^

.. java:method:: protected void finalize()
   :outertype: FileLogger

   The method finalized the class.

info
^^^^

.. java:method:: public void info(Object msg)
   :outertype: FileLogger

   Override info print method.

   :param msg: infoging object to be printed.

info
^^^^

.. java:method:: public void info(Object msg, Throwable t)
   :outertype: FileLogger

   Override info with exception print method.

   :param msg: infoging object to be printed.

init
^^^^

.. java:method:: protected void init()
   :outertype: FileLogger

   Override initialization method. It invokes when the logger is acted as Module Component.

log
^^^

.. java:method:: public void log(String s)
   :outertype: FileLogger

   Log a string to the file by the print stream.

   :param s: The string to be logged.

logStackTrace
^^^^^^^^^^^^^

.. java:method:: public void logStackTrace(Throwable e)
   :outertype: FileLogger

   Log a exception / throwable to the file by the print stream. The exception element will begin with the tag [Stack Trace] other than debug, error, fatal, warn, info.

   :param e: The throwable e to be logged.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: FileLogger

   toString method().

warn
^^^^

.. java:method:: public void warn(Object msg)
   :outertype: FileLogger

   Override warn print method.

   :param msg: warnging object to be printed.

warn
^^^^

.. java:method:: public void warn(Object msg, Throwable t)
   :outertype: FileLogger

   Override warn with exception print method.

   :param msg: warnging object to be printed.

