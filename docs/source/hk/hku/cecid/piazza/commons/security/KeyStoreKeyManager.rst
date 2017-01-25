.. java:import:: java.net Socket

.. java:import:: java.security KeyStore

.. java:import:: java.security Principal

.. java:import:: java.security PrivateKey

.. java:import:: java.security.cert Certificate

.. java:import:: java.security.cert X509Certificate

.. java:import:: javax.net.ssl X509KeyManager

KeyStoreKeyManager
==================

.. java:package:: hk.hku.cecid.piazza.commons.security
   :noindex:

.. java:type:: public class KeyStoreKeyManager extends KeyStoreComponent implements X509KeyManager

   KeyStoreKeyManager implements javax.net.ssl.X509KeyManager, which manages a given key store of X509 certificate-based key pairs and authenticates the local side of a secure socket.

   :author: Hugo Y. K. Lam

Constructors
------------
KeyStoreKeyManager
^^^^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreKeyManager()
   :outertype: KeyStoreKeyManager

   Creates a new instance of KeyStoreKeyManager.

KeyStoreKeyManager
^^^^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreKeyManager(KeyStoreManager keyman) throws KeyStoreManagementException
   :outertype: KeyStoreKeyManager

   Creates a new instance of KeyStoreKeyManager.

   :param keyman: the key store manager used for authentication.
   :throws KeyStoreManagementException: if the specified key store manager is null.

KeyStoreKeyManager
^^^^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreKeyManager(KeyStore keyStore, String alias, String password) throws KeyStoreManagementException
   :outertype: KeyStoreKeyManager

   Creates a new instance of KeyStoreKeyManager.

   :param keyStore: the initialized key store used for authentication.
   :param alias: the alias name associated with the key.
   :param password: the key password.
   :throws KeyStoreManagementException: if the specified key store is null.

Methods
-------
chooseClientAlias
^^^^^^^^^^^^^^^^^

.. java:method:: public String chooseClientAlias(String[] keyType, Principal[] issuers, Socket socket)
   :outertype: KeyStoreKeyManager

   Chooses an alias to authenticate the client side of a secure socket. This method always returns the predefined alias.

   :param keyType: the key algorithm type name(s), ordered with the most-preferred key type first.
   :param issuers: the list of acceptable CA issuer subject names or null if it does not matter which issuers are used.
   :param socket: the socket to be used for this connection or null.
   :return: the alias name.

   **See also:** :java:ref:`javax.net.ssl.X509KeyManager.chooseClientAlias(java.lang.String[],java.security.Principal[],java.net.Socket)`

chooseServerAlias
^^^^^^^^^^^^^^^^^

.. java:method:: public String chooseServerAlias(String keyType, Principal[] issuers, Socket socket)
   :outertype: KeyStoreKeyManager

   Chooses an alias to authenticate the server side of a secure socket. This method always returns the predefined alias.

   :param keyType: the key algorithm type name.
   :param issuers: the list of acceptable CA issuer subject names or null if it does not matter which issuers are used.
   :param socket: the socket to be used for this connection or null.
   :return: the alias name.

   **See also:** :java:ref:`javax.net.ssl.X509KeyManager.chooseServerAlias(java.lang.String,java.security.Principal[],java.net.Socket)`

getCertificateChain
^^^^^^^^^^^^^^^^^^^

.. java:method:: public X509Certificate[] getCertificateChain(String alias)
   :outertype: KeyStoreKeyManager

   Gets the certificate chain associated with the given alias.

   :param alias: the alias name.
   :return: the certificate chain.

   **See also:** :java:ref:`javax.net.ssl.X509KeyManager.getCertificateChain(java.lang.String)`

getClientAliases
^^^^^^^^^^^^^^^^

.. java:method:: public String[] getClientAliases(String keyType, Principal[] issuers)
   :outertype: KeyStoreKeyManager

   Gets the aliases for authenticating the client side of a secure socket. This method always returns the predefined alias.

   :param keyType: the key algorithm type name.
   :param issuers: the list of acceptable CA issuer subject names or null if it does not matter which issuers are used.
   :return: the aliases for authenticating the client side of a secure socket.

   **See also:** :java:ref:`javax.net.ssl.X509KeyManager.getClientAliases(java.lang.String,java.security.Principal[])`

getPrivateKey
^^^^^^^^^^^^^

.. java:method:: public PrivateKey getPrivateKey(String alias)
   :outertype: KeyStoreKeyManager

   Gets the key associated with the given alias.

   :param alias: the alias name.
   :throws RuntimeException: if unable to retrieve the private key.
   :return: the private key.

   **See also:** :java:ref:`javax.net.ssl.X509KeyManager.getPrivateKey(java.lang.String)`

getServerAliases
^^^^^^^^^^^^^^^^

.. java:method:: public String[] getServerAliases(String keyType, Principal[] issuers)
   :outertype: KeyStoreKeyManager

   Gets the aliases for authenticating the server side of a secure socket. This method always returns the predefined alias.

   :param keyType: the key algorithm type name.
   :param issuers: the list of acceptable CA issuer subject names or null if it does not matter which issuers are used.
   :return: the aliases for authenticating the server side of a secure socket.

   **See also:** :java:ref:`javax.net.ssl.X509KeyManager.getServerAliases(java.lang.String,java.security.Principal[])`

