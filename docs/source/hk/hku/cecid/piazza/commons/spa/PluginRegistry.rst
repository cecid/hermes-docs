.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.io FileSystem

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.util Zip

.. java:import:: java.io File

.. java:import:: java.io FileOutputStream

.. java:import:: java.io InputStream

.. java:import:: java.util ArrayList

.. java:import:: java.util Collection

.. java:import:: java.util HashMap

.. java:import:: java.util Iterator

.. java:import:: java.util Map

PluginRegistry
==============

.. java:package:: hk.hku.cecid.piazza.commons.spa
   :noindex:

.. java:type:: public class PluginRegistry

   A PluginRegistry is a registry which stores all the plugin configurations. It has a fixed registry location and the plugin configurations are specified in plugin descriptors.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`Plugin`

Constructors
------------
PluginRegistry
^^^^^^^^^^^^^^

.. java:constructor:: public PluginRegistry(String registry) throws PluginException
   :outertype: PluginRegistry

   Creates a new instance of PluginRegistry.

   :param registry: the registry location.
   :throws PluginException: if the registry is invalid.

PluginRegistry
^^^^^^^^^^^^^^

.. java:constructor:: public PluginRegistry(File registry) throws PluginException
   :outertype: PluginRegistry

   Creates a new instance of PluginRegistry.

   :param registry: the registry location.
   :throws PluginException: if the registry is invalid.

PluginRegistry
^^^^^^^^^^^^^^

.. java:constructor:: public PluginRegistry(String registry, String descriptor) throws PluginException
   :outertype: PluginRegistry

   Creates a new instance of PluginRegistry.

   :param registry: the registry location.
   :param descriptor: the plugin descriptor name.
   :throws PluginException: if the registry is invalid.

PluginRegistry
^^^^^^^^^^^^^^

.. java:constructor:: public PluginRegistry(File registry, String descriptor) throws PluginException
   :outertype: PluginRegistry

   Creates a new instance of PluginRegistry.

   :param registry: the registry location.
   :param descriptor: the plugin descriptor name.
   :throws PluginException: if the registry is invalid.

Methods
-------
activate
^^^^^^^^

.. java:method:: public synchronized void activate()
   :outertype: PluginRegistry

   Activates the plugin registry if it is not yet activated.

deactivate
^^^^^^^^^^

.. java:method:: public synchronized void deactivate()
   :outertype: PluginRegistry

   Deactivates the plugin registry if it is activated.

deploy
^^^^^^

.. java:method:: public String deploy(InputStream spa) throws PluginException
   :outertype: PluginRegistry

   Deploys a plugin to the plugin registry.

   :param spa: the SPA file input stream.
   :throws PluginException: if unable to deploy the plugin.
   :return: the plugin ID of the deployed plugin.

getAllExtensions
^^^^^^^^^^^^^^^^

.. java:method:: public Collection getAllExtensions(String point)
   :outertype: PluginRegistry

   Gets all extensions corresponding to the specified extension point.

   :param point: the extension point.
   :return: all extensions corresponding to the specified extension point.

getLocation
^^^^^^^^^^^

.. java:method:: public String getLocation()
   :outertype: PluginRegistry

   Gets the plugin registry location.

   :return: the plugin registry location.

getPlugin
^^^^^^^^^

.. java:method:: public Plugin getPlugin(String id)
   :outertype: PluginRegistry

   Gets a plugin from this plugin registry.

   :param id: the plugin ID.
   :return: the plugin corresponding to the specified plugin ID.

getPlugins
^^^^^^^^^^

.. java:method:: public Collection getPlugins()
   :outertype: PluginRegistry

   Gets all plugins in this plugin registry.

   :return: all plugins in this plugin registry.

hasErrors
^^^^^^^^^

.. java:method:: public boolean hasErrors()
   :outertype: PluginRegistry

   Checks if there is any error occurred during the initialization or activation of this plugin registry.

   :return: true if there is any error occurred during the activation of this plugin registry.

isActivated
^^^^^^^^^^^

.. java:method:: public boolean isActivated()
   :outertype: PluginRegistry

   Checks if this plugin registry has already been activated.

   :return: true if this plugin registry has already been activated.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: PluginRegistry

   Returns a string representation of this plugin registry.

   :return: a string representation of this plugin registry.

   **See also:** :java:ref:`java.lang.Object.toString()`

undeploy
^^^^^^^^

.. java:method:: public void undeploy(String pluginID) throws PluginException
   :outertype: PluginRegistry

   Undeploys a plugin from the plugin registry.

   :param pluginID: the plugin ID to undeploy.
   :throws PluginException: if unable to undeploy the plugin.

