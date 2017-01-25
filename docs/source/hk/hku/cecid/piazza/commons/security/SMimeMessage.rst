.. java:import:: hk.hku.cecid.piazza.commons.activation Mailcap

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io InputStream

.. java:import:: java.security DigestInputStream

.. java:import:: java.security MessageDigest

.. java:import:: java.security PrivateKey

.. java:import:: java.security Security

.. java:import:: java.security.cert CertStore

.. java:import:: java.security.cert CollectionCertStoreParameters

.. java:import:: java.security.cert X509Certificate

.. java:import:: java.util ArrayList

.. java:import:: java.util Iterator

.. java:import:: javax.activation CommandInfo

.. java:import:: javax.activation CommandMap

.. java:import:: javax.activation MailcapCommandMap

.. java:import:: javax.mail Session

.. java:import:: javax.mail.internet InternetHeaders

.. java:import:: javax.mail.internet MimeBodyPart

.. java:import:: javax.mail.internet MimeMultipart

.. java:import:: org.bouncycastle.asn1 ASN1EncodableVector

.. java:import:: org.bouncycastle.asn1 ASN1ObjectIdentifier

.. java:import:: org.bouncycastle.asn1.cms AttributeTable

.. java:import:: org.bouncycastle.asn1.cms IssuerAndSerialNumber

.. java:import:: org.bouncycastle.asn1.smime SMIMECapabilitiesAttribute

.. java:import:: org.bouncycastle.asn1.smime SMIMECapability

.. java:import:: org.bouncycastle.asn1.smime SMIMECapabilityVector

.. java:import:: org.bouncycastle.asn1.smime SMIMEEncryptionKeyPreferenceAttribute

.. java:import:: org.bouncycastle.asn1.x509 X509Name

.. java:import:: org.bouncycastle.cms CMSException

.. java:import:: org.bouncycastle.cms DefaultCMSSignatureAlgorithmNameGenerator

.. java:import:: org.bouncycastle.cms RecipientId

.. java:import:: org.bouncycastle.cms RecipientInformation

.. java:import:: org.bouncycastle.cms RecipientInformationStore

.. java:import:: org.bouncycastle.cms SignerInformation

.. java:import:: org.bouncycastle.cms SignerInformationStore

.. java:import:: org.bouncycastle.cms SignerInformationVerifier

.. java:import:: org.bouncycastle.cms.bc BcRSASignerInfoVerifierBuilder

.. java:import:: org.bouncycastle.cms.jcajce JcaSimpleSignerInfoGeneratorBuilder

.. java:import:: org.bouncycastle.cms.jcajce JceKeyTransRecipientInfoGenerator

.. java:import:: org.bouncycastle.cms.jcajce JceCMSContentEncryptorBuilder

.. java:import:: org.bouncycastle.cms.jcajce JceKeyTransRecipientId

.. java:import:: org.bouncycastle.cms.jcajce JceKeyTransEnvelopedRecipient

.. java:import:: org.bouncycastle.cms.jcajce ZlibCompressor

.. java:import:: org.bouncycastle.cms.jcajce ZlibExpanderProvider

.. java:import:: org.bouncycastle.cert.jcajce JcaCertStore

.. java:import:: org.bouncycastle.cert.jcajce JcaX509CertificateHolder

.. java:import:: org.bouncycastle.jce.provider BouncyCastleProvider

.. java:import:: org.bouncycastle.mail.smime SMIMECompressed

.. java:import:: org.bouncycastle.mail.smime SMIMECompressedGenerator

.. java:import:: org.bouncycastle.mail.smime SMIMEEnveloped

.. java:import:: org.bouncycastle.mail.smime SMIMEEnvelopedGenerator

.. java:import:: org.bouncycastle.mail.smime SMIMESigned

.. java:import:: org.bouncycastle.mail.smime SMIMESignedGenerator

.. java:import:: org.bouncycastle.operator DefaultSignatureAlgorithmIdentifierFinder

.. java:import:: org.bouncycastle.operator DefaultDigestAlgorithmIdentifierFinder

.. java:import:: org.bouncycastle.operator.bc BcDigestCalculatorProvider

.. java:import:: org.bouncycastle.util.encoders Base64

SMimeMessage
============

.. java:package:: hk.hku.cecid.piazza.commons.security
   :noindex:

.. java:type:: public class SMimeMessage

   SMimeMessage represents a Secure MIME Message. It encapsulates a MIME body part and provides methods for digital signing, signature verification, encryption, decryption, compression, and decompression.

   :author: Hugo Y. K. Lam

Fields
------
CONTENT_TRANSFER_ENC_BASE64
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String CONTENT_TRANSFER_ENC_BASE64
   :outertype: SMimeMessage

   Content transfer encoding: Base 64

