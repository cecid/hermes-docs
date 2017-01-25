.. java:import:: java.util List

.. java:import:: java.net PasswordAuthentication

.. java:import:: java.net URL

.. java:import:: java.net Authenticator

.. java:import:: java.net MalformedURLException

.. java:import:: javax.xml.soap SOAPConnection

.. java:import:: javax.xml.soap SOAPConnectionFactory

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPMessage

.. java:import:: javax.xml.soap SOAPBody

.. java:import:: javax.xml.soap MessageFactory

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.util SOAPUtilities

.. java:import:: hk.hku.cecid.corvus.ws.data Data

.. java:import:: hk.hku.cecid.piazza.commons.module Component

.. java:import:: hk.hku.cecid.piazza.commons.util UtilitiesException

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

SOAPSender
==========

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public abstract class SOAPSender extends Component implements Runnable

   The \ ``SOAPSender``\  is a abstract class for the \ *SOAP*\ -Based protocol client. It reduces the complexity and version incompatible induced from the apache AXIS by using only Built-in java SOAP XML Package. The target developer is for those whose are not familiar with the complex AXIS framework. It is implemented using the event-driven model so that developer are only required to implement several event method. The package is under development and will be standardized in the future release.

   :author: Twinsen Tsang

Fields
------
NS_PREFIX
^^^^^^^^^

.. java:field:: protected static final String NS_PREFIX
   :outertype: SOAPSender

   The namespace prefix

log
^^^

.. java:field:: protected FileLogger log
   :outertype: SOAPSender

   The logger used for log message and exception

   **See also:** :java:ref:`hk.hku.cecid.corvus.util.FileLogger`

properties
^^^^^^^^^^

.. java:field:: protected Data properties
   :outertype: SOAPSender

   The data properties for this sender.

request
^^^^^^^

.. java:field:: protected SOAPMessage request
   :outertype: SOAPSender

   The SOAP request

response
^^^^^^^^

.. java:field:: protected SOAPMessage response
   :outertype: SOAPSender

   The SOAP response

serviceEndPoint
^^^^^^^^^^^^^^^

.. java:field:: protected URL serviceEndPoint
   :outertype: SOAPSender

   The url of service end point.

Constructors
------------
SOAPSender
^^^^^^^^^^

.. java:constructor:: public SOAPSender()
   :outertype: SOAPSender

   SPA Constructor. It is used when the SOAP Sender is a component in the spa.

SOAPSender
^^^^^^^^^^

.. java:constructor:: public SOAPSender(FileLogger l, Data d)
   :outertype: SOAPSender

   Constructor

   :param l: The logger used for log message and exception.

SOAPSender
^^^^^^^^^^

.. java:constructor:: public SOAPSender(FileLogger l, Data d, String endpoint)
   :outertype: SOAPSender

   Constructor

   :param l: The logger used for log message and exception.
   :param endpoint: The url of service end point.

SOAPSender
^^^^^^^^^^

.. java:constructor:: public SOAPSender(FileLogger l, Data d, URL endpoint)
   :outertype: SOAPSender

   Constructor.

   :param l: The logger used for log message and exception.
   :param endpoint: The url of service end point.

Methods
-------
addRequestElementText
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean addRequestElementText(String tagName, String tagValue, String nsPrefix, String nsURI) throws SOAPException
   :outertype: SOAPSender

   Add SOAP element to body with name and value.

   :param tagName: The tag name of element to be retrieved.
   :param tagValue: The value of the element to be added.
   :param nsPrefix: The namespace Prefix
   :param nsURI: The namespace URI.
   :throws SOAPException:
   :return: true if the creation and addition is successfully.

addRequestElementText
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean addRequestElementText(String parentTagName, String parentNsURI, String tagName, String tagValue, String nsPrefix, String nsURI) throws SOAPException
   :outertype: SOAPSender

   Add SOAP element to specify parent element

   :param parentTagName: The tag name of parent element.
   :param parentNsURI: The namespace URI of parent element.
   :param tagName: The tag name of element to be retrieved.
   :param tagValue: The value of the element to be added.
   :param nsPrefix: The namespace Prefix
   :param nsURI: The namespace URI.
   :throws SOAPException:
   :return: true if the creation and linking is successfully.

