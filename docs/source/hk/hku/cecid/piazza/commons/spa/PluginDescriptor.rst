.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: java.io File

.. java:import:: java.io FileInputStream

.. java:import:: java.io FileNotFoundException

.. java:import:: java.io InputStream

.. java:import:: java.util ArrayList

.. java:import:: java.util Collection

.. java:import:: java.util Properties

PluginDescriptor
================

.. java:package:: hk.hku.cecid.piazza.commons.spa
   :noindex:

.. java:type:: public class PluginDescriptor

   PluginDescriptor is a descriptor containing the configurations of the plugin it represents.

   .. parsed-literal::

      <plugin id="nmtoken" name="nmtoken"? version="nmtoken"? provider-name="nmtoken"? class="nmtoken"?>

             <parameters>?
                     <parameter name="nmtoken" value="nmtoken" />*
             </parameters>

             <runtime>?
                     <library name="nmtoken" />*
             </runtime>

             <requires>?
                     <import plugin="nmtoken" />*
             </requires>

             <extension-point id="nmtoken" class="nmtoken" name="nmtoken"? />*

             <extension point="nmtoken" name="nmtoken"?>*
                     <parameter name="nmtoken" value="nmtoken" />*
             </extension>

      </plugin>

   :author: Hugo Y. K. Lam

Fields
------
DEFAULT_DESCRIPTOR_NAME
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String DEFAULT_DESCRIPTOR_NAME
   :outertype: PluginDescriptor

   The default descriptor name (plugin.xml).

Constructors
------------
PluginDescriptor
^^^^^^^^^^^^^^^^

.. java:constructor:: public PluginDescriptor(File file) throws PluginException, FileNotFoundException
   :outertype: PluginDescriptor

   Creates a new instance of PluginDescriptor.

   :param file: the plugin descriptor file.
   :throws PluginException: if unable to create the plugin descriptor.
   :throws FileNotFoundException: if the descriptor file does not exist.

PluginDescriptor
^^^^^^^^^^^^^^^^

.. java:constructor:: public PluginDescriptor(InputStream ins) throws PluginException
   :outertype: PluginDescriptor

   Creates a new instance of PluginDescriptor.

   :param ins: the plugin descriptor input stream.
   :throws PluginException: if unable to create the plugin descriptor.

Methods
-------
getExtensionPoints
^^^^^^^^^^^^^^^^^^

.. java:method:: public Collection getExtensionPoints()
   :outertype: PluginDescriptor

   Creates a collection of extension points according to the specified plugin descriptor.

   :return: a collection of extension points.

getExtensions
^^^^^^^^^^^^^

.. java:method:: public Collection getExtensions()
   :outertype: PluginDescriptor

   Creates a collection of extensions according to the specified plugin descriptor.

   :return: a collection of extensions.

getHandlerClass
^^^^^^^^^^^^^^^

.. java:method:: public String getHandlerClass()
   :outertype: PluginDescriptor

   Gets the handler class of the plugin.

   :return: the handler class of the plugin.

getId
^^^^^

.. java:method:: public String getId()
   :outertype: PluginDescriptor

   Gets the plugin ID.

   :return: the plugin ID.

getImports
^^^^^^^^^^

.. java:method:: public Collection getImports()
   :outertype: PluginDescriptor

   Creates a collection of imports according to the specified plugin descriptor.

   :return: a collection of imports.

getLibraries
^^^^^^^^^^^^

.. java:method:: public Collection getLibraries()
   :outertype: PluginDescriptor

   Creates a collection of libraries according to the specified plugin descriptor.

   :return: a collection of libraries.

getName
^^^^^^^

.. java:method:: public String getName()
   :outertype: PluginDescriptor

   Gets the plugin name.

   :return: the plugin name.

getParameters
^^^^^^^^^^^^^

.. java:method:: public Properties getParameters()
   :outertype: PluginDescriptor

   Gets the plugin parameters.

   :return: the plugin parameters.

getParent
^^^^^^^^^

.. java:method:: public PluginComponent getParent()
   :outertype: PluginDescriptor

   Gets the parent plugin component of this descriptor.

   :return: the parent plugin component of this descriptor.

getProviderName
^^^^^^^^^^^^^^^

.. java:method:: public String getProviderName()
   :outertype: PluginDescriptor

   Gets the plugin provider name.

   :return: the plugin provider name.

getVersion
^^^^^^^^^^

.. java:method:: public String getVersion()
   :outertype: PluginDescriptor

   Gets the plugin version.

   :return: the plugin version.

setParent
^^^^^^^^^

.. java:method:: public void setParent(PluginComponent parent)
   :outertype: PluginDescriptor

   Sets the parent plugin component of this descriptor.

   :param parent: the parent plugin component of this descriptor.

