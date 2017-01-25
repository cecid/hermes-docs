.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOFactory

.. java:import:: hk.hku.cecid.piazza.commons.spa Plugin

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginException

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginHandler

.. java:import:: hk.hku.cecid.piazza.commons.util Logger

.. java:import:: hk.hku.cecid.piazza.commons.util PropertySheet

PluginProcessor
===============

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public abstract class PluginProcessor implements PluginHandler

Methods
-------
getDAOFactory
^^^^^^^^^^^^^

.. java:method:: public DAOFactory getDAOFactory()
   :outertype: PluginProcessor

getLogger
^^^^^^^^^

.. java:method:: public Logger getLogger()
   :outertype: PluginProcessor

getModuleGroup
^^^^^^^^^^^^^^

.. java:method:: public ModuleGroup getModuleGroup() throws ModuleException
   :outertype: PluginProcessor

getModuleGroupImpl
^^^^^^^^^^^^^^^^^^

.. java:method:: protected abstract ModuleGroup getModuleGroupImpl()
   :outertype: PluginProcessor

getProperties
^^^^^^^^^^^^^

.. java:method:: public PropertySheet getProperties()
   :outertype: PluginProcessor

getProperties
^^^^^^^^^^^^^

.. java:method:: public String[] getProperties(String key)
   :outertype: PluginProcessor

getProperty
^^^^^^^^^^^

.. java:method:: public String getProperty(String key)
   :outertype: PluginProcessor

getProperty
^^^^^^^^^^^

.. java:method:: public String getProperty(String key, String def)
   :outertype: PluginProcessor

getSystemComponent
^^^^^^^^^^^^^^^^^^

.. java:method:: public Component getSystemComponent(String id) throws ModuleException
   :outertype: PluginProcessor

getSystemModule
^^^^^^^^^^^^^^^

.. java:method:: public SystemModule getSystemModule() throws ModuleException
   :outertype: PluginProcessor

processActivation
^^^^^^^^^^^^^^^^^

.. java:method:: public void processActivation(Plugin plugin) throws PluginException
   :outertype: PluginProcessor

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.PluginHandler.processActivation(Plugin)`

processDeactivation
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void processDeactivation(Plugin plugin) throws PluginException
   :outertype: PluginProcessor

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.PluginHandler.processDeactivation(Plugin)`

setModuleGroup
^^^^^^^^^^^^^^

.. java:method:: public void setModuleGroup(ModuleGroup moduleGroup) throws ModuleException
   :outertype: PluginProcessor

setModuleGroupImpl
^^^^^^^^^^^^^^^^^^

.. java:method:: protected abstract void setModuleGroupImpl(ModuleGroup moduleGroup)
   :outertype: PluginProcessor

