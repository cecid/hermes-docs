.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: hk.hku.cecid.piazza.commons.servlet.http HttpRequestAdaptor

.. java:import:: hk.hku.cecid.piazza.commons.util Headers

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io InputStream

.. java:import:: java.net HttpURLConnection

.. java:import:: java.util Iterator

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.servlet.http HttpServletResponse

.. java:import:: javax.xml.soap MessageFactory

.. java:import:: javax.xml.soap MimeHeader

.. java:import:: javax.xml.soap MimeHeaders

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPFactory

.. java:import:: javax.xml.soap SOAPMessage

SOAPHttpAdaptor
===============

.. java:package:: hk.hku.cecid.piazza.commons.soap
   :noindex:

.. java:type:: public abstract class SOAPHttpAdaptor extends HttpRequestAdaptor implements SOAPRequestListener

   SOAPHttpAdaptor is both an HttpRequestListener and SOAPRequestListener. It is an adaptor for handling SOAP on Http requests.

   :author: Hugo Y. K. Lam

Fields
------
msgFactory
^^^^^^^^^^

.. java:field:: protected MessageFactory msgFactory
   :outertype: SOAPHttpAdaptor

   A SOAP message factory.

soapFactory
^^^^^^^^^^^

.. java:field:: protected SOAPFactory soapFactory
   :outertype: SOAPHttpAdaptor

   A SOAP factory.

Methods
-------
isCacheEnabled
^^^^^^^^^^^^^^

.. java:method:: protected boolean isCacheEnabled()
   :outertype: SOAPHttpAdaptor

   Checks if cache in memory should be enabled. If this method returns false, it indicates that the SOAP request object will not provide a byte array cache of the original SOAP request.

   :return: true if cache in memory should be enabled.

isSOAPFaultEnabled
^^^^^^^^^^^^^^^^^^

.. java:method:: protected boolean isSOAPFaultEnabled()
   :outertype: SOAPHttpAdaptor

   Checks if errors in the request process should be reported as a SOAP fault to the client.

   :return: true if SOAP fault reporting is enabled.

listenerCreated
^^^^^^^^^^^^^^^

.. java:method:: public void listenerCreated() throws RequestListenerException
   :outertype: SOAPHttpAdaptor

   Creates a new instance of MessageFactory.

   :throws RequestListenerException: if unable to create MessageFactory.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.servlet.RequestListener.listenerCreated()`

listenerDestroyed
^^^^^^^^^^^^^^^^^

.. java:method:: public void listenerDestroyed() throws RequestListenerException
   :outertype: SOAPHttpAdaptor

   Cleans up resources.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.servlet.RequestListener.listenerDestroyed()`

processRequest
^^^^^^^^^^^^^^

.. java:method:: public String processRequest(HttpServletRequest request, HttpServletResponse response) throws RequestListenerException
   :outertype: SOAPHttpAdaptor

   Processes the HTTP request and transforms it into a SOAP request.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.servlet.http.HttpRequestListener.processRequest(javax.servlet.http.HttpServletRequest,
   javax.servlet.http.HttpServletResponse)`

