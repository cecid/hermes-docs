.. java:import:: hk.hku.cecid.piazza.commons.pagelet Pagelet

.. java:import:: hk.hku.cecid.piazza.commons.pagelet PageletStore

.. java:import:: hk.hku.cecid.piazza.commons.spa Extension

.. java:import:: hk.hku.cecid.piazza.commons.spa ExtensionPointIteratedHandler

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginException

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: hk.hku.cecid.piazza.corvus.admin.listener AdminPageletAdaptor

.. java:import:: java.net URL

AdminPageletRegistrar
=====================

.. java:package:: hk.hku.cecid.piazza.corvus.admin.handler
   :noindex:

.. java:type:: public class AdminPageletRegistrar extends ExtensionPointIteratedHandler

   AdminPageletRegistrar handles the registration of a pagelet with the default admin pagelet adaptor.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`hk.hku.cecid.piazza.corvus.admin.listener.AdminPageletAdaptor`

Methods
-------
getPageletStore
^^^^^^^^^^^^^^^

.. java:method:: protected PageletStore getPageletStore(Extension extension)
   :outertype: AdminPageletRegistrar

   Gets the pagelet store this registrar manages.

   :param extension: the extension being processed.
   :return: the pagelet store of the default admin pagelet adaptor.

processExtension
^^^^^^^^^^^^^^^^

.. java:method:: public void processExtension(Extension extension) throws PluginException
   :outertype: AdminPageletRegistrar

   Adds a pagelet to the pagelet store that this registrar manages.

   :param extension: the extension which represents the pagelet to be added.
   :throws PluginException: if unable to add the pagelet.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.ExtensionPointHandler.processExtensions(java.util.Collection)`

