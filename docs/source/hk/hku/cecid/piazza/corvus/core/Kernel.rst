.. java:import:: java.io File

.. java:import:: java.util Date

.. java:import:: java.util Properties

.. java:import:: hk.hku.cecid.piazza.commons.servlet.http HttpDispatcherContext

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginRegistry

.. java:import:: hk.hku.cecid.piazza.commons Sys

Kernel
======

.. java:package:: hk.hku.cecid.piazza.corvus.core
   :noindex:

.. java:type:: public class Kernel

   Kernel is the nucleus of Piazza Corvus. It initializes the basic configuration and sets up the plugin registry. After setting up the plugin registry, it activates the plugins and extension points and then Corvus is started.

   :author: Hugo Y. K. Lam

Methods
-------
getInstance
^^^^^^^^^^^

.. java:method:: public static Kernel getInstance()
   :outertype: Kernel

   Gets the single kernel instance.

   :return: the kernel instance.

getPluginRegistry
^^^^^^^^^^^^^^^^^

.. java:method:: public PluginRegistry getPluginRegistry()
   :outertype: Kernel

   Retrieves the plugin registry managed by this kernel.

   :return: the plugin registry.

getStartupTime
^^^^^^^^^^^^^^

.. java:method:: public Date getStartupTime()
   :outertype: Kernel

   Retrieves the startup time of this kernel.

   :return: the startup time.

hasErrors
^^^^^^^^^

.. java:method:: public boolean hasErrors()
   :outertype: Kernel

   Checks whether there were any errors in the start up process of this kernel.

   :return: true if there were any errors in the start up process.

shutdown
^^^^^^^^

.. java:method:: public void shutdown()
   :outertype: Kernel

   Shutdowns this kernel and deactivates all the plugin registry.

