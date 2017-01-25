.. java:import:: java.io File

.. java:import:: java.io FileInputStream

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.security InvalidKeyException

.. java:import:: java.security NoSuchAlgorithmException

.. java:import:: java.security NoSuchProviderException

.. java:import:: java.security PublicKey

.. java:import:: java.security SignatureException

.. java:import:: java.security.cert Certificate

.. java:import:: java.security.cert CertificateException

.. java:import:: java.security.cert CertificateExpiredException

.. java:import:: java.security.cert CertificateFactory

.. java:import:: java.security.cert CertificateNotYetValidException

.. java:import:: java.security.cert X509Certificate

.. java:import:: java.util Date

CertSource
==========

.. java:package:: hk.hku.cecid.ebms.pkg.pki
   :noindex:

.. java:type:: public class CertSource

   This class loads a X509 certificate file. Basically this class only acts as a convenience wrapper of java.security.cert.X509Certificate.

   :author: kcyee

Fields
------
x509Cert
^^^^^^^^

.. java:field:: protected X509Certificate x509Cert
   :outertype: CertSource

   internal X509 certificate storage.

Constructors
------------
CertSource
^^^^^^^^^^

.. java:constructor:: public CertSource()
   :outertype: CertSource

   Default constructor. The user should call load() to further initialize the certificate.

CertSource
^^^^^^^^^^

.. java:constructor:: public CertSource(File certFile) throws CertificateException
   :outertype: CertSource

   Constructor with initialization parameters. The certificate will be loaded from the file specified.

   :param certFile: the certificate file
   :throws CertificateException: if the file specified cannot be read, or any errors occurred when loading the file.

CertSource
^^^^^^^^^^

.. java:constructor:: public CertSource(String certFile) throws CertificateException
   :outertype: CertSource

   Constructor with initialization parameters. The certificate will be loaded from the file specified.

   :param certFile: the file name of the certificate file
   :throws CertificateException: if the file specified cannot be read, or any errors occurred when loading the file.

CertSource
^^^^^^^^^^

.. java:constructor:: public CertSource(X509Certificate cert)
   :outertype: CertSource

   Constructor with initialization parameters. The class will be initialized with the specified certificate.

   :param cert: the preloaded certificate

Methods
-------
getInternalCert
^^^^^^^^^^^^^^^

.. java:method:: public X509Certificate getInternalCert()
   :outertype: CertSource

   Gets the X509Certificate stored internally.

   :return: the X509Certificate stored internally.

getIssuer
^^^^^^^^^

.. java:method:: public String getIssuer() throws InitializationException
   :outertype: CertSource

   Gets the distinguished name (DN) of the issuer of the certificate.

   :throws InitializationException: the object is not yet initialized
   :return: the DN of the issuer

getPublicKey
^^^^^^^^^^^^

.. java:method:: public PublicKey getPublicKey()
   :outertype: CertSource

   Gets the public key in this certificate.

   :return: the public key in this certificate.

isValid
^^^^^^^

.. java:method:: public boolean isValid() throws InitializationException
   :outertype: CertSource

   Checks whether the certificate is valid in current time.

   :return: true if the certificate is still valid, false if otherwise.

isValid
^^^^^^^

.. java:method:: public boolean isValid(Date d) throws InitializationException
   :outertype: CertSource

   Checks whether the certificate is valid in the specified time.

   :param d: the specified time
   :return: true if the certificate is valid, false if otherwise.

load
^^^^

.. java:method:: public void load(File certFile) throws CertificateException
   :outertype: CertSource

   Loads the certificate file.

   :param certFile: the certificate file
   :throws CertificateException: if the file specified cannot be read, or any errors occurred when loading the file.

load
^^^^

.. java:method:: public void load(String certFile) throws CertificateException
   :outertype: CertSource

   Loads the certificate file.

   :param certFile: the file name of the certificate file
   :throws CertificateException: if the file specified cannot be read, or any errors occurred when loading the file.

verify
^^^^^^

.. java:method:: public boolean verify(PublicKey pubKey) throws InitializationException
   :outertype: CertSource

   Verifies whether the certificate is signed by the private key corresponding to the specified public key.

   :param pubKey: the public key for verification
   :return: true if the verification is passed, false if otherwise.

verify
^^^^^^

.. java:method:: public boolean verify(Certificate cert) throws InitializationException
   :outertype: CertSource

   Verifies whether the certificate is signed by the private key corresponding to public key in the specified certificate.

   :param cert: the certificate for verification
   :return: true if the verification is passed, false if otherwise.

verify
^^^^^^

.. java:method:: public boolean verify(CertSource cert) throws InitializationException
   :outertype: CertSource

   Verifies whether the certificate is signed by the private key corresponding to public key in the specified certificate.

   :param cert: the certificate for verification
   :return: true if the verification is passed, false if otherwise.

