.. java:import:: hk.hku.cecid.piazza.commons.spa Extension

.. java:import:: hk.hku.cecid.piazza.commons.spa ExtensionPointIteratedHandler

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginException

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: hk.hku.cecid.piazza.corvus.admin.listener AdminPageletAdaptor

.. java:import:: hk.hku.cecid.piazza.corvus.admin.menu MenuComponent

.. java:import:: java.net URL

AdminModuleRegistrar
====================

.. java:package:: hk.hku.cecid.piazza.corvus.admin.handler
   :noindex:

.. java:type:: public class AdminModuleRegistrar extends ExtensionPointIteratedHandler

   AdminModuleRegistrar handles the registration of an admin module with the default admin pagelet adaptor.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`hk.hku.cecid.piazza.corvus.admin.listener.AdminPageletAdaptor`

Methods
-------
processExtension
^^^^^^^^^^^^^^^^

.. java:method:: public void processExtension(Extension extension) throws PluginException
   :outertype: AdminModuleRegistrar

   Adds an admin module to the default admin pagelet adaptor.

   :param extension: the extension which represents the module to be added.
   :throws PluginException: if unable to add the module.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.ExtensionPointHandler.processExtensions(java.util.Collection)`

