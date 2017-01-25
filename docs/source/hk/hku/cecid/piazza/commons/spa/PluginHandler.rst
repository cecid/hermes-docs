PluginHandler
=============

.. java:package:: hk.hku.cecid.piazza.commons.spa
   :noindex:

.. java:type:: public interface PluginHandler

   A PluginHandler handles the activation process of a plugin.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`Plugin`

Methods
-------
processActivation
^^^^^^^^^^^^^^^^^

.. java:method:: public void processActivation(Plugin plugin) throws PluginException
   :outertype: PluginHandler

   Processes the activation of the plugin this handler represents. It is invoked when the plugin is being activated.

   :param plugin: the plugin this handler represents.
   :throws PluginException: if activation failed.

processDeactivation
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void processDeactivation(Plugin plugin) throws PluginException
   :outertype: PluginHandler

   Processes the deactivation of the plugin this handler represents. It is invoked when the plugin is being deactivated.

   :param plugin: the plugin this handler represents.
   :throws PluginException: if deactivation failed.

