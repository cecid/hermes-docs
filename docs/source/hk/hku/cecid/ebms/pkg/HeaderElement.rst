.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

HeaderElement
=============

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type::  class HeaderElement extends ExtensionElementImpl

   An \ ``ExtensionElement``\  in the SOAP Header of a \ ``HeaderContainer``\

   :author: cyng

Fields
------
ACTOR_NEXT_MSH_SCHEMAS
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ACTOR_NEXT_MSH_SCHEMAS
   :outertype: HeaderElement

ACTOR_NEXT_MSH_URN
^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ACTOR_NEXT_MSH_URN
   :outertype: HeaderElement

ACTOR_TO_PARTY_MSH_URN
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ACTOR_TO_PARTY_MSH_URN
   :outertype: HeaderElement

ATTRIBUTE_ACTOR
^^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_ACTOR
   :outertype: HeaderElement

ATTRIBUTE_MUST_UNDERSTAND
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_MUST_UNDERSTAND
   :outertype: HeaderElement

MUST_UNDERSTAND
^^^^^^^^^^^^^^^

.. java:field:: static final boolean MUST_UNDERSTAND
   :outertype: HeaderElement

Constructors
------------
HeaderElement
^^^^^^^^^^^^^

.. java:constructor::  HeaderElement(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: HeaderElement

HeaderElement
^^^^^^^^^^^^^

.. java:constructor::  HeaderElement(SOAPEnvelope soapEnvelope, String localName) throws SOAPException
   :outertype: HeaderElement

HeaderElement
^^^^^^^^^^^^^

.. java:constructor::  HeaderElement(SOAPEnvelope soapEnvelope, String localName, String prefix, String uri) throws SOAPException
   :outertype: HeaderElement

Methods
-------
getActor
^^^^^^^^

.. java:method:: public String getActor()
   :outertype: HeaderElement

setActor
^^^^^^^^

.. java:method::  void setActor(String actor) throws SOAPException
   :outertype: HeaderElement

