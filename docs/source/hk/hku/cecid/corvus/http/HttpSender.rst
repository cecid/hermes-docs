.. java:import:: java.net MalformedURLException

.. java:import:: java.net URL

.. java:import:: org.apache.http.client HttpClient

.. java:import:: org.apache.http.impl.client CloseableHttpClient

.. java:import:: org.apache.http.impl.client HttpClientBuilder

.. java:import:: org.apache.http.client.methods HttpRequestBase

.. java:import:: org.apache.http.client.methods HttpPost

.. java:import:: org.apache.http.client.methods CloseableHttpResponse

.. java:import:: org.apache.http Header

.. java:import:: org.apache.http HttpStatus

.. java:import:: org.apache.http HttpException

.. java:import:: org.apache.http.auth AuthScope

.. java:import:: org.apache.http.auth UsernamePasswordCredentials

.. java:import:: org.apache.http.auth Credentials

.. java:import:: org.apache.http.client CredentialsProvider

.. java:import:: org.apache.http.client.config RequestConfig

.. java:import:: org.apache.http.impl.auth BasicScheme

.. java:import:: org.apache.http.impl.client BasicCredentialsProvider

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data Data

HttpSender
==========

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class HttpSender implements Runnable

   The \ ``HttpSender``\  is top base class for sending HTTP request. TODO: javadoc

   :author: Twinsen Tsang

Fields
------
log
^^^

.. java:field:: protected FileLogger log
   :outertype: HttpSender

properties
^^^^^^^^^^

.. java:field:: protected Data properties
   :outertype: HttpSender

serviceEndPoint
^^^^^^^^^^^^^^^

.. java:field:: protected URL serviceEndPoint
   :outertype: HttpSender

Constructors
------------
HttpSender
^^^^^^^^^^

.. java:constructor:: public HttpSender()
   :outertype: HttpSender

   SPA Constructor. It is used when the HTTP Sender is a component in the SPA.

HttpSender
^^^^^^^^^^

.. java:constructor:: public HttpSender(FileLogger logger, Data d)
   :outertype: HttpSender

   Explicit Constructor.

   :param logger: The logger used for log message and exception.
   :param d: The data used for sending HTTP request.

HttpSender
^^^^^^^^^^

.. java:constructor:: public HttpSender(FileLogger logger, Data d, String username, String password)
   :outertype: HttpSender

   Explicit Constructor.

   :param logger: The logger used for log message and exception.
   :param d: The data used for sending HTTP request.
   :param username: The username for authentication
   :param password: The password for authentication

HttpSender
^^^^^^^^^^

.. java:constructor:: public HttpSender(FileLogger l, Data d, String endpoint)
   :outertype: HttpSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param d: The data used for sending HTTP request.
   :param endpoint: The URL of service end point.

HttpSender
^^^^^^^^^^

.. java:constructor:: public HttpSender(FileLogger l, Data d, URL endpoint)
   :outertype: HttpSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param d: The data used for sending HTTP request.
   :param endpoint: The URL of service end point.

HttpSender
^^^^^^^^^^

.. java:constructor:: public HttpSender(FileLogger l, Data d, String endpoint, String username, String password)
   :outertype: HttpSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param d: The data used for sending HTTP request.
   :param endpoint: The URL of service end point.
   :param username: The username for authentication
   :param password: The password for authentication

HttpSender
^^^^^^^^^^

.. java:constructor:: public HttpSender(FileLogger l, Data d, URL endpoint, String username, String password)
   :outertype: HttpSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param d: The data used for sending HTTP request.
   :param endpoint: The URL of service end point.
   :param username: The username for authentication
   :param password: The password for authentication

Methods
-------
closeResponse
^^^^^^^^^^^^^

.. java:method:: public void closeResponse(CloseableHttpResponse response)
   :outertype: HttpSender

   Close http response with exception handling

   :param response: the response to close

getCurrentLoopTimes
^^^^^^^^^^^^^^^^^^^

.. java:method:: public int getCurrentLoopTimes()
   :outertype: HttpSender

   Get what is the current loop times for looping

getExecutedMethod
^^^^^^^^^^^^^^^^^

