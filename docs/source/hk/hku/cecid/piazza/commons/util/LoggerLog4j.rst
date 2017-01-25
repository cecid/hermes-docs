.. java:import:: hk.hku.cecid.piazza.commons.module ComponentException

.. java:import:: hk.hku.cecid.piazza.commons.module PersistentComponent

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io IOException

.. java:import:: java.net URL

.. java:import:: java.util Properties

.. java:import:: org.apache.log4j Logger

.. java:import:: org.apache.log4j PropertyConfigurator

.. java:import:: org.apache.log4j.xml DOMConfigurator

.. java:import:: org.dom4j Node

.. java:import:: org.dom4j.io SAXReader

.. java:import:: org.xml.sax EntityResolver

.. java:import:: org.xml.sax InputSource

.. java:import:: org.xml.sax SAXException

LoggerLog4j
===========

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public class LoggerLog4j extends PersistentComponent implements hk.hku.cecid.piazza.commons.util.Logger

   LoggerLog4j is an implementation of a Logger and is backed by a Log4j logger.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`org.apache.log4j.Logger`

Constructors
------------
LoggerLog4j
^^^^^^^^^^^

.. java:constructor:: public LoggerLog4j()
   :outertype: LoggerLog4j

   Creates a new instance of LoggerLog4j.

LoggerLog4j
^^^^^^^^^^^

.. java:constructor:: public LoggerLog4j(URL url) throws ComponentException
   :outertype: LoggerLog4j

   Creates a new instance of LoggerLog4j.

   :param url: the url of the configuration file.
   :throws ComponentException: if the configuration could not be loaded from the specified url.

LoggerLog4j
^^^^^^^^^^^

.. java:constructor:: public LoggerLog4j(String name)
   :outertype: LoggerLog4j

   Creates a new instance of LoggerLog4j.

   :param name: the logger category name. null if the name should be looked up dynamically in logging.

LoggerLog4j
^^^^^^^^^^^

.. java:constructor:: public LoggerLog4j(String name, URL url) throws Exception
   :outertype: LoggerLog4j

   Creates a new instance of LoggerLog4j.

   :param name: the logger category name. null if the name should be looked up dynamically in logging.
   :param url: the url of the configuration file.
   :throws UtilitiesException: if the configuration could not be loaded from the specified url.

Methods
-------
debug
^^^^^

.. java:method:: public void debug(Object msg)
   :outertype: LoggerLog4j

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.debug(java.lang.Object)`

debug
^^^^^

.. java:method:: public void debug(Object msg, Throwable throwable)
   :outertype: LoggerLog4j

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.debug(java.lang.Object,java.lang.Throwable)`

error
^^^^^

.. java:method:: public void error(Object msg)
   :outertype: LoggerLog4j

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.error(java.lang.Object)`

error
^^^^^

.. java:method:: public void error(Object msg, Throwable throwable)
   :outertype: LoggerLog4j

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.error(java.lang.Object,java.lang.Throwable)`

fatal
^^^^^

.. java:method:: public void fatal(Object msg)
   :outertype: LoggerLog4j

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.fatal(java.lang.Object)`

fatal
^^^^^

.. java:method:: public void fatal(Object msg, Throwable throwable)
   :outertype: LoggerLog4j

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.fatal(java.lang.Object,java.lang.Throwable)`

info
^^^^

.. java:method:: public void info(Object msg)
   :outertype: LoggerLog4j

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.info(java.lang.Object)`

info
^^^^

.. java:method:: public void info(Object msg, Throwable throwable)
   :outertype: LoggerLog4j

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.info(java.lang.Object,java.lang.Throwable)`

init
^^^^

.. java:method:: protected void init() throws Exception
   :outertype: LoggerLog4j

   Initializes this logger and sets a default logger if specified.

   :throws Exception: if error occurred in initialization.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.Component.init()`

isDebugEnabled
^^^^^^^^^^^^^^

.. java:method:: public boolean isDebugEnabled()
   :outertype: LoggerLog4j

   Checks if the logger itself is in debug mode.

   :return: true if the logger itself is in debug mode.

loading
^^^^^^^

.. java:method:: protected void loading(URL url) throws Exception
   :outertype: LoggerLog4j

   Loads the configuration from the specified url location. A DOM configuration will be triggered if the url ends with ".xml".

   :param url: the url of the configuration source.
   :throws Exception: if the operation is unsuccessful.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.PersistentComponent.loading(java.net.URL)`

warn
^^^^

.. java:method:: public void warn(Object msg)
   :outertype: LoggerLog4j

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.warn(java.lang.Object)`

warn
^^^^

.. java:method:: public void warn(Object msg, Throwable throwable)
   :outertype: LoggerLog4j

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Logger.warn(java.lang.Object,java.lang.Throwable)`

