.. java:import:: java.util Collection

ExtensionPoint
==============

.. java:package:: hk.hku.cecid.piazza.commons.spa
   :noindex:

.. java:type:: public class ExtensionPoint extends PluginComponent

   An ExtensionPoint is a plugin component which represents the extension-point element in the plugin descriptor.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`Plugin`, :java:ref:`Extension`, :java:ref:`ExtensionPointHandler`

Constructors
------------
ExtensionPoint
^^^^^^^^^^^^^^

.. java:constructor:: public ExtensionPoint(PluginComponent parent, String id, String name, String handlerClass)
   :outertype: ExtensionPoint

   Creates a new instance of ExtensionPoint.

   :param parent: the parent plugin component.
   :param id: the extension point ID.
   :param handlerClass: the handler class of this extension point.

Methods
-------
getHandlerClass
^^^^^^^^^^^^^^^

.. java:method:: public String getHandlerClass()
   :outertype: ExtensionPoint

   Gets the handler class of this extension point.

   :return: the handler class of this extension point.

getId
^^^^^

.. java:method:: public String getId()
   :outertype: ExtensionPoint

   Gets the ID of this extention point.

   :return: the ID of this extention point.

getName
^^^^^^^

.. java:method:: public String getName()
   :outertype: ExtensionPoint

   Gets the name of this extension point.

   :return: the name of this extension point.

processExtensions
^^^^^^^^^^^^^^^^^

.. java:method:: public void processExtensions(Collection extensions) throws PluginException
   :outertype: ExtensionPoint

   Processes extensions by invoking the handler class of this extension point.

   :param extensions: the extensions to be processed.
   :throws PluginException: if there is error in processing extensions by the handler

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: ExtensionPoint

   Returns a string representation of this extension point.

   :return: a string representation of this extension point.

   **See also:** :java:ref:`java.lang.Object.toString()`