.. java:method:: public HttpRequestBase getExecutedMethod()
   :outertype: HttpSender

   Get the last executed HTTP method.  This method should be invoked during \ :java:ref:`onResponse()`\ .

   :return: the last executed HTTP method.

getLoopTimes
^^^^^^^^^^^^

.. java:method:: public int getLoopTimes()
   :outertype: HttpSender

   Get how many times should the sender to be send.

getResponse
^^^^^^^^^^^

.. java:method:: public CloseableHttpResponse getResponse()
   :outertype: HttpSender

   Get the response of the last executed HTTP method. This method should be invoked during \ :java:ref:`onResponse()`\ .

   :return: the response of the last executed HTTP method

getServiceEndPoint
^^^^^^^^^^^^^^^^^^

.. java:method:: public URL getServiceEndPoint()
   :outertype: HttpSender

   Get the service end-point.

   :return: the service end-point URL.

getUserObject
^^^^^^^^^^^^^

.. java:method:: public Object getUserObject()
   :outertype: HttpSender

   Get a user object.

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: protected void initializeMessage() throws Exception
   :outertype: HttpSender

   Implements this method if you want to send messages without much different between other message to sent.

isAuthenticationRequired
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isAuthenticationRequired()
   :outertype: HttpSender

   :return: true if HTTP authentication is required.

onBeforeRequest
^^^^^^^^^^^^^^^

.. java:method:: protected void onBeforeRequest(HttpClient client, HttpRequestBase request) throws Exception
   :outertype: HttpSender

   [@EVENT] This method is invoked just before sending the request to HTTP service end-point.

   :param client: The HTTP Connection used for sending SOAP request.
   :param request: The request created by \ :java:ref:`onCreateRequest()`\ .
   :throws Exception: Any type of exception will be processed at onError(throwable t).

onCreateRequest
^^^^^^^^^^^^^^^

.. java:method:: protected HttpRequestBase onCreateRequest() throws Exception
   :outertype: HttpSender

   [@EVENT] This method is invoked when the sender is required to create a HTTP Request from configuration.  By default, this method return a PostMethod pointing to \ :java:ref:`getServiceEndPoint()`\ .

   :throws Exception: Sub-class implementation-specific exception

onEachLoopStart
^^^^^^^^^^^^^^^

.. java:method:: protected void onEachLoopStart() throws Exception
   :outertype: HttpSender

   [@EVENT] This method is invoked when each loop iteration start.

   :throws Exception: Any type of exception will be processed at onError(throw-able t).

onEnd
^^^^^

.. java:method:: protected void onEnd()
   :outertype: HttpSender

   [@EVENT] This method is invoked when the sending execution is ended.

onError
^^^^^^^

.. java:method:: protected void onError(Throwable t)
   :outertype: HttpSender

   [@EVENT] This method is invoked when there is any exception thrown during web service call.  By default, it log the throw-able \ ``t``\  to the instance logger.

onResponse
^^^^^^^^^^

.. java:method:: protected void onResponse() throws Exception
   :outertype: HttpSender

   [@EVENT] This method is invoked when received the reply HTTP response from the server. Developer can use \ :java:ref:`getExecutedMethod()`\  to get the HTTP method generated thru \ :java:ref:`onCreateRequest()`\

   :throws Exception: Any type of exception will be processed at onError(throwable t).

onStart
^^^^^^^

.. java:method:: protected void onStart()
   :outertype: HttpSender

   [@EVENT] This method is invoked when the sender begins to execute the run method.

run
^^^

.. java:method:: public void run()
   :outertype: HttpSender

   The thread execution method.

setLoopTimes
^^^^^^^^^^^^

.. java:method:: public void setLoopTimes(int loopTimes)
   :outertype: HttpSender

   Set how many times should the sender to be send.

   :param loopTimes: the new loopTimes.

setServiceEndPoint
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setServiceEndPoint(URL endpoint)
   :outertype: HttpSender

   Set the service end-point.

   :param endpoint: The URL of the web service end-point.

setServiceEndPoint
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setServiceEndPoint(String endpoint)
   :outertype: HttpSender

   Set the service end-point.

   :param endpoint: The String of the web service end-point.

setUserObject
^^^^^^^^^^^^^

.. java:method:: public void setUserObject(Object obj)
   :outertype: HttpSender

   Set a user object for call-back.

   :param obj: The user object.

