.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListener

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.servlet.http HttpServletResponse

HttpRequestListener
===================

.. java:package:: hk.hku.cecid.piazza.commons.servlet.http
   :noindex:

.. java:type:: public interface HttpRequestListener extends RequestListener

   HttpRequestListener is a listener for handling requests for both HTTP \ ``GET``\  and \ ``POST``\  methods.

   :author: Hugo Y. K. Lam

Methods
-------
doEndRequest
^^^^^^^^^^^^

.. java:method:: public void doEndRequest(HttpServletRequest request, HttpServletResponse response) throws RequestListenerException
   :outertype: HttpRequestListener

   Invoked after invoking processRequest().

   :param request: the servlet request.
   :param response: the servlet response.
   :throws RequestListenerException: if errors occurred during processing the request.

doStartRequest
^^^^^^^^^^^^^^

.. java:method:: public boolean doStartRequest(HttpServletRequest request, HttpServletResponse response) throws RequestListenerException
   :outertype: HttpRequestListener

   Invoked before invoking processRequest().

   :param request: the servlet request.
   :param response: the servlet response.
   :throws RequestListenerException: if errors occurred during processing the request.
   :return: true if processRequest() should be invoked.

processRequest
^^^^^^^^^^^^^^

.. java:method:: public String processRequest(HttpServletRequest request, HttpServletResponse response) throws RequestListenerException
   :outertype: HttpRequestListener

   Processes requests for both HTTP \ ``GET``\  and \ ``POST``\  methods.

   :param request: the servlet request.
   :param response: the servlet response.
   :throws RequestListenerException: if errors occurred during processing the request.
   :return: the forwarding path.