countResponseElementText
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int countResponseElementText(String tagname, String nsURI) throws SOAPException
   :outertype: SOAPSender

   This methods count number of specified \ ``tagname``\  in the response. It should only be called inside \ :java:ref:`onResponse()`\ .

   :param tagname: The tag name of element to be retrieved.
   :param nsURI: The namespace URI.
   :throws SOAPException:
   :return: The element text in the tagname specified.

getCurrentLoopTimes
^^^^^^^^^^^^^^^^^^^

.. java:method:: public int getCurrentLoopTimes()
   :outertype: SOAPSender

   Get what is the current loop times for looping

getLoopTimes
^^^^^^^^^^^^

.. java:method:: public int getLoopTimes()
   :outertype: SOAPSender

   Get how many times should the sender to be send.

getRequestElementText
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getRequestElementText(String tagname, String nsURI, int whichOne) throws SOAPException
   :outertype: SOAPSender

   This method should only be called inside \ :java:ref:`onCreateRequest()`\ . because the request object will be deleted upon each ws call.

   :param tagname: The tag name of element to be retrieved.
   :param nsURI: The namespace URI.
   :param whichOne: The nth child element to be returned.

getResponseElementAsList
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String[] getResponseElementAsList(String tagname, String nsURI) throws SOAPException
   :outertype: SOAPSender

   This method should only be called inside \ :java:ref:`onResponse()`\ . because the response object will be deleted upon each ws call. This method get the element by it's \ ``tagname``\  and return a list of text value inside.

   :param tagname: The name of the XML tag to be extraceted.
   :param nsURI: The namespace URI.
   :throws SOAPException:
   :return: The elements' text in the tagname specified.

getResponseElementText
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getResponseElementText(String tagname, String nsURI, int whichOne) throws SOAPException
   :outertype: SOAPSender

   This method should only be called inside \ :java:ref:`onResponse()`\ . because the response object will be deleted upon each ws call.

   :param tagname: The tag name of element to be retrieved.
   :param nsURI: The namespace URI.
   :param whichOne: The nth child element to be returned.
   :return: The element text in the tagname specified.

getSOAPRequest
^^^^^^^^^^^^^^

.. java:method:: protected SOAPMessage getSOAPRequest()
   :outertype: SOAPSender

   Get the SOAP request.

   :return: The SOAP Request Body.

getSOAPResponse
^^^^^^^^^^^^^^^

.. java:method:: protected SOAPMessage getSOAPResponse()
   :outertype: SOAPSender

   Get the SOAP response. The method should only be called inside \ :java:ref:`onResponse()`\ .

   :return: The SOAP Response Body.

getServiceEndPoint
^^^^^^^^^^^^^^^^^^

.. java:method:: public URL getServiceEndPoint()
   :outertype: SOAPSender

   Get the service end-point.

   :return: the service endpoint URL.

getUserObject
^^^^^^^^^^^^^

.. java:method:: public Object getUserObject()
   :outertype: SOAPSender

   Get a user object.

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: SOAPSender

   Implements this method if you want to send messages without much different between other message to sent.

isRequestDirty
^^^^^^^^^^^^^^

.. java:method:: public boolean isRequestDirty()
   :outertype: SOAPSender

   :return: return true if the request is dirty.

isRequireXMLDeclaraction
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isRequireXMLDeclaraction()
   :outertype: SOAPSender

   return return true if the request requires the XML declaration to sent.

onBeforeRequest
^^^^^^^^^^^^^^^

.. java:method:: public void onBeforeRequest(SOAPConnection conn, SOAPMessage request) throws Exception
   :outertype: SOAPSender

   [@EVENT] This method is invoked just before sending the request to Web service endpoints.

   :param conn: The SOAP Connection used for sending SOAP request.
   :param request: The request created by \ :java:ref:`onCreateRequest()`\ .
   :throws Exception: Any type of exception will be processed at onError(throwable t).

onCreateRequest
^^^^^^^^^^^^^^^

