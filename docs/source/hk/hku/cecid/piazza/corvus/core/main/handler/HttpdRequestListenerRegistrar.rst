.. java:import:: hk.hku.cecid.piazza.commons.spa Extension

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginException

HttpdRequestListenerRegistrar
=============================

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.handler
   :noindex:

.. java:type:: public class HttpdRequestListenerRegistrar extends HttpdContextRegistrar

   HttpdRequestListenerRegistrar handles the registration of an HTTP request listener with the default HTTP dispatcher context.

   :author: Hugo Y. K. Lam

Methods
-------
processExtension
^^^^^^^^^^^^^^^^

.. java:method:: public void processExtension(Extension extension) throws PluginException
   :outertype: HttpdRequestListenerRegistrar

   Adds an HTTP request listener to the default HTTP dispatcher context.

   :param extension: the extension which represents the listener.
   :throws PluginException: if unable to add the request listener.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.ExtensionPointHandler.processExtensions(java.util.Collection)`

