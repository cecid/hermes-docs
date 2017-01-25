.. java:import:: java.util ArrayList

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPHeaderElement

ExtensionElementImpl
====================

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type::  class ExtensionElementImpl implements ExtensionElement

   An implementation of \ ``ExtensionElement``\ .

   :author: cyng

Fields
------
soapEnvelope
^^^^^^^^^^^^

.. java:field:: protected final SOAPEnvelope soapEnvelope
   :outertype: ExtensionElementImpl

   The \ ``javax.xml.soap.SOAPEnvelope``\  encapsulating this \ ``ExtensionElement``\

Constructors
------------
ExtensionElementImpl
^^^^^^^^^^^^^^^^^^^^

.. java:constructor::  ExtensionElementImpl(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: ExtensionElementImpl

   Construct an \ ``ExtensionElement``\  using the given \ ``SOAPEnvelope``\  and \ ``SOAPElement``\

ExtensionElementImpl
^^^^^^^^^^^^^^^^^^^^

.. java:constructor::  ExtensionElementImpl(SOAPEnvelope soapEnvelope, String localName, boolean isHeaderElement) throws SOAPException
   :outertype: ExtensionElementImpl

   Construct an \ ``ExtensionElement``\  using the given \ ``SOAPEnvelope``\  and whose namespace and URI are equal to that of SOAP extension element as defined in ebXML Messaging Service Specification

ExtensionElementImpl
^^^^^^^^^^^^^^^^^^^^

.. java:constructor::  ExtensionElementImpl(SOAPEnvelope soapEnvelope, String localName, String prefix, String uri, boolean isHeaderElement, boolean createSOAPElement) throws SOAPException
   :outertype: ExtensionElementImpl

   Construct an \ ``ExtensionElement``\  using the given \ ``SOAPEnvelope``\  and the specified namespace and URI. Change the default namespace and URI of this \ ``ExtensionElement``\  to the new one so that subsequent added children elements will inherit the new namespace and URI.

Methods
-------
addAttribute
^^^^^^^^^^^^

.. java:method:: public ExtensionElement addAttribute(String localName, String value) throws SOAPException
   :outertype: ExtensionElementImpl

   Add an attribute whose namespace is the same as this \ ``ExtensionElement``\

addAttribute
^^^^^^^^^^^^

.. java:method:: public ExtensionElement addAttribute(String localName, String prefix, String uri, String value) throws SOAPException
   :outertype: ExtensionElementImpl

   Add a namespace qualified attribute

addAttribute
^^^^^^^^^^^^

.. java:method:: public Element addAttribute(Name name, String value) throws SOAPException
   :outertype: ExtensionElementImpl

   Add an attribute of the given \ ``name``\  and \ ``value``\  to this \ ``Element``\ . If the namespace is found to be non-null, non-empty and different from the current \ ``Element``\ , the namespace is declared.

addChildElement
^^^^^^^^^^^^^^^

.. java:method:: public ExtensionElement addChildElement(String localName) throws SOAPException
   :outertype: ExtensionElementImpl

   Add a child element without text node value and whose namespace is the same as this \ ``ExtensionElement``\ , i.e., the parent

addChildElement
^^^^^^^^^^^^^^^

.. java:method:: public ExtensionElement addChildElement(String localName, String value) throws SOAPException
   :outertype: ExtensionElementImpl

   Add a child element with the specified value and whose namespace is the same as this \ ``ExtensionElement``\ , i.e., the parent

addChildElement
^^^^^^^^^^^^^^^

.. java:method:: public ExtensionElement addChildElement(String localName, String prefix, String uri) throws SOAPException
   :outertype: ExtensionElementImpl

   Add a child element without text node value and with the specified namespace

addChildElement
^^^^^^^^^^^^^^^

.. java:method:: public ExtensionElement addChildElement(String localName, String prefix, String uri, String value) throws SOAPException
   :outertype: ExtensionElementImpl

   Add a child element with the specified value and namespace. Change the default namespace and URI of this \ ``ExtensionElement``\  to the new one so that subsequent added children elements will inherit the new namespace and URI.

addChildElement
^^^^^^^^^^^^^^^

.. java:method:: public Element addChildElement(Element child) throws SOAPException
   :outertype: ExtensionElementImpl

   Add a child element to this \ ``Element``\

getAllAttributes
^^^^^^^^^^^^^^^^

.. java:method:: public Iterator getAllAttributes()
   :outertype: ExtensionElementImpl

   Get all attributes of this \ ``Element``\ . Each \ ``Iterator``\  entry is in the form of \ ``Map.Entry``\  representing a (\ ``javax.xml.soap.Name``\  name, \ ``String``\  value) pair.

getAttributeValue
^^^^^^^^^^^^^^^^^

.. java:method:: public String getAttributeValue(String localName) throws SOAPException
   :outertype: ExtensionElementImpl

   Get an attribute whose namespace is the same as this \ ``ExtensionElement``\

getAttributeValue
^^^^^^^^^^^^^^^^^

.. java:method:: public String getAttributeValue(String localName, String prefix, String uri) throws SOAPException
   :outertype: ExtensionElementImpl

   Get an attribute with the specified prefix and namespace

getAttributeValue
^^^^^^^^^^^^^^^^^

.. java:method:: public String getAttributeValue(Name name)
   :outertype: ExtensionElementImpl

   Get the attribute value of the specified attribute name

getChildElements
^^^^^^^^^^^^^^^^

.. java:method:: public Iterator getChildElements(String localName) throws SOAPException
   :outertype: ExtensionElementImpl

   Get all descendant child elements of the specified \ ``localName``\  whose namespace is the same as this \ ``ExtensionElement``\ , in the order in which they are encountered in a preorder traversal of this \ ``ExtensionElement``\  tree. Each \ ``Iterator``\  entry is in the form of an \ ``javax.xml.soap.SOAPElement``\ .

getChildElements
^^^^^^^^^^^^^^^^

.. java:method:: public Iterator getChildElements(Name name)
   :outertype: ExtensionElementImpl

   Get all descendant child elements of the specified \ ``javax.xml.soap.Name``\ , in the order in which they are encountered in a preorder traversal of this \ ``Element``\  tree. Each \ ``Iterator``\  entry is in the form of an \ ``javax.xml.soap.SOAPElement``\ .

getChildElements
^^^^^^^^^^^^^^^^

.. java:method:: public Iterator getChildElements()
   :outertype: ExtensionElementImpl

   Get all immediate child elements in the form of an \ ``javax.xml.soap.SOAPElement``\  in each \ ``Iterator``\  entry

getElementName
^^^^^^^^^^^^^^

.. java:method:: public Name getElementName()
   :outertype: ExtensionElementImpl

   Get the element name of this \ ``Element``\

getSOAPElement
^^^^^^^^^^^^^^

.. java:method:: public SOAPElement getSOAPElement() throws SOAPException
   :outertype: ExtensionElementImpl

   Return the \ ``javax.xml.soap.SOAPElement``\  representation of this \ ``Element``\

getValue
^^^^^^^^

.. java:method:: public String getValue()
   :outertype: ExtensionElementImpl

   Get the text node value of this \ ``Element``\ . Returns \ ``null``\  if it does not exist.

