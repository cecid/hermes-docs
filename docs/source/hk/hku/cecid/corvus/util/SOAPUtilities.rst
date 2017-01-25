.. java:import:: java.util Hashtable

.. java:import:: java.util Enumeration

.. java:import:: java.util List

.. java:import:: java.util Vector

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPBody

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPFactory

.. java:import:: javax.xml.soap SOAPMessage

.. java:import:: org.w3c.dom NodeList

.. java:import:: org.w3c.dom Node

SOAPUtilities
=============

.. java:package:: hk.hku.cecid.corvus.util
   :noindex:

.. java:type:: public class SOAPUtilities

   The SOAPUtilities acts as a SOAP Helper for some operations that frequently used.  Currently supported operations:

   ..

   * create a SOAP Element with specified tag name, value, ns prefix and uri (Also an attributes set).
   * get a SOAP Element with specified tag name, ns prefix and uri and which nth tag from a SOAP Message.
   * get a list of SOAP Element with specified tag name, ns prefix and uri from a SOAP Message.

   :author: Twinsen

Methods
-------
countElement
^^^^^^^^^^^^

.. java:method:: public static int countElement(SOAPMessage message, String tagname, String nsURI) throws SOAPException
   :outertype: SOAPUtilities

   Count how many element with \ ``tagname``\  and \ ``nsURI``\  is in SOAPMessage \ ``message``\ .

   :param message: The SOAP message
   :param tagname: The name of the tag to be counted.
   :param nsURI: The namespace URI of the tag.
   :throws SOAPException:
   :return: The number of element in the SOAP message.

createElement
^^^^^^^^^^^^^

.. java:method:: public static SOAPElement createElement(String tagName, String tagValue, String nsPrefix, String nsURI) throws SOAPException
   :outertype: SOAPUtilities

   Create a SOAP Element with the specified parameters.

   :param tagName: the name of XML tag.
   :param tagValue: the value of XML tag.
   :param nsPrefix: the namespace prefix.
   :param nsURI: the namespace URL.
   :return: the new SOAP element created.

createElement
^^^^^^^^^^^^^

.. java:method:: public static SOAPElement createElement(String tagName, String tagValue, String nsPrefix, String nsURI, Hashtable attrSet) throws SOAPException
   :outertype: SOAPUtilities

   Create a SOAP Element with the specified parameters.

   Also it create the attributes set as the parameter properties.

   :param tagName: the name of XML tag.
   :param tagValue: the value of XML tag.
   :param nsPrefix: the namespace prefix.
   :param nsURI: the namespace URL.
   :param attrSet: the attributes set in the element.
   :return: the new SOAP element created.

getElement
^^^^^^^^^^

.. java:method:: public static SOAPElement getElement(SOAPMessage message, String tagname, String nsURI, int whichOne) throws SOAPException
   :outertype: SOAPUtilities

   Get a SOAP Element from the SOAPMessage (SOAPbody inside).

   :param message: The SOAP message to be searched with.
   :param tagname: The tag name of element to be retrieved.
   :param nsURI: The namespace URI.
   :param whichOne: The nth child element to be returned.
   :return: The element in the tagname specified.

getElementList
^^^^^^^^^^^^^^

.. java:method:: public static List getElementList(SOAPMessage message, String tagname, String nsURI) throws SOAPException
   :outertype: SOAPUtilities

   Get a SOAP Element list from the SOAPMessage (SOAPbody inside).

   :param message: The SOAP message to be searched with.
   :param tagname: The tag name of element to be retrieved.
   :param nsURI: The namespace URI.
   :throws SOAPException:
   :return: list of SOAP element

linkElements
^^^^^^^^^^^^

.. java:method:: public static boolean linkElements(SOAPMessage message, String parentTagName, String parentNsURI, String childTagName, String childNsURI) throws SOAPException
   :outertype: SOAPUtilities

   Validate the existence of child SOAP element given the parent element.

   :param message:
   :param parentTagName:
   :param parentNsURI:
   :param childTagName:
   :param childNsURI:
   :throws SOAPException:
   :return: true if child element exists

