.. java:import:: java.io File

.. java:import:: java.io FileInputStream

.. java:import:: java.io FileNotFoundException

.. java:import:: java.io FileOutputStream

.. java:import:: java.io IOException

.. java:import:: java.io ObjectInputStream

.. java:import:: java.io ObjectOutputStream

.. java:import:: java.lang.reflect Constructor

.. java:import:: java.lang.reflect InvocationTargetException

.. java:import:: java.security Key

.. java:import:: java.security KeyStore

.. java:import:: java.security KeyStoreException

.. java:import:: java.security NoSuchAlgorithmException

.. java:import:: java.security NoSuchProviderException

.. java:import:: java.security Provider

.. java:import:: java.security Security

.. java:import:: java.security UnrecoverableKeyException

.. java:import:: java.security.cert Certificate

.. java:import:: java.security.cert CertificateException

.. java:import:: java.util Date

.. java:import:: java.util Enumeration

.. java:import:: java.util Hashtable

.. java:import:: java.util Vector

CompositeKeyStore
=================

.. java:package:: hk.hku.cecid.ebms.pkg.pki
   :noindex:

.. java:type:: public class CompositeKeyStore

   Composite keystore which manages keystores of different types. A typical Java keystore supports only one keystore type per file. That will be inconvenient for applications to manage several types of keystore. Also, this composite keystore supports managing multiple keystore files. This can be viewed as a keystore registry, that is, this object manages a pool of keystore files.

   :author: kcyee

Fields
------
cache
^^^^^

.. java:field:: protected Hashtable cache
   :outertype: CompositeKeyStore

   Internal storage of the aliases inside the keystore file

keystores
^^^^^^^^^

.. java:field:: protected Vector keystores
   :outertype: CompositeKeyStore

   Internal storage of the keystore object

storage
^^^^^^^

.. java:field:: protected Hashtable storage
   :outertype: CompositeKeyStore

   Internal storage of the keystore file information

Constructors
------------
CompositeKeyStore
^^^^^^^^^^^^^^^^^

.. java:constructor:: public CompositeKeyStore()
   :outertype: CompositeKeyStore

   Default constructor. The internal variables are being initialized.

Methods
-------
addKeyStoreFile
^^^^^^^^^^^^^^^

.. java:method:: public void addKeyStoreFile(String keyFile, String type, char[] password)
   :outertype: CompositeKeyStore

   Adds a keystore file to the keystore management pool.

   :param keyFile: the name of the keystore file
   :param type: the type of the keystore
   :param password: the password for accessing the keystore

addKeyStoreFile
^^^^^^^^^^^^^^^

.. java:method:: protected void addKeyStoreFile(File keyFile, String type, char[] password)
   :outertype: CompositeKeyStore

   Adds a keystore file to the keystore management pool.

   :param keyFile: the keystore file
   :param type: the type of the keystore
   :param password: the password for accessing the keystore

aliases
^^^^^^^

.. java:method:: public Enumeration aliases()
   :outertype: CompositeKeyStore

   Gets all the aliases of the keystores pointed by this composite keystore.

   :return: an enumeration of string, holding the aliases of the keys

containsAlias
^^^^^^^^^^^^^

.. java:method:: public boolean containsAlias(String alias)
   :outertype: CompositeKeyStore

   Determines whether a given alias exists in one of the keystores pointed by this composite keystore or not.

   :param alias: the alias of the key/certificate
   :return: true if the alias exists in one of the keystores, false & otherwise

getCertificate
^^^^^^^^^^^^^^

.. java:method:: public Certificate getCertificate(String alias) throws KeyStoreException
   :outertype: CompositeKeyStore

   Gets the certificate named by the given alias, from the collection of keystores pointed by this composite keystore.

   :param alias: the alias of the key/certificate
   :throws KeyStoreException: the keystore is corrupted
   :return: the certificate named by the given alias, null if not found

getCertificateAlias
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getCertificateAlias(Certificate cert)
   :outertype: CompositeKeyStore

   Gets the alias of the specified certificate.

   :param cert: the certificate
   :return: the alias of the certificate, if the certificate can be found in the collection of keystores pointed by this composite keystore. Otherwise, null will be returned

getCertificateChain
^^^^^^^^^^^^^^^^^^^

.. java:method:: public Certificate[] getCertificateChain(String alias) throws KeyStoreException
   :outertype: CompositeKeyStore

   Gets the certificate chain by the specified alias.

   :param alias: the alias of the key/certificate
   :throws KeyStoreException: the keystore is corrupted
   :return: the certificate chain by the specified alias, null if not found

