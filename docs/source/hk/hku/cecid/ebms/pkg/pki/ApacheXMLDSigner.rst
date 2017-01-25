.. java:import:: java.io InputStream

.. java:import:: java.security KeyStoreException

.. java:import:: java.security PrivateKey

.. java:import:: java.security PublicKey

.. java:import:: java.security.cert Certificate

.. java:import:: java.security.cert X509Certificate

.. java:import:: java.util ArrayList

.. java:import:: org.apache.log4j Logger

.. java:import:: org.apache.xml.security.exceptions XMLSecurityException

.. java:import:: org.apache.xml.security.keys KeyInfo

.. java:import:: org.apache.xml.security.keys.keyresolver KeyResolverException

.. java:import:: org.apache.xml.security.signature XMLSignature

.. java:import:: org.apache.xml.security.signature XMLSignatureException

.. java:import:: org.apache.xml.security.transforms TransformationException

.. java:import:: org.apache.xml.security.transforms Transforms

.. java:import:: org.apache.xml.security.utils Constants

.. java:import:: org.w3c.dom Document

.. java:import:: org.w3c.dom Element

.. java:import:: org.w3c.dom NodeList

ApacheXMLDSigner
================

.. java:package:: hk.hku.cecid.ebms.pkg.pki
   :noindex:

.. java:type:: public class ApacheXMLDSigner implements XMLDSigner

   This class hides the details for digital signature. The digital signature routines are provided by the Apache XML Security library. We defined a standard way to have the document signed as interface. Different classes will implement the interface using different library behind.

   :author: kcyee

Fields
------
ACTOR_NEXT_MSH_SCHEMAS
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ACTOR_NEXT_MSH_SCHEMAS
   :outertype: ApacheXMLDSigner

ACTOR_NEXT_MSH_URN
^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ACTOR_NEXT_MSH_URN
   :outertype: ApacheXMLDSigner

DIGEST_METHOD
^^^^^^^^^^^^^

.. java:field:: public static final String DIGEST_METHOD
   :outertype: ApacheXMLDSigner

   Name of the Digest method required, qualified by namespace [XMLDSIG 6.1]

ELEMENT_KEY_INFO
^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_KEY_INFO
   :outertype: ApacheXMLDSigner

   Name of the KeyInfo element which enables the recipient(s) to obtain the key needed to validate the signature [XMLDSIG 4.4]

ELEMENT_SIGNATURE
^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_SIGNATURE
   :outertype: ApacheXMLDSigner

   Name of the Signature element [ebMSS 4.1.1, XMLDSIG 4.1]

ELEMENT_XPATH
^^^^^^^^^^^^^

.. java:field:: public static final String ELEMENT_XPATH
   :outertype: ApacheXMLDSigner

   Name of the XPath element [XMLDSIG 6.6.3]

NAMESPACE_PREFIX_DS
^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String NAMESPACE_PREFIX_DS
   :outertype: ApacheXMLDSigner

   Namespace prefix of \ ``Signature``\ .

NAMESPACE_PREFIX_SOAP_ENVELOPE
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String NAMESPACE_PREFIX_SOAP_ENVELOPE
   :outertype: ApacheXMLDSigner

   Namespace prefix of SOAP envelope.

NAMESPACE_URI_DS
^^^^^^^^^^^^^^^^

.. java:field:: public static final String NAMESPACE_URI_DS
   :outertype: ApacheXMLDSigner

   Namespace URI of \ ``Signature``\ .

NAMESPACE_URI_SOAP_ENVELOPE
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String NAMESPACE_URI_SOAP_ENVELOPE
   :outertype: ApacheXMLDSigner

   Namespace URI of SOAP envelope.

NAMESPACE_URI_XML_NS
^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String NAMESPACE_URI_XML_NS
   :outertype: ApacheXMLDSigner

   Namespace URI of \ ``xmlns``\ .

SIGNATURE_METHOD
^^^^^^^^^^^^^^^^

.. java:field:: public static final String SIGNATURE_METHOD
   :outertype: ApacheXMLDSigner

   Name of the digital signature method required, qualified by the digital signature namespace [XMLDSIG 6.1]

TRANSFORM_ALGORITHM_XPATH
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String TRANSFORM_ALGORITHM_XPATH
   :outertype: ApacheXMLDSigner

   Name of the XPath transform algorithm recommended [XMLDSIG 6.1]

TRANSFORM_XPATH
^^^^^^^^^^^^^^^

.. java:field:: public static final String TRANSFORM_XPATH
   :outertype: ApacheXMLDSigner

   XPath transform string used in the implementation.

documents
^^^^^^^^^

