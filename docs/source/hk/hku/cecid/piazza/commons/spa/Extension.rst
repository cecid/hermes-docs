.. java:import:: java.util Properties

Extension
=========

.. java:package:: hk.hku.cecid.piazza.commons.spa
   :noindex:

.. java:type:: public class Extension extends PluginComponent

   An Extension is a plugin component which represents the extension element in the plugin descriptor.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`Plugin`, :java:ref:`ExtensionPoint`

Constructors
------------
Extension
^^^^^^^^^

.. java:constructor:: public Extension(PluginComponent parent, String point, String name)
   :outertype: Extension

   Creates a new instance of Extension.

   :param parent: the parent plugin component.
   :param point: the extension point this extension extends.
   :param name: the extension name.

Extension
^^^^^^^^^

.. java:constructor:: public Extension(PluginComponent parent, String point, String name, Properties parameters)
   :outertype: Extension

   Creates a new instance of Extension.

   :param parent: the parent plugin component.
   :param point: the extension point this extension extends.
   :param name: the extension name.
   :param parameters: the extension parameters.

Methods
-------
getName
^^^^^^^

.. java:method:: public String getName()
   :outertype: Extension

   Gets the extension name.

   :return: the extension name.

getParameter
^^^^^^^^^^^^

.. java:method:: public String getParameter(String key)
   :outertype: Extension

   Gets an extension parameter.

   :param key: the key of the parameter.
   :return: the parameter.

getParameters
^^^^^^^^^^^^^

.. java:method:: public Properties getParameters()
   :outertype: Extension

   Gets the extension parameters.

   :return: the parameters.

getPoint
^^^^^^^^

.. java:method:: public String getPoint()
   :outertype: Extension

   Gets the extension point this extension extends.

   :return: the extension point.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: Extension

   Returns a string representation of this extension.

   :return: a string representation of this extension.

   **See also:** :java:ref:`java.lang.Object.toString()`

