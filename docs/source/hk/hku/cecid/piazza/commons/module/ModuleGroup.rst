.. java:import:: hk.hku.cecid.piazza.commons.util Instance

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: java.net URL

.. java:import:: java.util Collection

.. java:import:: java.util Collections

.. java:import:: java.util HashSet

.. java:import:: java.util Iterator

.. java:import:: java.util LinkedHashMap

.. java:import:: java.util List

.. java:import:: java.util Map

.. java:import:: java.util Set

.. java:import:: java.util Vector

ModuleGroup
===========

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public class ModuleGroup

   ModuleGroup represents a group of modules and is capable of starting and stopping its active modules. A module group can have multiple system modules and the first one defined in the module group descriptor will be treated as the default system module.

   :author: Hugo Y. K. Lam

Constructors
------------
ModuleGroup
^^^^^^^^^^^

.. java:constructor:: public ModuleGroup(String descriptorLocation)
   :outertype: ModuleGroup

   Creates a new instance of ModuleGroup.

   :param descriptorLocation: the descriptor location.

ModuleGroup
^^^^^^^^^^^

.. java:constructor:: public ModuleGroup(String descriptorLocation, ClassLoader loader)
   :outertype: ModuleGroup

   Creates a new instance of ModuleGroup.

   :param descriptorLocation: the descriptor location.
   :param loader: the class loader for loading the modules.

Methods
-------
addChild
^^^^^^^^

.. java:method:: public void addChild(ModuleGroup group)
   :outertype: ModuleGroup

   Adds a child module group.

   :param group: the child module group.

getChildren
^^^^^^^^^^^

.. java:method:: public Collection getChildren()
   :outertype: ModuleGroup

   Gets the child module groups.

   :return: the child module groups.

getModule
^^^^^^^^^

.. java:method:: public Module getModule(String id)
   :outertype: ModuleGroup

   Gets the specified module in this module group.

   :param id: the module ID.
   :return: the specified module.

getModules
^^^^^^^^^^

.. java:method:: public Collection getModules()
   :outertype: ModuleGroup

   Gets all modules in this module group.

   :return: all modules in this module group.

getName
^^^^^^^

.. java:method:: public String getName()
   :outertype: ModuleGroup

   Gets the name of this module group.

   :return: the name of this module group.

getParent
^^^^^^^^^

.. java:method:: public ModuleGroup getParent()
   :outertype: ModuleGroup

   Gets the parent module group.

   :return: the parent module group.

getSystemModule
^^^^^^^^^^^^^^^

.. java:method:: public SystemModule getSystemModule()
   :outertype: ModuleGroup

   Gets the default system module.

   :return: the default system module or null if there is none.

removeChild
^^^^^^^^^^^

.. java:method:: public void removeChild(ModuleGroup group)
   :outertype: ModuleGroup

setParent
^^^^^^^^^

.. java:method:: public void setParent(ModuleGroup parent)
   :outertype: ModuleGroup

   Sets the parent module group.

   :param parent: the parent module group.

startActiveModules
^^^^^^^^^^^^^^^^^^

.. java:method:: public void startActiveModules()
   :outertype: ModuleGroup

   Starts all active modules.

stopActiveModules
^^^^^^^^^^^^^^^^^

.. java:method:: public void stopActiveModules()
   :outertype: ModuleGroup

   Stops all active modules.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: ModuleGroup

   Returns a string representation of this module group.

   :return: a string representation of this module group.

   **See also:** :java:ref:`java.lang.Object.toString()`

