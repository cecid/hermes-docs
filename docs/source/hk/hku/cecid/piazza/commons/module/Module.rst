.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.util ConsoleLogger

.. java:import:: hk.hku.cecid.piazza.commons.util Instance

.. java:import:: hk.hku.cecid.piazza.commons.util Logger

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: java.io File

.. java:import:: java.io InputStream

.. java:import:: java.net URL

.. java:import:: java.util Collection

.. java:import:: java.util Collections

.. java:import:: java.util Iterator

.. java:import:: java.util LinkedHashMap

.. java:import:: java.util Map

.. java:import:: java.util Properties

Module
======

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public class Module extends Component

   A Module is described by a module descriptor and contains zero to many components. Each module has its own classloader for loading its components, which are defined in the module descriptor, and its resources.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`Component`

Constructors
------------
Module
^^^^^^

.. java:constructor:: public Module(String descriptorLocation)
   :outertype: Module

   Creates and initializes a new instance of Module.

   :param descriptorLocation: the module descriptor.
   :throws ModuleException: if errors encountered when loading the module descriptor.

Module
^^^^^^

.. java:constructor:: public Module(String descriptorLocation, boolean shouldInitialize)
   :outertype: Module

   Creates a new instance of Module.

   :param descriptorLocation: the module descriptor.
   :param shouldInitialize: true if the module should be initialized.
   :throws ModuleException: if errors encountered when loading the module descriptor.

Module
^^^^^^

.. java:constructor:: public Module(String descriptorLocation, ClassLoader loader)
   :outertype: Module

   Creates and initializes a new instance of Module.

   :param descriptorLocation: the module descriptor.
   :param loader: the class loader for this module.
   :throws ModuleException: if errors encountered when loading the module descriptor.

Module
^^^^^^

.. java:constructor:: public Module(String descriptorLocation, ClassLoader loader, boolean shouldInitialize)
   :outertype: Module

   Creates a new instance of Module.

   :param descriptorLocation: the module descriptor.
   :param loader: the class loader for this module.
   :param shouldInitialize: true if the module should be initialized.
   :throws ModuleException: if errors encountered when loading the module descriptor.

Methods
-------
createComponents
^^^^^^^^^^^^^^^^

.. java:method:: protected void createComponents()
   :outertype: Module

   Creates all the components defined in the module descriptor.

   :throws ModuleException: if unable to create any component.

getClassLoader
^^^^^^^^^^^^^^

.. java:method:: public ClassLoader getClassLoader()
   :outertype: Module

   Gets the class loader that this module uses to load classes.

   :return: the class loader for this module.

getComponent
^^^^^^^^^^^^

.. java:method:: public Component getComponent(String id)
   :outertype: Module

   Gets the specified component in this module.

   :param id: the ID of the module component.
   :return: the module component.

getComponentCount
^^^^^^^^^^^^^^^^^

.. java:method:: public int getComponentCount()
   :outertype: Module

   Gets the number of components in this module.

   :return: the number of components in this module.

getComponents
^^^^^^^^^^^^^

.. java:method:: public Collection getComponents()
   :outertype: Module

   Gets all the components in this module.

   :return: all module components

getDescriptor
^^^^^^^^^^^^^

.. java:method:: public URL getDescriptor()
   :outertype: Module

   Gets the module descriptor.

   :return: the module descriptor.

getGroup
^^^^^^^^

.. java:method:: public ModuleGroup getGroup()
   :outertype: Module

   Gets the module group to which this module belongs.

   :return: the module group.

getLogger
^^^^^^^^^

.. java:method:: public Logger getLogger()
   :outertype: Module

   Gets the logger of this module.

   :return: the logger of this module.

getRequiredParameter
^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected String getRequiredParameter(String key)
   :outertype: Module

   Get the mandatory parameter from the current module, throw ModuleException if not found.

   :param key: the key in the parameters list.
   :throws ModuleException: if the parameter with \ ``key``\  does not exist.
   :return: The value of the parameter if found.

getResource
^^^^^^^^^^^

.. java:method:: public URL getResource(String name)
   :outertype: Module

   Gets a resource as URL.

   :param name: the name of the resource.
   :return: the URL of the resource.

   **See also:** :java:ref:`.getResource(String,ClassLoader)`

getResource
^^^^^^^^^^^

.. java:method:: public static URL getResource(String name, ClassLoader loader)
   :outertype: Module

   Gets a resource as URL.

   The specified name can be an absolute path or a relative path to the current directory or classpaths.

   If the specified name is a relative path, it will be searched through the current directory and then the classpaths.

   :param name: the name of the resource.
   :param loader: the class loader for finding the resource.
   :return: the URL of the resource.

getResourceAsStream
^^^^^^^^^^^^^^^^^^^

.. java:method:: public InputStream getResourceAsStream(String name)
   :outertype: Module

   Gets a resource as stream.

   :param name: the name of the resource.
   :return: an input stream of the resource.

   **See also:** :java:ref:`.getResource(String)`

getString
^^^^^^^^^

.. java:method:: protected String getString(String key)
   :outertype: Module

   Gets the string value of the specified key from the module descriptor.

   :param key: the key in the resource bundle.
   :return: the string value.

getVersion
^^^^^^^^^^

.. java:method:: public String getVersion()
   :outertype: Module

   Gets the version of this module.

   :return: the version of this module.

init
^^^^

.. java:method:: public void init()
   :outertype: Module

   Initializes the module and all its components.

   :throws ModuleException: if unable to initialize the module.

initComponents
^^^^^^^^^^^^^^

.. java:method:: protected void initComponents()
   :outertype: Module

   Initializes all the created components.

   :throws ModuleException: if unable to initialize any component.

setComponent
^^^^^^^^^^^^

.. java:method:: public void setComponent(Component component)
   :outertype: Module

   Sets a component to this module.

   :param component: the component to be set.

setGroup
^^^^^^^^

.. java:method:: public void setGroup(ModuleGroup group)
   :outertype: Module

   Sets the module group to which this module belongs.

   :param group: the module group.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: Module

   Returns a string representation of this module.

   :return: a string representation of this module.

   **See also:** :java:ref:`java.lang.Object.toString()`