CONTENT_TRANSFER_ENC_BINARY
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String CONTENT_TRANSFER_ENC_BINARY
   :outertype: SMimeMessage

   Content transfer encoding: Binary

DIGEST_ALG_MD5
^^^^^^^^^^^^^^

.. java:field:: public static final String DIGEST_ALG_MD5
   :outertype: SMimeMessage

   Digest algorithm: MD5

DIGEST_ALG_SHA1
^^^^^^^^^^^^^^^

.. java:field:: public static final String DIGEST_ALG_SHA1
   :outertype: SMimeMessage

   Digest algorithm: SHA

ENCRYPT_ALG_DES_EDE3_CBC
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ENCRYPT_ALG_DES_EDE3_CBC
   :outertype: SMimeMessage

   Encryption algorithm: DES EDE3

ENCRYPT_ALG_RC2_CBC
^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ENCRYPT_ALG_RC2_CBC
   :outertype: SMimeMessage

   Encryption algorithm: RC2

Constructors
------------
SMimeMessage
^^^^^^^^^^^^

.. java:constructor:: public SMimeMessage(MimeBodyPart bodyPart)
   :outertype: SMimeMessage

   Creates a new instance of SMimeMessage.

   :param bodyPart: the original MIME body part.

SMimeMessage
^^^^^^^^^^^^

.. java:constructor:: public SMimeMessage(MimeBodyPart bodyPart, X509Certificate cert)
   :outertype: SMimeMessage

   Creates a new instance of SMimeMessage.

   :param bodyPart: the original MIME body part.
   :param cert: the certificate for signature verification or encryption.

SMimeMessage
^^^^^^^^^^^^

.. java:constructor:: public SMimeMessage(MimeBodyPart bodyPart, X509Certificate cert, Session session)
   :outertype: SMimeMessage

   Creates a new instance of SMimeMessage.

   :param bodyPart: the original MIME body part.
   :param cert: the certificate for signature verification or encryption.
   :param session: the mail session.

SMimeMessage
^^^^^^^^^^^^

.. java:constructor:: public SMimeMessage(MimeBodyPart bodyPart, X509Certificate cert, PrivateKey privateKey)
   :outertype: SMimeMessage

   Creates a new instance of SMimeMessage.

   :param bodyPart: the original MIME body part.
   :param cert: the certificate for signature verification or encryption.
   :param privateKey: the private key for digital signing or decryption.

SMimeMessage
^^^^^^^^^^^^

.. java:constructor:: public SMimeMessage(MimeBodyPart bodyPart, X509Certificate cert, PrivateKey privateKey, Session session)
   :outertype: SMimeMessage

   Creates a new instance of SMimeMessage.

   :param bodyPart: the original MIME body part.
   :param cert: the certificate for signature verification or encryption.
   :param privateKey: the private key for digital signing or decryption.
   :param session: the mail session.

SMimeMessage
^^^^^^^^^^^^

.. java:constructor:: protected SMimeMessage(MimeBodyPart bodyPart, SMimeMessage smime)
   :outertype: SMimeMessage

   Creates a new instance of SMimeMessage.

   :param bodyPart: the original MIME body part.
   :param smime: the S/MIME message from which the configuration is copied.

Methods
-------
compress
^^^^^^^^

.. java:method:: public SMimeMessage compress() throws SMimeException
   :outertype: SMimeMessage

   Compresses the encapsulated MIME body part.

   :throws SMimeException: if unable to compress the body part.
   :return: an S/MIME message encapsulating the compressed MIME body part.

decompress
^^^^^^^^^^

.. java:method:: public SMimeMessage decompress() throws SMimeException
   :outertype: SMimeMessage

   Decompresses the encapsulated MIME body part.

   :throws SMimeException: if unable to decompress the body part.
   :return: an S/MIME message encapsulating the decompressed MIME body part.

decrypt
^^^^^^^

.. java:method:: public SMimeMessage decrypt() throws SMimeException
   :outertype: SMimeMessage

   Decrypts the encapsulated MIME body part.

   :throws SMimeException: if unable to decrpyt the body part.
   :return: an S/MIME message encapsulating the decrypted MIME body part.

decrypt
^^^^^^^

.. java:method:: public SMimeMessage decrypt(PrivateKey privateKey) throws SMimeException
   :outertype: SMimeMessage

   Decrypts the encapsulated MIME body part.

   :param privateKey: the private key for decryption.
   :throws SMimeException: if unable to decrpyt the body part.
   :return: an S/MIME message encapsulating the decrypted MIME body part.

digest
^^^^^^

.. java:method:: public String digest() throws SMimeException
   :outertype: SMimeMessage

   Digests the encapsulated MIME body part.

   :throws SMimeException: if unable to compute the digest value.
   :return: the digested value in Base 64 format.

