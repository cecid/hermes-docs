.. java:import:: hk.hku.cecid.ebms.pkg.pki CertResolver

.. java:import:: hk.hku.cecid.ebms.pkg.validation SOAPValidationException

.. java:import:: java.util ArrayList

.. java:import:: java.util Iterator

.. java:import:: javax.activation DataSource

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

Signature
=========

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public abstract class Signature extends HeaderElement

   An ebXML \ ``Signature``\  is a \ ``HeaderElement``\  in \ ``HeaderContainer``\  [ebMSS 4.1.1 and 4.1.3].

   This class is a partial implementation of the XML-Signature Syntax and Processing / RFC 3275. Please refer to these documents for details.

   :author: cyng

   **See also:** \ ` XML-Signature Syntax and Processing <http://www.w3.org/TR/xmldsig-core/>`_\

Fields
------
ATTRIBUTE_ALGORITHM
^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ATTRIBUTE_ALGORITHM
   :outertype: Signature

   Name of the Algorithm attribute.

ATTRIBUTE_ID
^^^^^^^^^^^^

.. java:field:: public static final String ATTRIBUTE_ID
   :outertype: Signature

   Name of the Id attribute.

ATTRIBUTE_URI
^^^^^^^^^^^^^

.. java:field:: public static final String ATTRIBUTE_URI
   :outertype: Signature

   Name of the URI attribute.

CANONICALIZATION_METHOD
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String CANONICALIZATION_METHOD
   :outertype: Signature

   Namespace URI of the canonicalization method as specified in \ `Exclusive XML Canonicalization Version 1.0 <http://www.w3.org/TR/xml-exc-c14n/>`_\ .

CHARACTER_ENCODING
^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String CHARACTER_ENCODING
   :outertype: Signature

   Default character coding.

DIGEST_ALGORITHM
^^^^^^^^^^^^^^^^

.. java:field:: public static final String DIGEST_ALGORITHM
   :outertype: Signature

   Name of the message digest algorithm.

DIGEST_METHOD
^^^^^^^^^^^^^

.. java:field:: public static final String DIGEST_METHOD
   :outertype: Signature

   Name of the Digest method required, qualified by namespace [XMLDSIG 6.1].

ELEMENT_CANONICALIZATION_METHOD
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_CANONICALIZATION_METHOD
   :outertype: Signature

   Name of the Canonicalization Method element [ebMSS 4.1.3, XMLDSIG 4.3.1] used in signature generation.

ELEMENT_DIGEST_METHOD
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_DIGEST_METHOD
   :outertype: Signature

   Name of the DigestMethod element which specifies the digest algorithm to be applied to the signed object [XMLDSIG 4.3.3.5].

ELEMENT_DIGEST_VALUE
^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_DIGEST_VALUE
   :outertype: Signature

   Name of the DigestValue element which contains the encoded value of the digest [XMLDSIG 4.3.3.6].

ELEMENT_KEY_INFO
^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_KEY_INFO
   :outertype: Signature

   Name of the KeyInfo element which enables the recipient(s) to obtain the key needed to validate the signature [XMLDSIG 4.4].

ELEMENT_OBJECT
^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_OBJECT
   :outertype: Signature

   Name of the Object element [XMLDSIG 4.5].

ELEMENT_REFERENCE
^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_REFERENCE
   :outertype: Signature

   Name of the Reference element which specifies a digest algorithm and digest value and other optional information [ebMSS 4.1.3, XMLDSIG 4.3.3].

ELEMENT_SIGNATURE
^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_SIGNATURE
   :outertype: Signature

   Name of the Signature element [ebMSS 4.1.1, XMLDSIG 4.1].

ELEMENT_SIGNATURE_METHOD
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_SIGNATURE_METHOD
   :outertype: Signature

   Name of the Signature Method element [ebMSS 4.1.3, XMLDSIG 4.3.2].

ELEMENT_SIGNATURE_VALUE
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_SIGNATURE_VALUE
   :outertype: Signature

   Name of the Signature Value element [ebMSS 4.1.3, XMLDSIG 4.2].

ELEMENT_SIGNED_INFO
^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_SIGNED_INFO
   :outertype: Signature

   Name of the SignedInfo element [ebMSS 4.1.3, XMLDSIG 4.3] containing information about the signature. They include:

   ..

   * Canonicalization method
   * Signature method
   * References made during signature generation

