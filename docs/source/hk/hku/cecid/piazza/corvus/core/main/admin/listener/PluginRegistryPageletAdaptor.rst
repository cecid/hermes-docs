.. java:import:: hk.hku.cecid.piazza.commons.spa Plugin

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginRegistry

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.corvus.admin.listener AdminPageletAdaptor

.. java:import:: hk.hku.cecid.piazza.corvus.core Kernel

.. java:import:: java.util Collection

.. java:import:: java.util Iterator

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.transform Source

PluginRegistryPageletAdaptor
============================

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.admin.listener
   :noindex:

.. java:type:: public class PluginRegistryPageletAdaptor extends AdminPageletAdaptor

   PluginRegistryPageletAdaptor is an admin pagelet adaptor which provides an admin function of the plugin registry.

   :author: Hugo Y. K. Lam

Methods
-------
getCenterSource
^^^^^^^^^^^^^^^

.. java:method:: protected Source getCenterSource(HttpServletRequest request)
   :outertype: PluginRegistryPageletAdaptor

   Generates the transformation source of the plugin regsitry.

   **See also:** :java:ref:`hk.hku.cecid.piazza.corvus.admin.listener.AdminPageletAdaptor.getCenterSource(javax.servlet.http.HttpServletRequest)`

