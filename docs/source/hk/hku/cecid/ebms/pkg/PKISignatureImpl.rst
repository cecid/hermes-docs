.. java:import:: hk.hku.cecid.ebms.pkg.pki ApacheXMLDSigner

.. java:import:: hk.hku.cecid.ebms.pkg.pki CertResolver

.. java:import:: hk.hku.cecid.ebms.pkg.pki CompositeKeyStore

.. java:import:: hk.hku.cecid.ebms.pkg.pki ErrorMessages

.. java:import:: hk.hku.cecid.ebms.pkg.pki SignException

.. java:import:: hk.hku.cecid.ebms.pkg.pki VerifyException

.. java:import:: hk.hku.cecid.ebms.pkg.validation SOAPValidationException

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io FileInputStream

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: java.security PrivateKey

.. java:import:: java.security PublicKey

.. java:import:: java.security.cert X509Certificate

.. java:import:: java.util Iterator

.. java:import:: javax.activation DataSource

.. java:import:: javax.xml.parsers DocumentBuilderFactory

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPPart

.. java:import:: javax.xml.transform TransformerFactory

.. java:import:: org.apache.log4j Logger

.. java:import:: org.dom4j.io DocumentResult

.. java:import:: org.dom4j.io XMLWriter

.. java:import:: org.w3c.dom Attr

.. java:import:: org.w3c.dom Document

.. java:import:: org.w3c.dom Element

.. java:import:: org.w3c.dom NamedNodeMap

.. java:import:: org.w3c.dom NodeList

PKISignatureImpl
================

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type::  class PKISignatureImpl extends Signature

   An implementation of ebXML \ ``Signature``\ , making use of Phoenix's PKI library.

   :author: kcyee

Fields
------
logger
^^^^^^

.. java:field:: static Logger logger
   :outertype: PKISignatureImpl

Constructors
------------
PKISignatureImpl
^^^^^^^^^^^^^^^^

.. java:constructor::  PKISignatureImpl(EbxmlMessage ebxmlMessage) throws SOAPException
   :outertype: PKISignatureImpl

PKISignatureImpl
^^^^^^^^^^^^^^^^

.. java:constructor::  PKISignatureImpl(EbxmlMessage ebxmlMessage, SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: PKISignatureImpl

Methods
-------
addReference
^^^^^^^^^^^^

.. java:method::  void addReference(String uri)
   :outertype: PKISignatureImpl

sign
^^^^

.. java:method::  void sign(String alias, char[] password, String keyStoreLocation) throws SignatureException
   :outertype: PKISignatureImpl

sign
^^^^

.. java:method::  void sign(String alias, char[] password, String keyStoreLocation, String algo) throws SignatureException
   :outertype: PKISignatureImpl

sign
^^^^

.. java:method::  void sign(String alias, char[] password, String keyStoreLocation, String algo, String digestAlgo, boolean signEnvelopeOnly) throws SignatureException
   :outertype: PKISignatureImpl

sign
^^^^

.. java:method::  void sign(String alias, char[] password) throws SignatureException
   :outertype: PKISignatureImpl

sign
^^^^

.. java:method::  void sign(String alias, char[] password, String keyStoreLocation, String type, String provider) throws SignatureException
   :outertype: PKISignatureImpl

sign
^^^^

.. java:method::  void sign(PrivateKey privateKey, X509Certificate[] certificates) throws SignatureException
   :outertype: PKISignatureImpl

verify
^^^^^^

.. java:method::  boolean verify(char[] password, String keyStoreLocation, CertResolver certResolver, DataSource dataSource) throws SignatureException
   :outertype: PKISignatureImpl

verify
^^^^^^

.. java:method::  boolean verify(Element documentElement, PublicKey key) throws SignatureException
   :outertype: PKISignatureImpl

verify
^^^^^^

.. java:method::  boolean verify(PublicKey key) throws SignatureException
   :outertype: PKISignatureImpl

