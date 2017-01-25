.. java:import:: hk.hku.cecid.piazza.commons.util ArrayUtilities

.. java:import:: java.security KeyStore

.. java:import:: java.security KeyStoreException

.. java:import:: java.security NoSuchAlgorithmException

.. java:import:: java.security PrivateKey

.. java:import:: java.security PublicKey

.. java:import:: java.security UnrecoverableKeyException

.. java:import:: java.security.cert Certificate

.. java:import:: java.security.cert X509Certificate

.. java:import:: java.util ArrayList

KeyStoreManager
===============

.. java:package:: hk.hku.cecid.piazza.commons.security
   :noindex:

.. java:type:: public class KeyStoreManager extends KeyStoreComponent

   KeyStoreManager manages a key store and provides convenient methods such as method that retrieves an X509Certificate or retrieves a private key.

   :author: Hugo Y. K. Lam

Constructors
------------
KeyStoreManager
^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreManager()
   :outertype: KeyStoreManager

   Creates a new instance of KeyStoreManager.

KeyStoreManager
^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreManager(KeyStore keyStore) throws KeyStoreManagementException
   :outertype: KeyStoreManager

   Creates a new instance of KeyStoreManager.

   :param keyStore: the initialized keystore to be managed.
   :throws KeyStoreManagementException: if the specified key store is null.

KeyStoreManager
^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreManager(KeyStore keyStore, String alias, String keyPass) throws KeyStoreManagementException
   :outertype: KeyStoreManager

   Creates a new instance of KeyStoreManager.

   :param keyStore: the initialized keystore to be managed.
   :param alias: the alias name associating with the managed key.
   :param keyPass: the key password.
   :throws KeyStoreManagementException: if the specified key store is null.

KeyStoreManager
^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreManager(String location, String storePass) throws KeyStoreManagementException
   :outertype: KeyStoreManager

   Creates a new instance of KeyStoreManager.

   :param location: the key store location.
   :param storePass: the key store password.
   :throws KeyStoreManagementException: if unable to initialize the key store with the given paramemeters.

KeyStoreManager
^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreManager(String location, String storePass, String alias, String keyPass) throws KeyStoreManagementException
   :outertype: KeyStoreManager

   Creates a new instance of KeyStoreManager.

   :param location: the key store location.
   :param storePass: the key store password.
   :param alias: the alias name.
   :param keyPass: the key password.
   :throws KeyStoreManagementException: if unable to initialize the key store with the given paramemeters.

KeyStoreManager
^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreManager(String location, String storePass, String storeType, Object provider) throws KeyStoreManagementException
   :outertype: KeyStoreManager

   Creates a new instance of KeyStoreManager.

   :param location: the key store location.
   :param storePass: the key store password.
   :param storeType: the key store type.
   :param provider: the key store provider.
   :throws KeyStoreManagementException: if unable to initialize the key store with the given paramemeters.

KeyStoreManager
^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreManager(String location, String storePass, String alias, String keyPass, String storeType, Object provider) throws KeyStoreManagementException
   :outertype: KeyStoreManager

   Creates a new instance of KeyStoreManager.

   :param location: the key store location.
   :param storePass: the key store password.
   :param alias: the alias name.
   :param keyPass: the key password.
   :param storeType: the key store type.
   :param provider: the key store provider.
   :throws KeyStoreManagementException: if unable to initialize the key store with the given paramemeters.

Methods
-------
getAlias
^^^^^^^^

.. java:method:: public String getAlias()
   :outertype: KeyStoreManager

   Gets the managed alias.

   :return: the managed alias.

getAliases
^^^^^^^^^^

.. java:method:: public String[] getAliases()
   :outertype: KeyStoreManager

   Gets all the aliases in the managed key store.

   :return: all the aliases in the managed key store.

getCertificate
^^^^^^^^^^^^^^

.. java:method:: public Certificate getCertificate()
   :outertype: KeyStoreManager

   Gets the managed certificate.

   :return: the managed certificate.

getCertificate
^^^^^^^^^^^^^^

.. java:method:: public Certificate getCertificate(String alias)
   :outertype: KeyStoreManager

   Gets the certificate asscoiated with the given alias name.

   :param alias: the alias name.
   :return: the certificate.

getCertificateChain
^^^^^^^^^^^^^^^^^^^

.. java:method:: public Certificate[] getCertificateChain()
   :outertype: KeyStoreManager

   Gets the managed certificate chain.

   :return: the managed certificate chain.

getCertificateChain
^^^^^^^^^^^^^^^^^^^

.. java:method:: public Certificate[] getCertificateChain(String alias)
   :outertype: KeyStoreManager

   Gets the certificate chain asscoiated with the given alias name.

   :param alias: the alias name.
   :return: the certificate chain.

getKeyStore
^^^^^^^^^^^

.. java:method:: public KeyStore getKeyStore()
   :outertype: KeyStoreManager

   Gets the managed key store.

   :return: the key store.

getPrivateKey
^^^^^^^^^^^^^

.. java:method:: public PrivateKey getPrivateKey() throws NoSuchAlgorithmException, UnrecoverableKeyException
   :outertype: KeyStoreManager

   Gets the managed private key.

   :throws NoSuchAlgorithmException: if the algorithm for recovering the key cannot be found.
   :throws UnrecoverableKeyException: if the key cannot be recovered (e.g., the given password is wrong).
   :return: the private key.

getPublicKey
^^^^^^^^^^^^

.. java:method:: public PublicKey getPublicKey()
   :outertype: KeyStoreManager

   Gets the managed public key.

   :return: the public key.

getX509Certificate
^^^^^^^^^^^^^^^^^^

.. java:method:: public X509Certificate getX509Certificate()
   :outertype: KeyStoreManager

   Gets the managed X509 certificate.

   :throws ClassCastException: if the certificate is not of the X509 type.
   :return: the managed X509 certificate.

getX509Certificate
^^^^^^^^^^^^^^^^^^

.. java:method:: public X509Certificate getX509Certificate(String alias)
   :outertype: KeyStoreManager

   Gets the managed X509 certificate.

   :param alias: the alias name.
   :throws ClassCastException: if the certificate is not of the X509 type.
   :return: the managed X509 certificate.

getX509CertificateChain
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public X509Certificate[] getX509CertificateChain()
   :outertype: KeyStoreManager

   Gets the managed X509 certificate chain.

   :return: the managed certificate chain.

getX509CertificateChain
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public X509Certificate[] getX509CertificateChain(String alias)
   :outertype: KeyStoreManager

   Gets the X509 certificate chain asscoiated with the given alias name.

   :param alias: the alias name.
   :return: the certificate chain.

isCertificateTrusted
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isCertificateTrusted()
   :outertype: KeyStoreManager

   Checks if the managed certificate is trusted.

   :return: true if the managed certificate is trusted.

isCertificateTrusted
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isCertificateTrusted(String alias)
   :outertype: KeyStoreManager

   Checks if the certificate asscoiated with the given alias name is trusted.

   :return: true the certificate is trusted.

