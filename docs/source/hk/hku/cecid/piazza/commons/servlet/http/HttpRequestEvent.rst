.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.servlet.http HttpServletResponse

HttpRequestEvent
================

.. java:package:: hk.hku.cecid.piazza.commons.servlet.http
   :noindex:

.. java:type:: public class HttpRequestEvent

   HttpRequestEvent represents an event of an HTTP request.

   :author: Hugo Y. K. Lam

Constructors
------------
HttpRequestEvent
^^^^^^^^^^^^^^^^

.. java:constructor::  HttpRequestEvent()
   :outertype: HttpRequestEvent

   Creates a new instance of HttpRequestEvent.

HttpRequestEvent
^^^^^^^^^^^^^^^^

.. java:constructor::  HttpRequestEvent(String pathInfo, HttpServletRequest request, HttpServletResponse response)
   :outertype: HttpRequestEvent

   Creates a new instance of HttpRequestEvent.

   :param pathInfo: the path information.
   :param request: the request object.
   :param response: the response object.

Methods
-------
getPathInfo
^^^^^^^^^^^

.. java:method:: public String getPathInfo()
   :outertype: HttpRequestEvent

   Gets the path information.

   :return: the path information.

getRequest
^^^^^^^^^^

.. java:method:: public HttpServletRequest getRequest()
   :outertype: HttpRequestEvent

   Gets the request object.

   :return: the request object.

getResponse
^^^^^^^^^^^

.. java:method:: public HttpServletResponse getResponse()
   :outertype: HttpRequestEvent

   Gets the response object.

   :return: the response object.

setPathInfo
^^^^^^^^^^^

.. java:method::  void setPathInfo(String pathInfo)
   :outertype: HttpRequestEvent

   Sets the path information.

   :param pathInfo: the path information.

setRequest
^^^^^^^^^^

.. java:method::  void setRequest(HttpServletRequest request)
   :outertype: HttpRequestEvent

   Sets the request object.

   :param request: the request object.

setResponse
^^^^^^^^^^^

.. java:method::  void setResponse(HttpServletResponse response)
   :outertype: HttpRequestEvent

   Sets the response object.

   :param response: the response object.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: HttpRequestEvent

   Returns a string representation of this event.

   :return: a string representation of this event.

   **See also:** :java:ref:`java.lang.Object.toString()`