digest
^^^^^^

.. java:method:: public String digest(String digestAlg, boolean isHeadersIncluded) throws SMimeException
   :outertype: SMimeMessage

   Digests the encapsulated MIME body part.

   :param digestAlg: digest algorithm.
   :param isHeadersIncluded: true if the digest should be computed on both the headers and the content of the encapsulated body part.
   :throws SMimeException: if unable to compute the digest value.
   :return: the digested value in Base 64 format.

encrypt
^^^^^^^

.. java:method:: public SMimeMessage encrypt() throws SMimeException
   :outertype: SMimeMessage

   Encrypts the encapsulated MIME body part.

   :throws SMimeException: if unable to encrpyt the body part.
   :return: an S/MIME message encapsulating the encrypted MIME body part.

encrypt
^^^^^^^

.. java:method:: public SMimeMessage encrypt(X509Certificate cert) throws SMimeException
   :outertype: SMimeMessage

   Encrypts the encapsulated MIME body part.

   :param cert: the certificate for encryption.
   :throws SMimeException: if unable to encrpyt the body part.
   :return: an S/MIME message encapsulating the encrypted MIME body part.

getBodyPart
^^^^^^^^^^^

.. java:method:: public MimeBodyPart getBodyPart()
   :outertype: SMimeMessage

   Gets the encapsulated MIME body part.

   :return: the encapsulated MIME body part.

getContentTransferEncoding
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getContentTransferEncoding()
   :outertype: SMimeMessage

   Gets the content transfer encoding which will be used in encryption, digital signing, and compression.

   :return: the content transfer encoding.

getDigestAlgorithm
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getDigestAlgorithm()
   :outertype: SMimeMessage

   Gets the digest algorithm which will be used in digital signing.

   :return: the digest algorithm.

getEncryptAlgorithm
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getEncryptAlgorithm()
   :outertype: SMimeMessage

   Gets the encryption algorithm which will be used in encryption.

   :return: the encryption algorithm.

isCompressed
^^^^^^^^^^^^

.. java:method:: public boolean isCompressed() throws SMimeException
   :outertype: SMimeMessage

   Checks if the encapsulated MIME body part is compressed.

   :throws SMimeException: if error occurred in checking.
   :return: true if the encapsulated MIME body part is compressed.

isEncrypted
^^^^^^^^^^^

.. java:method:: public boolean isEncrypted() throws SMimeException
   :outertype: SMimeMessage

   Checks if the encapsulated MIME body part is encrypted.

   :throws SMimeException: if error occurred in checking.
   :return: true if the encapsulated MIME body part is encrypted.

isSigned
^^^^^^^^

.. java:method:: public boolean isSigned() throws SMimeException
   :outertype: SMimeMessage

   Checks if the encapsulated MIME body part is signed.

   :throws SMimeException: if error occurred in checking.
   :return: true if the encapsulated MIME body part is signed.

setContentTransferEncoding
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setContentTransferEncoding(String contentTransferEncoding)
   :outertype: SMimeMessage

   Sets the content transfer encoding to used in encryption, digital signing, and compression.

   :param contentTransferEncoding: the content transfer encoding.

setDigestAlgorithm
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setDigestAlgorithm(String digestAlgorithm)
   :outertype: SMimeMessage

   Sets the digest algorithm to used in digital signing.

   :param digestAlgorithm: the digest algorithm.

setEncryptAlgorithm
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setEncryptAlgorithm(String encryptAlgorithm)
   :outertype: SMimeMessage

   Sets the encryption algorithm to be used in encryption.

   :param encryptAlgorithm: the encryption algorithm.

sign
^^^^

.. java:method:: public SMimeMessage sign() throws SMimeException
   :outertype: SMimeMessage

   Signs the encapsulated MIME body part.

   :throws SMimeException: if unable to sign the body part.
   :return: an S/MIME message encapsulating the signed MIME body part.

unsign
^^^^^^

.. java:method:: public SMimeMessage unsign() throws SMimeException
   :outertype: SMimeMessage

   Unsigns the encapsulated MIME body part.

   :throws SMimeException: if unable to unsign the body part.
   :return: the an S/MIME message encapsulating the signed content.

verify
^^^^^^

.. java:method:: public SMimeMessage verify() throws SMimeException
   :outertype: SMimeMessage

   Verifies the encapsulated MIME body part.

   :throws SMimeException: if unable to verify the body part.
   :return: an S/MIME message encapsulating the signed content.

verify
^^^^^^

.. java:method:: public SMimeMessage verify(X509Certificate cert) throws SMimeException
   :outertype: SMimeMessage

   Verifies the encapsulated MIME body part.

   :param cert: the certificate for verification.
   :throws SMimeException: if unable to verify the body part.
   :return: an S/MIME message encapsulating the signed content.

