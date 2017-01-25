.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: java.io IOException

.. java:import:: java.net HttpURLConnection

.. java:import:: java.util Date

.. java:import:: java.util Iterator

.. java:import:: java.util Properties

.. java:import:: javax.servlet RequestDispatcher

.. java:import:: javax.servlet ServletConfig

.. java:import:: javax.servlet ServletException

.. java:import:: javax.servlet.http HttpServlet

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.servlet.http HttpServletResponse

HttpDispatcher
==============

.. java:package:: hk.hku.cecid.piazza.commons.servlet.http
   :noindex:

.. java:type:: public class HttpDispatcher extends HttpServlet

   HttpDispatcher is an HttpServlet which dispatches Http request to the Http request listeners registered in its Http dispatcher context.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`HttpDispatcherContext`

Fields
------
CONFIG_KEY
^^^^^^^^^^

.. java:field:: public static final String CONFIG_KEY
   :outertype: HttpDispatcher

   The request attribute key of the servlet config.

Methods
-------
destroy
^^^^^^^

.. java:method:: public void destroy()
   :outertype: HttpDispatcher

   Destroys the servlet.

doDelete
^^^^^^^^

.. java:method:: protected void doDelete(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException
   :outertype: HttpDispatcher

   Handles the HTTP \ ``POST``\  method.

   :param request: the servlet request.
   :param response: the servlet response.

doGet
^^^^^

.. java:method:: protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException
   :outertype: HttpDispatcher

   Handles the HTTP \ ``GET``\  method.

   :param request: the servlet request.
   :param response: the servlet response.

doPost
^^^^^^

.. java:method:: protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException
   :outertype: HttpDispatcher

   Handles the HTTP \ ``POST``\  method.

   :param request: the servlet request.
   :param response: the servlet response.

fireRequestAcceptedEvent
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected boolean fireRequestAcceptedEvent(HttpRequestEvent event)
   :outertype: HttpDispatcher

   Invoked before a request is processed by the listener registered at the request context path which is relative to this servlet's context path.

   :param event: the HTTP request event.
   :return: true if the request should be accepted and processed by the registered listener.

fireRequestProcessedEvent
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected void fireRequestProcessedEvent(HttpRequestEvent event)
   :outertype: HttpDispatcher

   Invoked when a request has been processed by the listener registered at the request context path which is relative to this servlet's context path.

   :param event: the HTTP request event.

getServletInfo
^^^^^^^^^^^^^^

.. java:method:: public String getServletInfo()
   :outertype: HttpDispatcher

   Gets a short description of this servlet.

   :return: a short description of this servlet.

init
^^^^

.. java:method:: public void init(ServletConfig config) throws ServletException
   :outertype: HttpDispatcher

   Initializes the servlet.

   :param config: the ServletConfig.
   :throws ServletException: if error occurred in initialization.

processRequest
^^^^^^^^^^^^^^

.. java:method:: protected void processRequest(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException
   :outertype: HttpDispatcher

   Processes requests for both HTTP \ ``GET``\  and \ ``POST``\  methods.

   :param request: servlet request.
   :param response: servlet response.

