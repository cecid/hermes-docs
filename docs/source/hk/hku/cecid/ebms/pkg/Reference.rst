.. java:import:: hk.hku.cecid.ebms.pkg.validation SOAPValidationException

.. java:import:: java.util ArrayList

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

Reference
=========

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class Reference extends ExtensionElementImpl

   A \ ``Reference``\  inside a \ ``Manifest``\

   :author: cyng

Fields
------
ATTRIBUTE_HREF
^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_HREF
   :outertype: Reference

   Name of the required href attribute in \ ``Reference``\  specifying the URI of the payload.

ATTRIBUTE_LOCATION
^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_LOCATION
   :outertype: Reference

   Name of the required Location attribute of the \ ``Schema``\  element.

ATTRIBUTE_ROLE
^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_ROLE
   :outertype: Reference

   Name of the optional role attribute in \ ``Reference``\  specifying the URI of the payload.

ATTRIBUTE_TYPE
^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_TYPE
   :outertype: Reference

   Name of the type attribute in \ ``Reference``\  specifying the type of XLINK link.

ELEMENT_SCHEMA
^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_SCHEMA
   :outertype: Reference

   Name of the Schema element

HREF_PREFIX
^^^^^^^^^^^

.. java:field:: public static final String HREF_PREFIX
   :outertype: Reference

   The prefix of "href" attribute of this \ ``Reference``\ .

REFERENCE
^^^^^^^^^

.. java:field:: static final String REFERENCE
   :outertype: Reference

   \ ``Reference``\  element name

Constructors
------------
Reference
^^^^^^^^^

.. java:constructor::  Reference(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: Reference

   Parse the given \ ``SOAPElement``\  to reconstruct a \ ``Reference``\  object with \ ``SOAPEnvelope``\  as the parent.

   :param soapEnvelope: \ ``SOAPEnvelope``\  object into which the \ ``Reference``\  object is added.
   :param soapElement: \ ``SOAPElement``\  object to be parsed to reconstruct the \ ``Reference``\  object.
   :throws SOAPException:

Methods
-------
addDescription
^^^^^^^^^^^^^^

.. java:method:: public void addDescription(String description) throws SOAPException
   :outertype: Reference

   Add  element with default \ ``xml:lang``\

   :param description: Description to be added to the \ ``Reference``\ .
   :throws SOAPException:

addDescription
^^^^^^^^^^^^^^

.. java:method:: public void addDescription(String description, String lang) throws SOAPException
   :outertype: Reference

   Add  element with specified \ ``xml:lang``\

   :param description: Description to be added to the \ ``Reference``\ .
   :param lang: Language of the description specified in \ ` RFC 1766 <http://www.ietf.org/rfc/rfc1766.txt>`_\  and ISO639.
   :throws SOAPException:

addSchema
^^^^^^^^^

.. java:method:: public void addSchema(String location, String version) throws SOAPException
   :outertype: Reference

   Create a \ ``Schema``\  object using the given location and version, and add it to the \ ``Reference``\  object.

   :param location: URI of the schema.
   :param version: Version identifier of the schema.
   :throws SOAPException:

getDescriptionCount
^^^^^^^^^^^^^^^^^^^

.. java:method:: public int getDescriptionCount()
   :outertype: Reference

   Gets the number of \ ``Description``\  elements in this \ ``Reference``\ .

   :return: The number of \ ``Description``\  elements.

getDescriptions
^^^^^^^^^^^^^^^

.. java:method:: public Iterator getDescriptions()
   :outertype: Reference

   Get the descriptions in the \ ``Reference``\  element.

   :return: An iterator pointing to a list of descriptions of type \ ``Description``\ .

getHref
^^^^^^^

.. java:method:: public String getHref()
   :outertype: Reference

   Get href attribute of the \ ``Reference``\  element.

   :return: Href attribute.

getId
^^^^^

.. java:method:: public String getId()
   :outertype: Reference

   Get ID attribute of the \ ``Reference``\  element.

   :return: ID attribute.

getRole
^^^^^^^

.. java:method:: public String getRole()
   :outertype: Reference

getSchemas
^^^^^^^^^^

.. java:method:: public Iterator getSchemas()
   :outertype: Reference

   Get the schemas in the \ ``Reference``\  element.

   :return: An iterator pointing to a list of schemas of type \ ``Schema``\ .

setHref
^^^^^^^

.. java:method::  void setHref(String href) throws SOAPException
   :outertype: Reference

setId
^^^^^

.. java:method::  void setId(String id) throws SOAPException
   :outertype: Reference

setRole
^^^^^^^

.. java:method:: public void setRole(String role) throws SOAPException
   :outertype: Reference