getCreationDate
^^^^^^^^^^^^^^^

.. java:method:: public Date getCreationDate(String alias) throws KeyStoreException
   :outertype: CompositeKeyStore

   Gets the creation date of the key/certificate by the specified alias.

   :param alias: the alias of the key/certificate
   :throws KeyStoreException: the keystore is corrupted
   :return: the creation date of the key/certificate by the specified alias, null if not found

getKey
^^^^^^

.. java:method:: public Key getKey(String alias, char[] password) throws KeyStoreException, NoSuchAlgorithmException, UnrecoverableKeyException
   :outertype: CompositeKeyStore

   Gets the key by the specified alias. A password should be given also to retrieve the key.

   :param alias: the alias of the key/certificate
   :param password: the password to retrieve the key
   :throws KeyStoreException: the keystore is corrupted
   :throws NoSuchAlgorithmException: the keystore cannot be read
   :throws UnrecoverableKeyException: the keystore cannot be read
   :return: the key specified by the alias, null if not found

getKeyStore
^^^^^^^^^^^

.. java:method:: public KeyStore getKeyStore()
   :outertype: CompositeKeyStore

   Gets the first KeyStore object from the keystore management pool.

   :return: the first KeyStore object from the keystore management pool

isCertificateEntry
^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isCertificateEntry(String alias) throws KeyStoreException
   :outertype: CompositeKeyStore

   Determines whether the specified alias is specifying a certificate or not.

   :param alias: the alias of the key/certificate
   :throws KeyStoreException: the keystore is corrupted

isKeyEntry
^^^^^^^^^^

.. java:method:: public boolean isKeyEntry(String alias) throws KeyStoreException
   :outertype: CompositeKeyStore

   Determines whether the specified alias is specifying a key or not.

   :param alias: the alias of the key/certificate
   :throws KeyStoreException: the keystore is corrupted

load
^^^^

.. java:method:: public void load(String storeFileName) throws InitializationException
   :outertype: CompositeKeyStore

   Loads the composite keystore from a persistent file in the file system.

   :param storeFileName: the name of the composite keystore persistent file
   :throws InitializationException: the persistent file is corrupted

load
^^^^

.. java:method:: public void load(File storeFile) throws InitializationException
   :outertype: CompositeKeyStore

   Loads the composite keystore from a persistent file in the file system.

   :param storeFile: the composite keystore persistent file
   :throws InitializationException: the persistent file is corrupted

loadCache
^^^^^^^^^

.. java:method:: protected void loadCache()
   :outertype: CompositeKeyStore

   Loads the keystores pointed by this composite keystore into memory and create a caching of aliases.

loadKeyStore
^^^^^^^^^^^^

.. java:method:: protected KeyStore loadKeyStore(String fileName, KeyStoreFileProp ksp)
   :outertype: CompositeKeyStore

   Gets an instance of the keystore of correct type. This function will consider the Java version and determine whether to use JSSE or not. For Java version 1.4 or above, JSSE is built in. So, no need to call an external provider to create an instance of PKCS#12 formatted keystore. Otherwise, JSSE should be used, and we make use of dynamic binding to load the JSSE library.

   :param fileName: the keystore file name to load
   :param ksp: other keystore parameters for loading
   :return: keystore instance of the correct type

removeKeyStoreFile
^^^^^^^^^^^^^^^^^^

.. java:method:: public void removeKeyStoreFile(String keyFile)
   :outertype: CompositeKeyStore

   Removes a keystore file from the keystore management pool.

   :param keyFile: the name of the keystore file

removeKeyStoreFile
^^^^^^^^^^^^^^^^^^

.. java:method:: protected void removeKeyStoreFile(File keyFile)
   :outertype: CompositeKeyStore

   Removes a keystore file from the keystore management pool.

   :param keyFile: the keystore file

size
^^^^

.. java:method:: public int size()
   :outertype: CompositeKeyStore

   Gets the total number of keys/certificates in all the keystores pointed by this composite keystore.

   :return: the total number of keys/certificates

store
^^^^^

.. java:method:: public void store(String storeFileName) throws StoreException
   :outertype: CompositeKeyStore

   Stores the composite keystore to a persistent file in the file system.

   :param storeFileName: the name of the composite keystore persistent file
   :throws StoreException: the composite keystore is not successfully stored

store
^^^^^

.. java:method:: public void store(File storeFile) throws StoreException
   :outertype: CompositeKeyStore

   Stores the composite keystore to a persistent file in the file system.

   :param storeFile: the composite keystore persistent file
   :throws StoreException: the composite keystore is not successfully stored

