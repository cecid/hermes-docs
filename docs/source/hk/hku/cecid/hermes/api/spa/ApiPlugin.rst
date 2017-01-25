.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.module ModuleGroup

.. java:import:: hk.hku.cecid.piazza.commons.module SystemModule

.. java:import:: hk.hku.cecid.piazza.commons.spa Plugin

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginException

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginHandler

ApiPlugin
=========

.. java:package:: hk.hku.cecid.hermes.api.spa
   :noindex:

.. java:type:: public class ApiPlugin implements PluginHandler

   :author: Patrick Yee

Fields
------
core
^^^^

.. java:field:: public static SystemModule core
   :outertype: ApiPlugin

Methods
-------
getModuleGroup
^^^^^^^^^^^^^^

.. java:method:: public static ModuleGroup getModuleGroup()
   :outertype: ApiPlugin

   :return: the Api module group

processActivation
^^^^^^^^^^^^^^^^^

.. java:method:: public void processActivation(Plugin plugin) throws PluginException
   :outertype: ApiPlugin

processDeactivation
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void processDeactivation(Plugin arg0) throws PluginException
   :outertype: ApiPlugin

