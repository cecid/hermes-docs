.. java:import:: hk.hku.cecid.piazza.commons.servlet.http HttpDispatcherContext

.. java:import:: hk.hku.cecid.piazza.commons.spa Plugin

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginException

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginHandler

AdminPluginHandler
==================

.. java:package:: hk.hku.cecid.piazza.corvus.admin.handler
   :noindex:

.. java:type:: public class AdminPluginHandler implements PluginHandler

   AdminPluginHandler is responsible for creating a new HTTP dispatcher context for the admin dispatcher.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.servlet.http.HttpDispatcherContext`

Fields
------
ADMIN_CONTEXT_ID
^^^^^^^^^^^^^^^^

.. java:field:: public static final String ADMIN_CONTEXT_ID
   :outertype: AdminPluginHandler

   The ID of the admin dispatcher context.

API_CONTEXT_ID
^^^^^^^^^^^^^^

.. java:field:: public static final String API_CONTEXT_ID
   :outertype: AdminPluginHandler

Methods
-------
processActivation
^^^^^^^^^^^^^^^^^

.. java:method:: public void processActivation(Plugin plugin) throws PluginException
   :outertype: AdminPluginHandler

   Processes the admin plugin activation and creates a new HTTP dispatcher context for the admin dispatcher.

   :param plugin: the plugin this handler represents.
   :throws PluginException: if activation failed.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.PluginHandler.processActivation(hk.hku.cecid.piazza.commons.spa.Plugin)`

processDeactivation
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void processDeactivation(Plugin plugin) throws PluginException
   :outertype: AdminPluginHandler

   Processes the admin plugin deactivation.

   :param plugin: the plugin this handler represents.
   :throws PluginException: if deactivation failed.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.PluginHandler.processDeactivation(hk.hku.cecid.piazza.commons.spa.Plugin)`

