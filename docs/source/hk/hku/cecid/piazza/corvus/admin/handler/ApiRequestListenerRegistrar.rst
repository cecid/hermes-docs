.. java:import:: hk.hku.cecid.piazza.commons.servlet.http HttpDispatcherContext

.. java:import:: hk.hku.cecid.piazza.commons.spa Extension

.. java:import:: hk.hku.cecid.piazza.corvus.core.main.handler HttpdRequestListenerRegistrar

ApiRequestListenerRegistrar
===========================

.. java:package:: hk.hku.cecid.piazza.corvus.admin.handler
   :noindex:

.. java:type:: public class ApiRequestListenerRegistrar extends HttpdRequestListenerRegistrar

   ApiRequestListenerRegistrar handles the registration of an HTTP request listener with the API dispatcher context.

   :author: Patrick Yee

Methods
-------
getHttpdContext
^^^^^^^^^^^^^^^

.. java:method:: protected HttpDispatcherContext getHttpdContext(Extension extension)
   :outertype: ApiRequestListenerRegistrar

   Gets the admin dispatcher context.

   **See also:** :java:ref:`hk.hku.cecid.piazza.corvus.core.main.handler.HttpdContextRegistrar.getHttpdContext(hk.hku.cecid.piazza.commons.spa.Extension)`

