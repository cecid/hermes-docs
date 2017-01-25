.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: hk.hku.cecid.piazza.commons.util Instance

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: java.util ArrayList

.. java:import:: java.util Iterator

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.servlet.http HttpServletResponse

.. java:import:: javax.xml.namespace QName

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPBody

.. java:import:: javax.xml.soap SOAPBodyElement

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPMessage

.. java:import:: org.w3c.dom Element

.. java:import:: org.w3c.dom Node

.. java:import:: org.w3c.dom NodeList

WebServicesAdaptor
==================

.. java:package:: hk.hku.cecid.piazza.commons.soap
   :noindex:

.. java:type:: public abstract class WebServicesAdaptor extends SOAPHttpAdaptor

   WebServicesAdaptor is a SOAPHttpAdaptor which handles web services request. This adaptor can only handles document style web services. It invokes either one of the following methods in the subclass for handling the request:

   ..

   #. public Element[] serviceRequested(Element[] bodies)
   #. public SOAPElement[] serviceRequested(SOAPElement[] bodies)
   #. public void serviceRequested(SOAPMessage req, SOAPMessage resp)
   #. public void serviceRequested(WebServicesRequest req, WebServicesResponse resp)

   :author: Hugo Y. K. Lam

Methods
-------
createElement
^^^^^^^^^^^^^

.. java:method:: protected SOAPElement createElement(String name, String value, String namespace, String xsdType) throws SOAPException
   :outertype: WebServicesAdaptor

   Creates a SOAP element.

   :param name: the element name.
   :param value: the element value.
   :param namespace: the namespace.
   :param xsdType: the XSD data type.
   :throws SOAPException: if unable to create the element.
   :return: the newly created element.

createElement
^^^^^^^^^^^^^

.. java:method:: protected SOAPElement createElement(String local, String namespace) throws SOAPException
   :outertype: WebServicesAdaptor

createElement
^^^^^^^^^^^^^

.. java:method:: protected SOAPElement createElement(String local, String namespace, String value) throws SOAPException
   :outertype: WebServicesAdaptor

createText
^^^^^^^^^^

.. java:method:: protected SOAPElement createText(String name, String value, String namespace) throws SOAPException
   :outertype: WebServicesAdaptor

   Creates a text element.

   :param name: the element name.
   :param value: the element value.
   :param namespace: the namespace.
   :throws SOAPException: if unable to create the element.
   :return: the newly created text element.

doStartRequest
^^^^^^^^^^^^^^

.. java:method:: public boolean doStartRequest(HttpServletRequest request, HttpServletResponse response) throws RequestListenerException
   :outertype: WebServicesAdaptor

   Responses with a web services descriptor if the request's query is "wsdl" or the request is a "get" method.

   :param request: the servlet request.
   :param response: the servlet response.
   :throws RequestListenerException: if there is any error in processing the request.
   :return: true if the request is not a "wsdl" request, false otherwise.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.servlet.http.HttpRequestListener.doStartRequest(javax.servlet.http.HttpServletRequest,
   javax.servlet.http.HttpServletResponse)`

getChildElementArray
^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected SOAPElement[] getChildElementArray(SOAPElement element)
   :outertype: WebServicesAdaptor

getText
^^^^^^^

.. java:method:: protected String getText(Element[] elements, String nodename)
   :outertype: WebServicesAdaptor

   Gets the text value of the element with the specified node name in the given elements.

   :param elements: the elements containing the target node.
   :param nodename: the target node name.
   :return: the text value of the specified node.

isElement
^^^^^^^^^

.. java:method:: protected boolean isElement(SOAPElement element, String local, String namespace)
   :outertype: WebServicesAdaptor

processDescriptorRequest
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected void processDescriptorRequest(OutputStream outs) throws RequestListenerException
   :outertype: WebServicesAdaptor

   Processes the WSDL request. Override to provide specific descriptor.

   :param outs: the output stream to which the descriptor should be written.
   :throws RequestListenerException: if there is error in processing the WSDL request.

processRequest
^^^^^^^^^^^^^^

.. java:method:: public void processRequest(SOAPRequest request, SOAPResponse response) throws SOAPRequestException
   :outertype: WebServicesAdaptor

   Prcoesses the SOAP request.

   :param request: the SOAP request.
   :param response: the SOAP response.
   :throws SOAPRequestException: if there is any error in processing the SOAP request.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.soap.SOAPRequestListener.processRequest(hk.hku.cecid.piazza.commons.soap.SOAPRequest,
   hk.hku.cecid.piazza.commons.soap.SOAPResponse)`

