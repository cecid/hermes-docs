.. java:import:: java.io File

.. java:import:: java.net MalformedURLException

.. java:import:: java.net URL

.. java:import:: java.util ArrayList

.. java:import:: java.util Collection

.. java:import:: java.util Iterator

.. java:import:: java.util Properties

Plugin
======

.. java:package:: hk.hku.cecid.piazza.commons.spa
   :noindex:

.. java:type:: public class Plugin extends PluginComponent

   A Plugin represents a plugin descriptor. It contains the elements specified in the descriptor. It also contains a class loader for loading classes which stored in the libraries specified in the descriptor. If there is a plugin handler specified in the descriptor, it will be invoked when the plugin is being activated.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`PluginRegistry`, :java:ref:`PluginClassLoader`, :java:ref:`PluginHandler`

Constructors
------------
Plugin
^^^^^^

.. java:constructor:: public Plugin(PluginRegistry registry, File folder, String descriptor) throws PluginException
   :outertype: Plugin

   Creates a new instance of Plugin.

   :param registry: the plugin registry which stores this plugin.
   :param folder: the folder which holds this plugin.
   :param descriptor: the descriptor of this plugin.
   :throws PluginException: if this plugin cannot be initialized according to its plugin descriptor.

Methods
-------
activate
^^^^^^^^

.. java:method:: public synchronized void activate() throws PluginException
   :outertype: Plugin

   Activates this plugin by invoking the plugin handler specified in the plugin descriptor. If the plugin has already been activated, nothing will be done.

   :throws PluginException: if there is any error in processing activation by the handler.

deactivate
^^^^^^^^^^

.. java:method:: public synchronized void deactivate() throws PluginException
   :outertype: Plugin

   Deactivates this plugin by invoking the plugin handler specified in the plugin descriptor. If the plugin has not yet been activated, nothing will be done.

   :throws PluginException: if there is any error in processing deactivation by the handler.

getClassLoader
^^^^^^^^^^^^^^

.. java:method:: public PluginClassLoader getClassLoader()
   :outertype: Plugin

   Gets the class loader for this plugin.

   :return: the class loader for this plugin.

getExtensionPoints
^^^^^^^^^^^^^^^^^^

.. java:method:: public Collection getExtensionPoints()
   :outertype: Plugin

   Gets all the extension points declared in the plugin descriptor.

   :return: all the extension points declared in the plugin descriptor.

getExtensions
^^^^^^^^^^^^^

.. java:method:: public Collection getExtensions()
   :outertype: Plugin

   Gets all extensions declared in the plugin descriptor.

   :return: all extensions declared in the plugin descriptor.

getExtensions
^^^^^^^^^^^^^

.. java:method:: public Collection getExtensions(String point)
   :outertype: Plugin

   Gets all extensions declared in the plugin descriptor which extends the specified extension point.

   :param point: the extension point.
   :return: all extensions declared in the plugin descriptor which extends the specified extension point.

getHandlerClass
^^^^^^^^^^^^^^^

.. java:method:: public String getHandlerClass()
   :outertype: Plugin

   Gets the handler class of this plugin.

   :return: the handler class of this plugin.

getId
^^^^^

.. java:method:: public String getId()
   :outertype: Plugin

   Gets the plugin ID.

   :return: the plugin ID.

getImports
^^^^^^^^^^

.. java:method:: public Collection getImports()
   :outertype: Plugin

   Gets all plugin imports declared in the plugin descriptor.

   :return: all plugin imports declared in the plugin descriptor.

getLibraries
^^^^^^^^^^^^

.. java:method:: public Collection getLibraries()
   :outertype: Plugin

   Gets all libraries declared in the plugin descriptor.

   :return: all libraries declared in the plugin descriptor.

getName
^^^^^^^

.. java:method:: public String getName()
   :outertype: Plugin

   Gets the plugin name.

   :return: the plugin name.

getParameters
^^^^^^^^^^^^^

.. java:method:: public Properties getParameters()
   :outertype: Plugin

   Gets the parameters of this plugin.

   :return: the parameters of this plugin.

getPluginRegistry
^^^^^^^^^^^^^^^^^

.. java:method:: public PluginRegistry getPluginRegistry()
   :outertype: Plugin

   Gets the plugin registry of this plugin.

   :return: the plugin registry of this plugin.

getProviderName
^^^^^^^^^^^^^^^

.. java:method:: public String getProviderName()
   :outertype: Plugin

   Gets the provider name of this plugin.

   :return: the provider name of this plugin.

getVersion
^^^^^^^^^^

.. java:method:: public String getVersion()
   :outertype: Plugin

   Gets the version of this plugin.

   :return: the version of this plugin.

isActivated
^^^^^^^^^^^

.. java:method:: public boolean isActivated()
   :outertype: Plugin

   Checks if this plugin has been activated.

   :return: true if this plugin has been activated.

loadClass
^^^^^^^^^

.. java:method:: public Class loadClass(String name) throws PluginException
   :outertype: Plugin

   Loads a class from this plugin's class loader.

   :param name: the class name.
   :throws PluginException: if the class was not found.
   :return: the Class instance for the specified class name.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: Plugin

   Returns a string representation of this plugin.

   :return: a string representation of this plugin.

   **See also:** :java:ref:`java.lang.Object.toString()`

