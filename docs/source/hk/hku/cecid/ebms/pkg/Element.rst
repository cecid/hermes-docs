.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPException

Element
=======

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type::  interface Element

   Encapsulation of a \ ``javax.xml.soap.SOAPElement``\

   :author: cyng

Methods
-------
addAttribute
^^^^^^^^^^^^

.. java:method::  Element addAttribute(Name name, String value) throws SOAPException
   :outertype: Element

   Add an attribute of the given \ ``name``\  and \ ``value``\  to this \ ``Element``\

   :param name: the attribute name in \ ``javax.xml.soap.Name``\  representation
   :param value: the attribute value
   :return: this \ ``Element``\  to which the attribute is added

addChildElement
^^^^^^^^^^^^^^^

.. java:method::  Element addChildElement(Element child) throws SOAPException
   :outertype: Element

   Add a child element to this \ ``Element``\

   :param child: the child \ ``Element``\
   :return: the newly added child \ ``Element``\

getAllAttributes
^^^^^^^^^^^^^^^^

.. java:method::  Iterator getAllAttributes()
   :outertype: Element

   Get all attributes of this \ ``Element``\ . Each \ ``Iterator``\  entry is in the form of \ ``Map.Entry``\  representing a (\ ``javax.xml.soap.Name``\  name, \ ``String``\  value) pair.

getAttributeValue
^^^^^^^^^^^^^^^^^

.. java:method::  String getAttributeValue(Name name)
   :outertype: Element

   Get the attribute value of the specified attribute name

getChildElements
^^^^^^^^^^^^^^^^

.. java:method::  Iterator getChildElements(Name name)
   :outertype: Element

   Get all descendant child elements of the specified \ ``javax.xml.soap.Name``\ , in the order in which they are encountered in a preorder traversal of this \ ``Element``\  tree. Each \ ``Iterator``\  entry is in the form of an \ ``javax.xml.soap.SOAPElement``\ .

getChildElements
^^^^^^^^^^^^^^^^

.. java:method::  Iterator getChildElements()
   :outertype: Element

   Get all immediate child elements in the form of an \ ``javax.xml.soap.SOAPElement``\  in each \ ``Iterator``\  entry

getElementName
^^^^^^^^^^^^^^

.. java:method::  Name getElementName()
   :outertype: Element

   Get the element name of this \ ``Element``\

getSOAPElement
^^^^^^^^^^^^^^

.. java:method::  SOAPElement getSOAPElement() throws SOAPException
   :outertype: Element

   Return the \ ``javax.xml.soap.SOAPElement``\  representation of this \ ``Element``\

getValue
^^^^^^^^

.. java:method::  String getValue()
   :outertype: Element

   Get the text node value of this \ ``Element``\ . Returns \ ``null``\  if it does not exist.

