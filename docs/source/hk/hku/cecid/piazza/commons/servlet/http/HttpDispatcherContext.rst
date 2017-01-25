.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.servlet StatefulServletContext

.. java:import:: hk.hku.cecid.piazza.commons.util Instance

.. java:import:: java.util Arrays

.. java:import:: java.util Collection

.. java:import:: java.util Enumeration

.. java:import:: java.util Hashtable

.. java:import:: java.util Properties

.. java:import:: java.util Vector

.. java:import:: javax.servlet.http HttpServletRequest

HttpDispatcherContext
=====================

.. java:package:: hk.hku.cecid.piazza.commons.servlet.http
   :noindex:

.. java:type:: public class HttpDispatcherContext extends StatefulServletContext

   An HttpDispatcherContext is a StatefulServletContext. Additionally it manages the Http request listeners for the HttpDispatcher.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`HttpDispatcher`, :java:ref:`HttpRequestListener`

Constructors
------------
HttpDispatcherContext
^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public HttpDispatcherContext()
   :outertype: HttpDispatcherContext

   Creates a new instance of HttpDispatcherContext.

Methods
-------
addContext
^^^^^^^^^^

.. java:method:: public static void addContext(String id, HttpDispatcherContext context)
   :outertype: HttpDispatcherContext

   Adds an Http dispatcher context to the embeded context store.

   :param id: the ID of the Http dispatcher context.
   :param context: the Http dispatcher context.

addRequestFilter
^^^^^^^^^^^^^^^^

.. java:method:: public boolean addRequestFilter(Object requestFilter)
   :outertype: HttpDispatcherContext

   Adds a request filter for receiving request events.

   :param requestFilter: the request filter.
   :return: true if the operation is successful, false otherwise.

getContext
^^^^^^^^^^

.. java:method:: public static HttpDispatcherContext getContext(String id)
   :outertype: HttpDispatcherContext

   Gets an Http dispatcher context from the embeded context store.

   :param id: the ID of the Http dispatcher context.
   :return: the Http dispatcher context.

getDefaultContext
^^^^^^^^^^^^^^^^^

.. java:method:: public static HttpDispatcherContext getDefaultContext()
   :outertype: HttpDispatcherContext

   Gets the default Http dispatcher context.

   :return: the default Http dispatcher context.

getListener
^^^^^^^^^^^

.. java:method:: public HttpRequestListener getListener(String pathInfo)
   :outertype: HttpDispatcherContext

   Gets the Http request listener for the specified path which is relative to its corresponding servlet's context path. If there is an exact match on the specified path, the registered listener will be returned. Else if there is a wildcard path which matches the specified path, its corresponding registered listener will be returned. Otherwise, null will be returned.

   :param pathInfo: the path information.
   :return: the HttpRequestListener registered at the specified path.

getPathInfo
^^^^^^^^^^^

.. java:method:: public String getPathInfo(HttpServletRequest request)
   :outertype: HttpDispatcherContext

   Gets the path information from the specified request. The path information will be fixed according to the internal logic of this context if necessary.

   :param request: the Http servlet request.
   :return: the path information.

getRegisteredListenersInfo
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public Properties getRegisteredListenersInfo()
   :outertype: HttpDispatcherContext

   Gets the information of all registered Http request listeners. The resulted properties will contain a set of pathInfo-listenerName pairs.

   :return: the information as properties.

getRequestFilters
^^^^^^^^^^^^^^^^^

.. java:method:: public Collection getRequestFilters()
   :outertype: HttpDispatcherContext

   Gets all the request filters in this context.

   :return: all the request filters in this context.

register
^^^^^^^^

.. java:method:: public boolean register(String pathInfo, Object requestListener)
   :outertype: HttpDispatcherContext

   Registers an Http request listener at a specified path which is relative to its corresponding servlet's context path.

   :param pathInfo: the path information.
   :param requestListener: the Http request listener, the class name of the listener, or the class of the listener.
   :return: true if the operation is successful, false otherwise.

register
^^^^^^^^

.. java:method:: public boolean register(String pathInfo, Object requestListener, Properties params)
   :outertype: HttpDispatcherContext

   Registers an Http request listener at a specified path which is relative to its corresponding servlet's context path.

   :param pathInfo: the path information.
   :param requestListener: the Http request listener, the class name of the listener, or the class of the listener.
   :param params: the parameters of the listener.
   :return: true if the operation is successful, false otherwise.

unregister
^^^^^^^^^^

.. java:method:: public boolean unregister(String pathInfo)
   :outertype: HttpDispatcherContext

   Unregisters an Http request listener at a specified path which is relative to its corresponding servlet's context path.

   :param pathInfo: the path information.
   :return: true if the operation is successful, false otherwise.

unregisterAll
^^^^^^^^^^^^^

.. java:method:: public void unregisterAll()
   :outertype: HttpDispatcherContext

   Unregisters all Http request listeners in this context.

