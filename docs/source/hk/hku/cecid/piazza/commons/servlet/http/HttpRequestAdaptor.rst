.. java:import:: java.util Properties

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.servlet.http HttpServletResponse

HttpRequestAdaptor
==================

.. java:package:: hk.hku.cecid.piazza.commons.servlet.http
   :noindex:

.. java:type:: public abstract class HttpRequestAdaptor implements HttpRequestListener

   HttpRequestAdaptor is an abstract adapter class for handling HTTP requests. The methods in this class are empty. This class exists as convenience for creating listener objects.

   :author: Hugo Y. K. Lam

Fields
------
parameters
^^^^^^^^^^

.. java:field:: protected final Properties parameters
   :outertype: HttpRequestAdaptor

   The parameters of this listener.

Methods
-------
doEndRequest
^^^^^^^^^^^^

.. java:method:: public void doEndRequest(HttpServletRequest request, HttpServletResponse response) throws RequestListenerException
   :outertype: HttpRequestAdaptor

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.servlet.http.HttpRequestListener.doEndRequest(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse)`

doStartRequest
^^^^^^^^^^^^^^

.. java:method:: public boolean doStartRequest(HttpServletRequest request, HttpServletResponse response) throws RequestListenerException
   :outertype: HttpRequestAdaptor

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.servlet.http.HttpRequestListener.doStartRequest(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse)`

getParameters
^^^^^^^^^^^^^

.. java:method:: public Properties getParameters()
   :outertype: HttpRequestAdaptor

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.servlet.RequestListener.getParameters()`

listenerCreated
^^^^^^^^^^^^^^^

.. java:method:: public void listenerCreated() throws RequestListenerException
   :outertype: HttpRequestAdaptor

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.servlet.RequestListener.listenerCreated()`

listenerDestroyed
^^^^^^^^^^^^^^^^^

.. java:method:: public void listenerDestroyed() throws RequestListenerException
   :outertype: HttpRequestAdaptor

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.servlet.RequestListener.listenerDestroyed()`

