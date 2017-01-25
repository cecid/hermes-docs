PluginComponent
===============

.. java:package:: hk.hku.cecid.piazza.commons.spa
   :noindex:

.. java:type:: public class PluginComponent

   A PluginComponent represents any components compose the plugin, including the plugin itself.

   :author: Hugo Y. K. Lam

Constructors
------------
PluginComponent
^^^^^^^^^^^^^^^

.. java:constructor:: public PluginComponent(PluginComponent parent)
   :outertype: PluginComponent

   Creates a new instance of PluginComponent.

   :param parent: the parent component.

Methods
-------
getParent
^^^^^^^^^

.. java:method:: public PluginComponent getParent()
   :outertype: PluginComponent

   Gets the parent component of this plugin component.

   :return: the parent component of this plugin component.

getPlugin
^^^^^^^^^

.. java:method:: public Plugin getPlugin()
   :outertype: PluginComponent

   Gets the plugin which holds this plugin component.

   :return: the plugin which holds this plugin component.

