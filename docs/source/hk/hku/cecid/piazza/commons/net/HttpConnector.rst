.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.module Component

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: java.net HttpURLConnection

.. java:import:: java.net MalformedURLException

.. java:import:: java.net URL

.. java:import:: java.util Iterator

.. java:import:: java.util Map

.. java:import:: java.util Vector

.. java:import:: javax.net.ssl HostnameVerifier

.. java:import:: javax.net.ssl HttpsURLConnection

.. java:import:: javax.net.ssl KeyManager

.. java:import:: javax.net.ssl SSLContext

.. java:import:: javax.net.ssl SSLSocketFactory

.. java:import:: javax.net.ssl TrustManager

HttpConnector
=============

.. java:package:: hk.hku.cecid.piazza.commons.net
   :noindex:

.. java:type:: public class HttpConnector

   HttpConnector is a connector for making HTTP/S connections to an URL.

   :author: Hugo Y. K. Lam

Constructors
------------
HttpConnector
^^^^^^^^^^^^^

.. java:constructor:: public HttpConnector(Object destUrl) throws MalformedURLException
   :outertype: HttpConnector

   Creates a new instance of HttpConnector.

   :param destUrl: the destination URL, either in String or URL format.
   :throws MalformedURLException: if the URL is malformed.

Methods
-------
addKeyManager
^^^^^^^^^^^^^

.. java:method:: public void addKeyManager(KeyManager km)
   :outertype: HttpConnector

   Adds a key manager for SSL connection.

   :param km: the key manager.

addTrustManager
^^^^^^^^^^^^^^^

.. java:method:: public void addTrustManager(TrustManager tm)
   :outertype: HttpConnector

   Adds a trust manager for SSL connection.

   :param tm: the trust manager.

createConnection
^^^^^^^^^^^^^^^^

.. java:method:: public HttpURLConnection createConnection() throws ConnectionException
   :outertype: HttpConnector

   Creates a new HTTP connection based on this connector's properties.

   :throws ConnectionException: if unable to create a new HTTP connection.
   :return: a new HTTP connection.

getHostnameVerifier
^^^^^^^^^^^^^^^^^^^

.. java:method:: public HostnameVerifier getHostnameVerifier()
   :outertype: HttpConnector

   Gets the host verifier for SSL connection.

   :return: the host name verifier.

getRequestHeaders
^^^^^^^^^^^^^^^^^

.. java:method:: public Map getRequestHeaders()
   :outertype: HttpConnector

   Gets the HTTP request headers.

   :return: the HTTP headers, or null.

getSSLSocketFactory
^^^^^^^^^^^^^^^^^^^

.. java:method:: public SSLSocketFactory getSSLSocketFactory() throws ConnectionException
   :outertype: HttpConnector

   Gets the SSL socket factory which is used in SSL connection.

   :throws ConnectionException: if unable to create SSL socket factory.
   :return: the SSL socket factory.

send
^^^^

.. java:method:: public InputStream send(InputStream request) throws ConnectionException
   :outertype: HttpConnector

   Sends an HTTP/S request using the given HTTP connection.

   :param request: the HTTP request content or null for a simple get request.
   :throws ConnectionException: if failed in sending the HTTP request or creating a new connection.
   :return: an input stream for reading the reply from the host.

send
^^^^

.. java:method:: public InputStream send(InputStream request, HttpURLConnection connection) throws ConnectionException
   :outertype: HttpConnector

   Sends an HTTP/S request using the given HTTP connection.

   :param request: the HTTP request content or null for a simple get request.
   :param connection: the HTTP connection for sending the request.
   :throws ConnectionException: if failed in sending the HTTP request.
   :return: an input stream for reading the reply from the host.

setHostnameVerifier
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setHostnameVerifier(HostnameVerifier hostnameVerifier)
   :outertype: HttpConnector

   Sets a host name verifier for SSL connection.

   :param hostnameVerifier: the host name verifier.

setRequestHeaders
^^^^^^^^^^^^^^^^^

.. java:method:: public void setRequestHeaders(Map headers)
   :outertype: HttpConnector

   Sets the HTTP request headers.

   :param headers: the HTTP headers.

