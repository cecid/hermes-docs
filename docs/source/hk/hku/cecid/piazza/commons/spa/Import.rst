Import
======

.. java:package:: hk.hku.cecid.piazza.commons.spa
   :noindex:

.. java:type:: public class Import extends PluginComponent

   An Import is a plugin component which represents the import element in the plugin descriptor.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`Plugin`

Constructors
------------
Import
^^^^^^

.. java:constructor:: public Import(PluginComponent parent, String importedPluginId)
   :outertype: Import

   Creates a new instance of Import.

   :param parent: the parent plugin component.
   :param importedPluginId: the ID of the imported plugin.

Methods
-------
getImportedPlugin
^^^^^^^^^^^^^^^^^

.. java:method:: public Plugin getImportedPlugin()
   :outertype: Import

   Gets the imported plugin.

   :return: the imported plugin.

getImportedPluginId
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getImportedPluginId()
   :outertype: Import

   Gets the ID of the imported plugin.

   :return: the ID of the imported plugin.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: Import

   Returns a string representation of this import.

   :return: a string representation of this import.

   **See also:** :java:ref:`java.lang.Object.toString()`

