.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io InputStream

.. java:import:: java.io StringWriter

.. java:import:: java.net HttpURLConnection

.. java:import:: java.util Enumeration

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: java.util Map

.. java:import:: java.util StringTokenizer

.. java:import:: javax.mail Header

.. java:import:: javax.mail.internet InternetHeaders

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.servlet.http HttpServletResponse

.. java:import:: javax.xml.soap MimeHeader

.. java:import:: javax.xml.soap MimeHeaders

Headers
=======

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public class Headers

   The Headers class represents the headers of an HTTP URL connection or of the HTTP servlet request and response.

   :author: Hugo Y. K. Lam

Constructors
------------
Headers
^^^^^^^

.. java:constructor:: public Headers(HttpURLConnection connection)
   :outertype: Headers

   Creates a new instance of Headers.

   :param connection: the HTTP connection for getting or setting the headers.

Headers
^^^^^^^

.. java:constructor:: public Headers(HttpServletRequest request, HttpServletResponse response)
   :outertype: Headers

   Creates a new instance of Headers.

   :param request: the servlet request for getting the headers.
   :param response: the servlet response for setting the headers.

Methods
-------
getInputStreamHeaders
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public InputStream getInputStreamHeaders()
   :outertype: Headers

   Gets the headers as an input stream from the underlying request object.

   :return: an input stream of the headers.

getInternetHeaders
^^^^^^^^^^^^^^^^^^

.. java:method:: public InternetHeaders getInternetHeaders()
   :outertype: Headers

   Gets the Internet headers from the underlying request object.

   :return: the Internet headers.

getMimeHeaders
^^^^^^^^^^^^^^

.. java:method:: public MimeHeaders getMimeHeaders()
   :outertype: Headers

   Gets the mime headers from the underlying request object.

   :return: the mime headers.

putInternetHeaders
^^^^^^^^^^^^^^^^^^

.. java:method:: public void putInternetHeaders(InternetHeaders headers)
   :outertype: Headers

   Puts the Internet headers into the underlying response object.

   :param headers: the Internet headers.

putMimeHeaders
^^^^^^^^^^^^^^

.. java:method:: public void putMimeHeaders(MimeHeaders headers)
   :outertype: Headers

   Puts the mime headers into the underlying response object.

   :param headers: the mime headers.

