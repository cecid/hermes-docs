.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: hk.hku.cecid.piazza.commons.servlet.http HttpRequestAdaptor

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: java.net HttpURLConnection

.. java:import:: java.net InetAddress

.. java:import:: java.net URL

.. java:import:: java.util Enumeration

.. java:import:: java.util Iterator

.. java:import:: java.util Map

.. java:import:: javax.servlet ServletInputStream

.. java:import:: javax.servlet ServletOutputStream

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.servlet.http HttpServletResponse

HttpProxyListener
=================

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.listener
   :noindex:

.. java:type:: public class HttpProxyListener extends HttpRequestAdaptor

   HttpProxyListener is an HTTP request listener which serves as a simple HTTP proxy handler. It does not support HTTPS nor caching.

   :author: Hugo Y. K. Lam

Methods
-------
processRequest
^^^^^^^^^^^^^^

.. java:method:: public String processRequest(HttpServletRequest request, HttpServletResponse response) throws RequestListenerException
   :outertype: HttpProxyListener

   Perform a simple HTTP proxy operation. No caching will be provided.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.servlet.http.HttpRequestListener.processRequest(javax.servlet.http.HttpServletRequest,
   javax.servlet.http.HttpServletResponse)`

