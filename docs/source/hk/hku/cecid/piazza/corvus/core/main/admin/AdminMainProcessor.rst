.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.module ModuleGroup

.. java:import:: hk.hku.cecid.piazza.commons.module SystemModule

.. java:import:: hk.hku.cecid.piazza.commons.spa Plugin

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginException

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginHandler

AdminMainProcessor
==================

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.admin
   :noindex:

.. java:type:: public class AdminMainProcessor implements PluginHandler

   The plugin handler for the Admin Main module plugin

   :author: Joel Matsumoto

Fields
------
ACTIVE_MODULE_SCHEDULER
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String ACTIVE_MODULE_SCHEDULER
   :outertype: AdminMainProcessor

   Housecleaning Scheduler Active Task module id

core
^^^^

.. java:field:: public static SystemModule core
   :outertype: AdminMainProcessor

Methods
-------
getModuleGroup
^^^^^^^^^^^^^^

.. java:method:: public static ModuleGroup getModuleGroup()
   :outertype: AdminMainProcessor

processActivation
^^^^^^^^^^^^^^^^^

.. java:method:: public void processActivation(Plugin plugin) throws PluginException
   :outertype: AdminMainProcessor

   Activate the module group from the conf files

processDeactivation
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void processDeactivation(Plugin plugin) throws PluginException
   :outertype: AdminMainProcessor

   Deactivate the modules for this module group

