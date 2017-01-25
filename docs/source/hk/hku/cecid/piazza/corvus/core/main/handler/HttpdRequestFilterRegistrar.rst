.. java:import:: hk.hku.cecid.piazza.commons.spa Extension

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginException

HttpdRequestFilterRegistrar
===========================

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.handler
   :noindex:

.. java:type:: public class HttpdRequestFilterRegistrar extends HttpdContextRegistrar

   HttpdRequestFilterRegistrar handles the registration of an HTTP request filter with the default HTTP dispatcher context.

   :author: Hugo Y. K. Lam

Methods
-------
processExtension
^^^^^^^^^^^^^^^^

.. java:method:: public void processExtension(Extension extension) throws PluginException
   :outertype: HttpdRequestFilterRegistrar

   Adds an HTTP request filter to the default HTTP dispatcher context.

   :param extension: the extension which represents the filter.
   :throws PluginException: if unable to add the request filter.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.ExtensionPointHandler.processExtensions(java.util.Collection)`