ELEMENT_TRANSFORM
^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_TRANSFORM
   :outertype: Signature

   Name of the Transform element which describes the transformation applied on the data object [XMLDSIG 4.3.3.4]. Transformation algorithms are described in XMLDSIG 6.6: Transform Algorithms.

ELEMENT_TRANSFORMS
^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_TRANSFORMS
   :outertype: Signature

   Name of the Transforms element which is an ordered list of transformations applied to obtain the data object to be signed [XMLDSIG 4.3.3.4].

ELEMENT_X509_CERTIFICATE
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_X509_CERTIFICATE
   :outertype: Signature

   Name of the X509Certificate element which contains a binary (ASN.1 DER) X.509 Certificate [XMLDSIG 4.4].

ELEMENT_X509_DATA
^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_X509_DATA
   :outertype: Signature

   Name of the X509Data element which contains identifier(s) of keys or X509 certificates [XMLDSIG 4.4.4].

ELEMENT_XPATH
^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_XPATH
   :outertype: Signature

   Name of the XPath element [XMLDSIG 6.6.3].

NAMESPACE_PREFIX_DS
^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String NAMESPACE_PREFIX_DS
   :outertype: Signature

   Namespace prefix of \ ``Signature``\ .

NAMESPACE_URI_DS
^^^^^^^^^^^^^^^^

.. java:field:: public static final String NAMESPACE_URI_DS
   :outertype: Signature

   Namespace URI of \ ``Signature``\ .

SIGNATURE_ALGORITHM
^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SIGNATURE_ALGORITHM
   :outertype: Signature

   Name of the digital signature algorithm.

SIGNATURE_METHOD
^^^^^^^^^^^^^^^^

.. java:field:: public static final String SIGNATURE_METHOD
   :outertype: Signature

   Name of the digital signature method required, qualified by the digital signature namespace [XMLDSIG 6.1].

TRANSFORM_ALGORITHM_ENVELOPED_SIGNATURE
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String TRANSFORM_ALGORITHM_ENVELOPED_SIGNATURE
   :outertype: Signature

   Name of the enveloped signature required, qualified by the digital signature namespace [XMLDSIG 6.1].

TRANSFORM_ALGORITHM_XPATH
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String TRANSFORM_ALGORITHM_XPATH
   :outertype: Signature

   Name of the XPath transform algorithm recommended [XMLDSIG 6.1].

TRANSFORM_XPATH
^^^^^^^^^^^^^^^

.. java:field:: public static final String TRANSFORM_XPATH
   :outertype: Signature

   XPath transform string used in the implementation.

references
^^^^^^^^^^

.. java:field:: final ArrayList references
   :outertype: Signature

signatureValue
^^^^^^^^^^^^^^

.. java:field::  String signatureValue
   :outertype: Signature

Constructors
------------
Signature
^^^^^^^^^

.. java:constructor::  Signature(SOAPEnvelope soapEnvelope, String localName, String prefix, String uri) throws SOAPException
   :outertype: Signature

   Initializes the \ ``Signature``\  object using the given \ ``SOAPEnvelope``\ , local name, namespace prefix and namespace URI.

   :param soapEnvelope: \ ``SOAPEnvelope``\  on which digital signature will be applied.
   :param localName: Local name of the signature element.
   :param prefix: Namespace prefix of the signature element.
   :param uri: Namespace URI of the signature element.
   :throws SOAPException:

Signature
^^^^^^^^^

