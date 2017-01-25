.. java:import:: hk.hku.cecid.ebms.pkg.validation SOAPValidationException

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

SignatureReference
==================

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class SignatureReference extends HeaderElement

   element in .

   :author: cyng

Fields
------
ATTRIBUTE_URI
^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_URI
   :outertype: SignatureReference

   URI attribute name

ELEMENT_DIGEST_VALUE
^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_DIGEST_VALUE
   :outertype: SignatureReference

   element name

SIGNATURE_REFERENCE
^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String SIGNATURE_REFERENCE
   :outertype: SignatureReference

   element name

Constructors
------------
SignatureReference
^^^^^^^^^^^^^^^^^^

.. java:constructor::  SignatureReference(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: SignatureReference

Methods
-------
getDigestValue
^^^^^^^^^^^^^^

.. java:method:: public String getDigestValue()
   :outertype: SignatureReference

   Gets  element of this .

   :return: element of this .

getUri
^^^^^^

.. java:method:: public String getUri()
   :outertype: SignatureReference

   Gets URI attribute of this .

   :return: URI attribute of this .

