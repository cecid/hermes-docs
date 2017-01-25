.. java:import:: java.net URL

.. java:import:: java.net URLClassLoader

.. java:import:: java.net URLStreamHandlerFactory

.. java:import:: java.util Iterator

.. java:import:: java.util Vector

PluginClassLoader
=================

.. java:package:: hk.hku.cecid.piazza.commons.spa
   :noindex:

.. java:type:: public class PluginClassLoader extends URLClassLoader

   A PluginClassLoader is a class loader for loading classes which stored in the libraries specified in a plugin descriptor.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`Plugin`

Constructors
------------
PluginClassLoader
^^^^^^^^^^^^^^^^^

.. java:constructor:: public PluginClassLoader(Plugin plugin, URL[] urls)
   :outertype: PluginClassLoader

   Creates a new instance of PluginClassLoader.

   :param plugin: the Plugin corresponds to this class loader.
   :param urls: the search paths.

PluginClassLoader
^^^^^^^^^^^^^^^^^

.. java:constructor:: public PluginClassLoader(Plugin plugin, URL[] urls, ClassLoader parent)
   :outertype: PluginClassLoader

   Creates a new instance of PluginClassLoader.

   :param plugin: the Plugin corresponds to this class loader.
   :param urls: the search paths.
   :param parent: the parent class loader.

PluginClassLoader
^^^^^^^^^^^^^^^^^

.. java:constructor:: public PluginClassLoader(Plugin plugin, URL[] urls, ClassLoader parent, URLStreamHandlerFactory factory)
   :outertype: PluginClassLoader

   Creates a new instance of PluginClassLoader.

   :param plugin: the Plugin corresponds to this class loader.
   :param urls: the search paths.
   :param parent: the parent class loader.
   :param factory: the URL stream handler factory.

Methods
-------
findClass
^^^^^^^^^

.. java:method:: protected Class findClass(String name) throws ClassNotFoundException
   :outertype: PluginClassLoader

   Finds and loads the class with the specified name from the URL search path. Any URLs referring to JAR files are loaded and opened as needed until the class is found. If the class is not found from the search paths of this class loader, it will be searched from the imported class loaders.

   :param name: the name of the class.
   :throws java.lang.ClassNotFoundException: if the class could not be found.
   :return: the resulting class.

   **See also:** :java:ref:`java.lang.ClassLoader.findClass(java.lang.String)`

findImportedClass
^^^^^^^^^^^^^^^^^

.. java:method:: protected Class findImportedClass(String name) throws ClassNotFoundException
   :outertype: PluginClassLoader

   Finds and loads the class with the specified name from the imported class loaders.

   :param name: the name of the class.
   :throws java.lang.ClassNotFoundException: if the class could not be found.
   :return: the resulting class.

   **See also:** :java:ref:`java.lang.ClassLoader.findClass(java.lang.String)`

findResource
^^^^^^^^^^^^

.. java:method:: public URL findResource(String name)
   :outertype: PluginClassLoader

   Finds the resource with the specified name on the URL search paths.

   :param name: the name of the resource.
   :return: a URL for the resource, or null if the resource could not be found.

   **See also:** :java:ref:`java.lang.ClassLoader.findResource(java.lang.String)`

getPlugin
^^^^^^^^^

.. java:method:: public Plugin getPlugin()
   :outertype: PluginClassLoader

   Gets the plugin corresponds to this class loader.

   :return: the plugin corresponds to this class loader.

importClassLoader
^^^^^^^^^^^^^^^^^

.. java:method::  void importClassLoader(ClassLoader loader)
   :outertype: PluginClassLoader

   Imports a class loader.

   :param loader: the class loader to be imported.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: PluginClassLoader

   Returns a string representation of this class loader.

   :return: a string representation of this class loader.

   **See also:** :java:ref:`java.lang.Object.toString()`