.. java:field:: protected ArrayList documents
   :outertype: ApacheXMLDSigner

   Internal variable for holding the documents needed to be referred in the signature.

envelope
^^^^^^^^

.. java:field:: protected Document envelope
   :outertype: ApacheXMLDSigner

   Internal variable for holding the envelope of the signature.

logger
^^^^^^

.. java:field:: protected static Logger logger
   :outertype: ApacheXMLDSigner

   Logger

signature
^^^^^^^^^

.. java:field:: protected XMLSignature signature
   :outertype: ApacheXMLDSigner

   Internal variable of the Apache XML Security library signature object for doing the actual signing/verifying algorithm.

trusted
^^^^^^^

.. java:field:: protected CompositeKeyStore trusted
   :outertype: ApacheXMLDSigner

   Internal variable for holding the trusted anchor for certificate path verification.

Constructors
------------
ApacheXMLDSigner
^^^^^^^^^^^^^^^^

.. java:constructor:: public ApacheXMLDSigner()
   :outertype: ApacheXMLDSigner

   Default constructor to initialize the internal variables.

Methods
-------
addCertResolver
^^^^^^^^^^^^^^^

.. java:method:: public void addCertResolver(CertResolver certResolver, Object obj)
   :outertype: ApacheXMLDSigner

addDocument
^^^^^^^^^^^

.. java:method:: public void addDocument(String uri, InputStream is, String contentType)
   :outertype: ApacheXMLDSigner

   Adds a reference to a document attachment to the signature.

   :param uri: the URI of the document attachment
   :param is: the input stream of the content of the document
   :param contentType: the content type of the document

getElement
^^^^^^^^^^

.. java:method:: public Element getElement()
   :outertype: ApacheXMLDSigner

   Gets the DOM element of the signature generated.

   :return: the DOM element of the signature

setEnvelope
^^^^^^^^^^^

.. java:method:: public void setEnvelope(Document doc, String algo, String digestAlgo) throws SignException
   :outertype: ApacheXMLDSigner

   Set the envelope to host the Signature element. That is the XML document where the Signature element to be added. The digital signature here will always be an enveloped signature. The envelope will be included in the process of signing.

   :param doc: the XML document to host the Signature element
   :param algo: the algorithm used for digital signature. Currently, only two values are tested: \ ``dsa-sha1``\  and \ ``rsa-sha1``\ .
   :param digestAlgo: the algorithm used for making digest value. Currently, one value is supported: \ ``sha1``\
   :throws SignException: internal exception when doing initialization on Apache XML Security library

setEnvelope
^^^^^^^^^^^

.. java:method:: public void setEnvelope(Document doc, String algo) throws SignException
   :outertype: ApacheXMLDSigner

   Set the envelope to host the Signature element. That is the XML document where the Signature element to be added. The digital signature here will always be an enveloped signature. The envelope will be included in the process of signing.

   :param doc: the XML document to host the Signature element
   :param algo: the algorithm used for digital signature. Currently, only two values are tested: \ ``dsa-sha1``\  and \ ``rsa-sha1``\ .
   :throws SignException: internal exception when doing initialization on Apache XML Security library

setEnvelope
^^^^^^^^^^^

.. java:method:: public void setEnvelope(Document doc) throws SignException
   :outertype: ApacheXMLDSigner

   Set the envelope to host the Signature element. That is the XML document where the Signature element to be added. The digital signature here will always be an enveloped signature. The envelope will be included in the process of signing.

   :param doc: the XML document to host the Signature element
   :throws SignException: internal exception when doing initialization on Apache XML Security library

setTrustAnchor
^^^^^^^^^^^^^^

.. java:method:: public void setTrustAnchor(CompositeKeyStore ks)
   :outertype: ApacheXMLDSigner

   Sets the trust anchor for verfication of certificate path.

   :param ks: the keystore providing the trusted certificates

sign
^^^^

.. java:method:: public void sign(CompositeKeyStore ks, String alias, char[] password) throws SignException
   :outertype: ApacheXMLDSigner

   Signs the envelope and documents by using the specified key in the keystore.

   :param ks: the keystore holding the key for signing
   :param alias: the alias of the key for signing
   :param password: the password for accessing the key for signing
   :throws SignException: when there is any error in the processing of signing

verify
^^^^^^

.. java:method:: public boolean verify() throws VerifyException
   :outertype: ApacheXMLDSigner

   Verifies the signature in the envelope passed in, which may reference the documents specified using the addDocument method.

   :throws VerifyException: when there is any error in the processing of verification
   :return: true if the signature can be verified successfully, false if otherwise.

