.. java:import:: java.security InvalidKeyException

.. java:import:: java.security NoSuchAlgorithmException

.. java:import:: java.security NoSuchProviderException

.. java:import:: java.security PublicKey

.. java:import:: java.security SignatureException

.. java:import:: java.security.cert CRLException

.. java:import:: java.security.cert Certificate

.. java:import:: java.security.cert X509CRL

.. java:import:: java.util Date

CRLSource
=========

.. java:package:: hk.hku.cecid.ebms.pkg.pki
   :noindex:

.. java:type:: public abstract class CRLSource

   This is an abstract class for holding a X509 CRL instance. The functionality of CRL is given by this class. The sub-classes will provide different initialization method for loading the CRL, for example, through a file or through LDAP.

   :author: kcyee

Fields
------
crl
^^^

.. java:field:: protected X509CRL crl
   :outertype: CRLSource

   Internal storage of X509 CRL

ready
^^^^^

.. java:field:: protected boolean ready
   :outertype: CRLSource

   Indicates the CRL has been loaded correctly or not

Constructors
------------
CRLSource
^^^^^^^^^

.. java:constructor:: public CRLSource()
   :outertype: CRLSource

   Default constructor. It initializes the object. But the object is still unusable until init() is called.

Methods
-------
getIssuer
^^^^^^^^^

.. java:method:: public String getIssuer() throws InitializationException
   :outertype: CRLSource

   Gets the distinguished name (DN) of the issuer of the CRL.

   :throws InitializationException: the object is not yet initialized
   :return: the DN of the issuer

getNextUpdate
^^^^^^^^^^^^^

.. java:method:: public Date getNextUpdate() throws InitializationException
   :outertype: CRLSource

   Gets the next update date of the CRL.

   :throws InitializationException: the object is not yet initialized
   :return: the next update date

getThisUpdate
^^^^^^^^^^^^^

.. java:method:: public Date getThisUpdate() throws InitializationException
   :outertype: CRLSource

   Gets the last update date of the CRL.

   :throws InitializationException: the object is not yet initialized
   :return: the last update date

init
^^^^

.. java:method:: public abstract void init() throws CRLException
   :outertype: CRLSource

   Initializes the object. The initialization procedure depends on the source of the CRL. So, we declare this method as abstract here, leaving the sub-classes to concern about the initialization.

   :throws CRLException: Initialization error occurs

isReady
^^^^^^^

.. java:method:: public boolean isReady()
   :outertype: CRLSource

   Gets the readiness of the object. The object will be ready for use after init() is called. And the internal X509 CRL storage is populated.

   :return: true if the object is ready for use; false if otherwise

isRevoked
^^^^^^^^^

.. java:method:: public boolean isRevoked(Certificate cert) throws InitializationException
   :outertype: CRLSource

   Checks the specified certificate against the CRL to see whether the certificate has been revoked or not.

   :param cert: the certificate to be tested against the CRL
   :throws InitializationException: the object is not yet initialized
   :return: true if the specified certificate is revoked according to the CRL; false if otherwise

isRevoked
^^^^^^^^^

.. java:method:: public boolean isRevoked(CertSource cert) throws InitializationException
   :outertype: CRLSource

   Checks the specified certificate against the CRL to see whether the certificate has been revoked or not.

   :param cert: the certificate to be tested against the CRL
   :throws InitializationException: the object is not yet initialized
   :return: true if the specified certificate is revoked according to the CRL; false if otherwise

verifySignature
^^^^^^^^^^^^^^^

.. java:method:: public boolean verifySignature(PublicKey pubKey) throws InitializationException
   :outertype: CRLSource

   Verifies the CRL to check whether is is signed by the private key corresponding to the specified public key or not.

   :param pubKey: the public key used to verify
   :throws InitializationException: the object is not yet initialized
   :return: true if the CRL is signed by the private key corresponding to \ ``pubKey``\ ; false if otherwise

verifySignature
^^^^^^^^^^^^^^^

.. java:method:: public boolean verifySignature(Certificate cert) throws InitializationException
   :outertype: CRLSource

   Verifies the CRL to check whether is is signed by the private key corresponding to the public key in the specified certificate or not.

   :param cert: the certificate storing the public key to be used for verification
   :throws InitializationException: the object is not yet initialized
   :return: true if the CRL is signed by the private key corresponding to the public key stored in \ ``cert``\ ; false if otherwise

verifySignature
^^^^^^^^^^^^^^^

.. java:method:: public boolean verifySignature(CertSource cert) throws InitializationException
   :outertype: CRLSource

   Verifies the CRL to check whether is is signed by the private key corresponding to the public key in the specified certificate or not.

   :param cert: the certificate storing the public key to be used for verification
   :throws InitializationException: the object is not yet initialized
   :return: true if the CRL is signed by the private key corresponding to the public key stored in \ ``cert``\ ; false if otherwise

