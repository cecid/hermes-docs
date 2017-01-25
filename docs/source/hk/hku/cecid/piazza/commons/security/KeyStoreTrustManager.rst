.. java:import:: java.security KeyStore

.. java:import:: java.security KeyStoreException

.. java:import:: java.security.cert CertificateException

.. java:import:: java.security.cert X509Certificate

.. java:import:: java.util Enumeration

.. java:import:: javax.net.ssl X509TrustManager

KeyStoreTrustManager
====================

.. java:package:: hk.hku.cecid.piazza.commons.security
   :noindex:

.. java:type:: public class KeyStoreTrustManager extends KeyStoreComponent implements X509TrustManager

   This class implements the javax.net.ssl.X509TrustManager, which trusts a Certificate Chain if any of the certificate in the certificate chain is stored in the KeyStore.

   :author: Bob P. Y. Koon

Constructors
------------
KeyStoreTrustManager
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreTrustManager()
   :outertype: KeyStoreTrustManager

   Creates a new instance of KeyStoreTrustManger.

KeyStoreTrustManager
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreTrustManager(KeyStoreManager keyman) throws KeyStoreManagementException
   :outertype: KeyStoreTrustManager

   Creates a new instance of KeyStoreTrustManger.

   :param keyman: the trusted key store manager.
   :throws KeyStoreManagementException: if the specified key store manager is null.

KeyStoreTrustManager
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreTrustManager(KeyStore keyStore) throws KeyStoreManagementException
   :outertype: KeyStoreTrustManager

   Creates a new instance of KeyStoreTrustManger.

   :param keyStore: the initialized trusted key store.
   :throws KeyStoreManagementException: if the specified key store is null.

Methods
-------
checkClientTrusted
^^^^^^^^^^^^^^^^^^

.. java:method:: public void checkClientTrusted(X509Certificate[] chain, String authType) throws CertificateException
   :outertype: KeyStoreTrustManager

   Checks if the client is trusted. It trusts the certificate chain if the embeded key store contains one of the certificate in the chain.

   :param chain: the peer certificate chain.
   :param authType: the key exchange algorithm used.
   :throws IllegalArgumentException: if null or zero-length chain is passed in for the chain parameter or if null or zero-length string is passed in for the authType parameter.
   :throws CertificateException: if the certificate chain is not trusted by this TrustManager.

   **See also:** :java:ref:`javax.net.ssl.X509TrustManager.checkClientTrusted(java.security.cert.X509Certificate[],java.lang.String)`

checkServerTrusted
^^^^^^^^^^^^^^^^^^

.. java:method:: public void checkServerTrusted(X509Certificate[] chain, String authType) throws CertificateException
   :outertype: KeyStoreTrustManager

   Checks if the server is trusted. It trusts the certificate chain if the embeded key store contains one of the certificate in the chain.

   :param chain: the peer certificate chain.
   :param authType: the key exchange algorithm used.
   :throws IllegalArgumentException: if null or zero-length chain is passed in for the chain parameter or if null or zero-length string is passed in for the authType parameter.
   :throws CertificateException: if the certificate chain is not trusted by this TrustManager.

   **See also:** :java:ref:`javax.net.ssl.X509TrustManager.checkServerTrusted(java.security.cert.X509Certificate[],java.lang.String)`

getAcceptedIssuers
^^^^^^^^^^^^^^^^^^

.. java:method:: public X509Certificate[] getAcceptedIssuers()
   :outertype: KeyStoreTrustManager

   Returns an array of certificate authority certificates which are stored in the embeded key store.

   :return: a non-null (possibly empty) array of acceptable CA issuer certificates.

