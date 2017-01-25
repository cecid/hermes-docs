.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: java.net HttpURLConnection

.. java:import:: javax.mail.internet InternetHeaders

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.servlet.http HttpServletResponse

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: hk.hku.cecid.piazza.commons.servlet.http HttpRequestAdaptor

.. java:import:: hk.hku.cecid.piazza.commons.util Headers

AS2RequestAdaptor
=================

.. java:package:: hk.hku.cecid.edi.as2.listener
   :noindex:

.. java:type:: public abstract class AS2RequestAdaptor extends HttpRequestAdaptor

   AS2RequestAdaptor

   :author: Hugo Y. K. Lam

Methods
-------
processRequest
^^^^^^^^^^^^^^

.. java:method:: public String processRequest(HttpServletRequest request, HttpServletResponse response) throws RequestListenerException
   :outertype: AS2RequestAdaptor

   processRequest

   :param request:
   :param response:
   :throws RequestListenerException:
   :return: String

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.servlet.http.HttpRequestListener.processRequest(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse)`

processRequest
^^^^^^^^^^^^^^

.. java:method:: public abstract void processRequest(AS2Request request, AS2Response response) throws RequestListenerException
   :outertype: AS2RequestAdaptor

