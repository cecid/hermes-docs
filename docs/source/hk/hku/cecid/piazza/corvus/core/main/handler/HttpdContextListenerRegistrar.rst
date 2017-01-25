.. java:import:: hk.hku.cecid.piazza.commons.spa Extension

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginException

HttpdContextListenerRegistrar
=============================

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.handler
   :noindex:

.. java:type:: public class HttpdContextListenerRegistrar extends HttpdContextRegistrar

   HttpdContextListenerRegistrar handles the registration of an HTTP dispatcher context listener with the default HTTP dispatcher context.

   :author: Hugo Y. K. Lam

Methods
-------
processExtension
^^^^^^^^^^^^^^^^

.. java:method:: public void processExtension(Extension extension) throws PluginException
   :outertype: HttpdContextListenerRegistrar

   Adds an HTTP dispatcher context listener to the default HTTP dispatcher context.

   :param extension: the extension which represents the listener.
   :throws PluginException: if unable to add the context listener.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.ExtensionPointHandler.processExtensions(java.util.Collection)`

