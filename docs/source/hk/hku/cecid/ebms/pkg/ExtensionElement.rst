.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap SOAPException

ExtensionElement
================

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type::  interface ExtensionElement extends Element

   An \ ``ExtensionElement``\  in the \ ``HeaderContainer``\

   :author: cyng

Fields
------
ATTRIBUTE_ID
^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_ID
   :outertype: ExtensionElement

   Name of the ID attribute.

ATTRIBUTE_LANG
^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_LANG
   :outertype: ExtensionElement

   Name of the language attribute.

ATTRIBUTE_SCHEMA_LOCATION
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_SCHEMA_LOCATION
   :outertype: ExtensionElement

   Name of the Schema location attribute

ATTRIBUTE_VERSION
^^^^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_VERSION
   :outertype: ExtensionElement

   Name of the version attribute.

LANG_TYPE
^^^^^^^^^

.. java:field:: static final String LANG_TYPE
   :outertype: ExtensionElement

   Default language type of the MSH.

NAMESPACE_PREFIX_EB
^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_PREFIX_EB
   :outertype: ExtensionElement

   Namespace prefix of \ ``ExtensionElement``\ .

NAMESPACE_PREFIX_SOAP_ENVELOPE
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_PREFIX_SOAP_ENVELOPE
   :outertype: ExtensionElement

   Namespace prefix of SOAP envelope.

NAMESPACE_PREFIX_XLINK
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_PREFIX_XLINK
   :outertype: ExtensionElement

   Namespace prefix of XLINK.

NAMESPACE_PREFIX_XML
^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_PREFIX_XML
   :outertype: ExtensionElement

   Namespace prefix of XML.

NAMESPACE_PREFIX_XSI
^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_PREFIX_XSI
   :outertype: ExtensionElement

   Namespace prefix of XML Schema Instance

NAMESPACE_URI_EB
^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_URI_EB
   :outertype: ExtensionElement

   Namespace URI of \ ``ExtensionElement``\ .

NAMESPACE_URI_SOAP_ENVELOPE
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_URI_SOAP_ENVELOPE
   :outertype: ExtensionElement

   Namespace URI of SOAP envelope.

NAMESPACE_URI_XLINK
^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_URI_XLINK
   :outertype: ExtensionElement

   Namespace URI of XLINK.

NAMESPACE_URI_XML
^^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_URI_XML
   :outertype: ExtensionElement

   Namespace URI of XML.

NAMESPACE_URI_XSI
^^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_URI_XSI
   :outertype: ExtensionElement

   Namespace URI of XML Schema Instance

SCHEMA_LOCATION_SOAP_BODY
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String SCHEMA_LOCATION_SOAP_BODY
   :outertype: ExtensionElement

   URI of SOAP SOAP body schema location

SCHEMA_LOCATION_SOAP_ENVELOPE
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String SCHEMA_LOCATION_SOAP_ENVELOPE
   :outertype: ExtensionElement

   URI of SOAP envelope schema location

SCHEMA_LOCATION_SOAP_HEADER
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String SCHEMA_LOCATION_SOAP_HEADER
   :outertype: ExtensionElement

   URI of SOAP header schema location

VERSION
^^^^^^^

.. java:field:: static final String VERSION
   :outertype: ExtensionElement

   Version of ebXML Messaging Service.

XML_NS_DECL_PREFIX
^^^^^^^^^^^^^^^^^^

.. java:field:: static final String XML_NS_DECL_PREFIX
   :outertype: ExtensionElement

   Attribute prefix for XML namespace declarations.

XML_NS_SEPARATOR
^^^^^^^^^^^^^^^^

.. java:field:: static final char XML_NS_SEPARATOR
   :outertype: ExtensionElement

   Character that separates the namespace prefix and local name in an XML tag.

Methods
-------
addAttribute
^^^^^^^^^^^^

.. java:method::  ExtensionElement addAttribute(String localName, String value) throws SOAPException
   :outertype: ExtensionElement

   Add an attribute whose namespace is the same as this \ ``ExtensionElement``\ .

addAttribute
^^^^^^^^^^^^

.. java:method::  ExtensionElement addAttribute(String localName, String prefix, String uri, String value) throws SOAPException
   :outertype: ExtensionElement

   Add a namespace qualified attribute.

addChildElement
^^^^^^^^^^^^^^^

.. java:method::  ExtensionElement addChildElement(String localName) throws SOAPException
   :outertype: ExtensionElement

   Add a child element without text node value and whose namespace is the same as this \ ``ExtensionElement``\ , i.e., the parent.

addChildElement
^^^^^^^^^^^^^^^

.. java:method::  ExtensionElement addChildElement(String localName, String value) throws SOAPException
   :outertype: ExtensionElement

   Add a child element with the specified value and whose namespace is the same as this \ ``ExtensionElement``\ , i.e., the parent.

addChildElement
^^^^^^^^^^^^^^^

.. java:method::  ExtensionElement addChildElement(String localName, String prefix, String uri) throws SOAPException
   :outertype: ExtensionElement

   Add a child element without text node value and with the specified namespace.

addChildElement
^^^^^^^^^^^^^^^

.. java:method::  ExtensionElement addChildElement(String localName, String prefix, String uri, String value) throws SOAPException
   :outertype: ExtensionElement

   Add a child element with the specified value and namespace.

getAttributeValue
^^^^^^^^^^^^^^^^^

.. java:method::  String getAttributeValue(String localName) throws SOAPException
   :outertype: ExtensionElement

   Get an attribute whose namespace is the same as this \ ``ExtensionElement``\ .

getAttributeValue
^^^^^^^^^^^^^^^^^

.. java:method::  String getAttributeValue(String localName, String prefix, String uri) throws SOAPException
   :outertype: ExtensionElement

   Get an attribute with the specified prefix and namespace

getChildElements
^^^^^^^^^^^^^^^^

.. java:method::  Iterator getChildElements(String localName) throws SOAPException
   :outertype: ExtensionElement

   Get all descendant child elements of the specified \ ``localName``\  whose namespace is the same as this \ ``ExtensionElement``\ , in the order in which they are encountered in a preorder traversal of this \ ``ExtensionElement``\  tree. Each \ ``Iterator``\  entry is in the form of an \ ``javax.xml.soap.SOAPElement``\ .

