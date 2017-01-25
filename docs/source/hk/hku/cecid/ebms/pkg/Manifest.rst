.. java:import:: java.util ArrayList

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

Manifest
========

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class Manifest extends BodyElement

   An ebXML \ ``Manifest``\  in the SOAP Body of a \ ``HeaderContainer``\

   :author: cyng

Fields
------
MANIFEST
^^^^^^^^

.. java:field:: static final String MANIFEST
   :outertype: Manifest

   \ ``Manifest``\  element name

Constructors
------------
Manifest
^^^^^^^^

.. java:constructor::  Manifest(SOAPEnvelope soapEnvelope) throws SOAPException
   :outertype: Manifest

   Constructs a \ ``Manifest``\

Manifest
^^^^^^^^

.. java:constructor::  Manifest(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: Manifest

Methods
-------
addReference
^^^^^^^^^^^^

.. java:method:: public Reference addReference(String id, String href) throws SOAPException
   :outertype: Manifest

getReferences
^^^^^^^^^^^^^

.. java:method:: public Iterator getReferences()
   :outertype: Manifest