.. java:method:: public SOAPMessage onCreateRequest() throws Exception
   :outertype: SOAPSender

   [@EVENT] This method is invoked when the sender is required to sent a SOAP Request for configuration. The default return value is the request in the sender.
   If developer want to send a custom SOAP request other than the sender
   SOAP request, override the function and return your
   customizing SOAP Request.
   For example, if you want to send a SOAP request always with soap element "test". Then you should override this function called.

   .. parsed-literal::

      public SOAPMessage onCreateRequest() throws Exception{
          SOAPMessage request = MessageFactory.newInstance().createMessage();
                   ..
                   ..
                 add the element "test".
          return request;
      }

   :throws Exception: Any type of exception will be processed at onError(throwable t).
   :return: javax.xml.SOAPMessage

onEachLoopStart
^^^^^^^^^^^^^^^

.. java:method:: public void onEachLoopStart() throws Exception
   :outertype: SOAPSender

   [@EVENT] This method is invoked when each loop iteration start.

   :throws Exception: Any type of exception will be processed at onError(throwable t).

onEnd
^^^^^

.. java:method:: public void onEnd()
   :outertype: SOAPSender

   [@EVENT] This method is invoked when the sending execution is ended.

onError
^^^^^^^

.. java:method:: public void onError(Throwable t)
   :outertype: SOAPSender

   [@EVENT] This method is invoked when there is any exception thrown during web service call.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: SOAPSender

   [@EVENT] This method is invoked when received the reply SOAP response from the server Developer can use \ :java:ref:`getSOAPResponse()`\  to get the SOAP response for self-handling. Otherwise, developer can use \ :java:ref:`getResponseElementText(String,String,int)`\  to get the response element text from the response object.

   :throws Exception: Any type of exception will be processed at onError(throwable t).

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: SOAPSender

   [@EVENT] This method is invoked when the sender begins to execute the run method.

resetSOAPRequest
^^^^^^^^^^^^^^^^

.. java:method:: protected void resetSOAPRequest() throws SOAPException
   :outertype: SOAPSender

   Reset the request to empty SOAP Body. It is commonly used when for each loop times the request

   :throws SOAPException:

resetSOAPResponse
^^^^^^^^^^^^^^^^^

.. java:method:: protected void resetSOAPResponse() throws SOAPException
   :outertype: SOAPSender

   Reset the request to empty SOAP Body. It is commonly used when for each loop times the response.

run
^^^

.. java:method:: public void run()
   :outertype: SOAPSender

   The thread execution method.

setBasicAuthentication
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setBasicAuthentication(String username, String password)
   :outertype: SOAPSender

   Set to use the basic authentication when calling the web service.

   :param username: The username for basic authentication.
   :param password: The password for basic authentication.

setLoopTimes
^^^^^^^^^^^^

.. java:method:: public void setLoopTimes(int loopTimes)
   :outertype: SOAPSender

   Set how many times should the sender to be send.

   :param loopTimes: the new loopTimes.

setRequestDirty
^^^^^^^^^^^^^^^

.. java:method:: public void setRequestDirty(boolean dirty)
   :outertype: SOAPSender

   Set if the request is dirty. We considered "dirty" as the request has been modified by someone during last sending.

setRequireXMLDeclaraction
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setRequireXMLDeclaraction(boolean require)
   :outertype: SOAPSender

   Set if the request requires XML declaration at the top of the request.  This is equivalent to:

   .. parsed-literal::

      SOAPRequest.setProperty(WRITE_XML_DECLARATION, "true");

   :param require: true if requires XML declaration.

   **See also:** :java:ref:`javax.xml.soap.SOAPMessage.setProperty(String,Object)`, :java:ref:`javax.xml.soap.SOAPMessage.WRITE_XML_DECLARATION`

setServiceEndPoint
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setServiceEndPoint(URL endpoint)
   :outertype: SOAPSender

   Set the service endpoint.

   :param endpoint: The URL of the web service endpoint.

setServiceEndPoint
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setServiceEndPoint(String endpoint)
   :outertype: SOAPSender

   Set the service endpoint.

   :param endpoint: The String of the web service endpoint.

setUserObject
^^^^^^^^^^^^^

.. java:method:: public void setUserObject(Object obj)
   :outertype: SOAPSender

   Set a user object for callback.

   :param obj: The user object.

transformResponseContent
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public PropertyTree transformResponseContent() throws UtilitiesException, SOAPException
   :outertype: SOAPSender

   Transform the response into a property tree. It should only be called inside \ :java:ref:`onResponse()`\ .

   :return: An XML Property tree having the same tag content in the response.

