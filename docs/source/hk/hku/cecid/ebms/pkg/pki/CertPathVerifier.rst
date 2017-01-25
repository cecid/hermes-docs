.. java:import:: java.io IOException

.. java:import:: java.security InvalidAlgorithmParameterException

.. java:import:: java.security KeyStore

.. java:import:: java.security KeyStoreException

.. java:import:: java.security NoSuchAlgorithmException

.. java:import:: java.security.cert CertPath

.. java:import:: java.security.cert CertPathBuilder

.. java:import:: java.security.cert CertPathBuilderException

.. java:import:: java.security.cert CertStore

.. java:import:: java.security.cert CollectionCertStoreParameters

.. java:import:: java.security.cert PKIXBuilderParameters

.. java:import:: java.security.cert X509CertSelector

.. java:import:: java.security.cert X509Certificate

.. java:import:: java.util ArrayList

.. java:import:: org.apache.log4j Logger

CertPathVerifier
================

.. java:package:: hk.hku.cecid.ebms.pkg.pki
   :noindex:

.. java:type:: public class CertPathVerifier

   This class wraps the certificate path verification routine into a separate static method. This is useful when JDK1.3 is used, the cert path verification is skipped. And the JDK1.4 specific classes will not be loaded, as they are all called in this class.

   :author: kcyee

Fields
------
logger
^^^^^^

.. java:field:: protected static Logger logger
   :outertype: CertPathVerifier

   Logger

Methods
-------
verify
^^^^^^

.. java:method:: public static boolean verify(java.security.cert.Certificate[] certs, CompositeKeyStore trusted)
   :outertype: CertPathVerifier

   Verifies the specified certificate chain against the trusted anchors. The trusted anchors contains all public certificate that is trusted. This method will make use of JDK1.4's utilities to verify the certificate chain.

   :param certs: the certificate chain being verified
   :param trusted: the keystore storing the trusted anchors.
   :return: true if verification is succeeded; false otherwise