.. java:constructor::  Signature(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: Signature

Methods
-------
addReference
^^^^^^^^^^^^

.. java:method:: abstract void addReference(String uri) throws SignatureException
   :outertype: Signature

   Add a reference URI to this \ ``Signature``\ .

   :param uri: Reference URI to be added.
   :throws SignatureException:

getReferences
^^^^^^^^^^^^^

.. java:method:: public Iterator getReferences()
   :outertype: Signature

getSignatureValue
^^^^^^^^^^^^^^^^^

.. java:method::  String getSignatureValue()
   :outertype: Signature

newInstance
^^^^^^^^^^^

.. java:method:: static Signature newInstance(EbxmlMessage ebxmlMessage) throws SOAPException
   :outertype: Signature

   Get a new instance of \ ``Signature``\  which will be used to sign or verify the given \ ``EbxmlMessage``\

newInstance
^^^^^^^^^^^

.. java:method:: static Signature newInstance(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: Signature

newInstance
^^^^^^^^^^^

.. java:method:: static Signature newInstance(EbxmlMessage ebxmlMessage, SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: Signature

sign
^^^^

.. java:method:: abstract void sign(String username, char[] password) throws SignatureException
   :outertype: Signature

   Sign the \ ``EbxmlMessage``\  with the username and
   password used to retrieve private key from the keystore.

   :param username: User name required to open the private key.
   :param password: Password required to open the private key.
   :throws SignatureException:

sign
^^^^

.. java:method:: abstract void sign(String username, char[] password, String keyStoreLocation, String algorithm) throws SignatureException
   :outertype: Signature

   Sign the \ ``EbxmlMessage``\  with the username and
   password used to retrieve private key from the keystore

   :param username: User name required to open the private key.
   :param password: Password required to open the private key.
   :param keyStoreLocation: File location of the keystore.
   :param algorithm: Name of the algorithm used to sign the message.
   :throws SignatureException:

sign
^^^^

.. java:method:: abstract void sign(String username, char[] password, String keyStoreLocation, String algorithm, String digestAlgo, boolean signEnvelopeOnly) throws SignatureException
   :outertype: Signature

   Sign the \ ``EbxmlMessage``\  with the username and
   password used to retrieve private key from the keystore

   :param username: User name required to open the private key.
   :param password: Password required to open the private key.
   :param keyStoreLocation: File location of the keystore.
   :param algorithm: Name of the algorithm used to sign the message.
   :param digestAlgo: Name of the algorithm used to make the digest.
   :param signEnvelopeOnly: whether sign the envelope only.,
   :throws SignatureException:

sign
^^^^

.. java:method:: abstract void sign(String username, char[] password, String keyStoreLocation) throws SignatureException
   :outertype: Signature

   Sign the \ ``EbxmlMessage``\  with the username and
   password used to retrieve private key from the keystore

   :param username: User name required to open the private key.
   :param password: Password required to open the private key.
   :param keyStoreLocation: File location of the keystore.
   :throws SignatureException:

sign
^^^^

.. java:method:: abstract void sign(String username, char[] password, String keyStoreLocation, String type, String provider) throws SignatureException
   :outertype: Signature

   Sign the \ ``EbxmlMessage``\  with the username and
   password used to retrieve private key from the keystore.

   :param username: User name required to open the private key.
   :param password: Password required to open the private key.
   :param keyStoreLocation: File location of the keystore
   :param type:
   :param provider:
   :throws SignatureException:

sign
^^^^

.. java:method:: abstract void sign(java.security.PrivateKey privateKey, java.security.cert.X509Certificate[] certificates) throws SignatureException
   :outertype: Signature

   Sign the \ ``EbxmlMessage``\  using the private key supplied and attach X.509 certificates to the signature.

   :param privateKey: Private key used to sign the message.
   :param certificates: List of certificates to be included in the signature.
   :throws SignatureException:

verify
^^^^^^

.. java:method:: abstract boolean verify(char[] password, String keyStoreLocation, CertResolver certResolver, DataSource datasource) throws SignatureException
   :outertype: Signature

   Verify the message using trusted keystore.

   :param password: Password to open the keystore.
   :param keyStoreLocation: File location of the key store.
   :param certResolver: Resolve a certificate chain in order to verify the message. If it is null, the certificate chain is extracted directly from the  element in the message.
   :throws SignatureException:
   :return: true if the digital signature is valid; false otherwise.

verify
^^^^^^

.. java:method:: abstract boolean verify(org.w3c.dom.Element documentElement, java.security.PublicKey publicKey) throws SignatureException
   :outertype: Signature

   Verify the XML signature of the \ ``EbxmlMessage``\

   :param documentElement: Document fragment which contains the digital signature.
   :param publicKey: Public key used to verify the digitall signature.
   :throws SignatureException:
   :return: true if digital signature is valid; false otherwise.

verify
^^^^^^

.. java:method:: abstract boolean verify(java.security.PublicKey publicKey) throws SignatureException
   :outertype: Signature

   Verify the XML signature of the \ ``EbxmlMessage``\

   :param publicKey: Public key used to verify the digitall signature.
   :throws SignatureException:
   :return: true if digital signature is valid; false otherwise.

