.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.net ConnectionException

.. java:import:: hk.hku.cecid.piazza.commons.net HttpConnector

.. java:import:: hk.hku.cecid.piazza.commons.util Headers

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: java.net HttpURLConnection

.. java:import:: java.net MalformedURLException

.. java:import:: javax.xml.soap MessageFactory

.. java:import:: javax.xml.soap MimeHeaders

.. java:import:: javax.xml.soap SOAPMessage

SOAPHttpConnector
=================

.. java:package:: hk.hku.cecid.piazza.commons.soap
   :noindex:

.. java:type:: public class SOAPHttpConnector extends HttpConnector

   SOAPHttpConnector is an HTTP connector for making HTTP SOAP connections to an endpoint.

   :author: Hugo Y. K. Lam

Constructors
------------
SOAPHttpConnector
^^^^^^^^^^^^^^^^^

.. java:constructor:: public SOAPHttpConnector(Object endpoint) throws MalformedURLException
   :outertype: SOAPHttpConnector

   Creates a new instance of SOAPHttpConnector.

   :param endpoint: the end point, either in String or URL format.
   :throws MalformedURLException: if the end point is malformed.

Methods
-------
send
^^^^

.. java:method:: public SOAPMessage send(SOAPMessage request) throws ConnectionException
   :outertype: SOAPHttpConnector

   Sends an HTTP SOAP request.

   :param request: the SOAP request message.
   :throws ConnectionException: if failed in sending the HTTP SOAP request or creating a new connection.
   :return: the SOAP reply message responsed from the host.

send
^^^^

.. java:method:: public SOAPMessage send(SOAPMessage request, HttpURLConnection connection) throws ConnectionException
   :outertype: SOAPHttpConnector

   Sends an HTTP SOAP request using the given HTTP connection.

   :param request: the SOAP request message.
   :param connection: the HTTP connection for sending the request.
   :throws ConnectionException: if failed in sending the HTTP SOAP request.
   :return: the SOAP reply message responsed from the host.

