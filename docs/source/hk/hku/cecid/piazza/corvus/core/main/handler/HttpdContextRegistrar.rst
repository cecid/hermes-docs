.. java:import:: hk.hku.cecid.piazza.commons.servlet.http HttpDispatcherContext

.. java:import:: hk.hku.cecid.piazza.commons.spa Extension

.. java:import:: hk.hku.cecid.piazza.commons.spa ExtensionPointIteratedHandler

HttpdContextRegistrar
=====================

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.handler
   :noindex:

.. java:type:: public abstract class HttpdContextRegistrar extends ExtensionPointIteratedHandler

   HttpdContextRegistrar is a generic registrar for any extension point handler which handles reqistration, or alike, with an HTTP dispatcher context.

   :author: Hugo Y. K. Lam

Methods
-------
getHttpdContext
^^^^^^^^^^^^^^^

.. java:method:: protected HttpDispatcherContext getHttpdContext(Extension extension)
   :outertype: HttpdContextRegistrar

   Gets the HTTP dispatcher context this registrar manages.

   :param extension: the extension being processed.
   :return: the default HTTP dispatcher context.

