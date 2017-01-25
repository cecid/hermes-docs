.. java:import:: hk.hku.cecid.piazza.commons.servlet.http HttpDispatcherContext

.. java:import:: hk.hku.cecid.piazza.commons.spa Extension

.. java:import:: hk.hku.cecid.piazza.corvus.core.main.handler HttpdRequestFilterRegistrar

AdminRequestFilterRegistrar
===========================

.. java:package:: hk.hku.cecid.piazza.corvus.admin.handler
   :noindex:

.. java:type:: public class AdminRequestFilterRegistrar extends HttpdRequestFilterRegistrar

   AdminRequestFilterRegistrar handles the registration of an HTTP request filter with the admin dispatcher context.

   :author: Hugo Y. K. Lam

Methods
-------
getHttpdContext
^^^^^^^^^^^^^^^

.. java:method:: protected HttpDispatcherContext getHttpdContext(Extension extension)
   :outertype: AdminRequestFilterRegistrar

   Gets the admin dispatcher context.

   **See also:** :java:ref:`hk.hku.cecid.piazza.corvus.core.main.handler.HttpdContextRegistrar.getHttpdContext(hk.hku.cecid.piazza.commons.spa.Extension)`

