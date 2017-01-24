Configuration for Message Signing and Secure Channels
=====================================================
Introduction
------------
Under the current implementation, Hermes 2 only supports the PKCS #12 standard. A keystore is needed for Hermes 2 to retrieve a key for message signing.
There is a keystore created for both ebMS and AS2 plugins during installation.
To learn more about PKI, please refer to the `Wikipedia article <https://en.wikipedia.org/wiki/Public_key_infrastructure>`_ or `this article <http://searchsecurity.techtarget.com/definition/PKI>`_.


Configuration to enable message signing
---------------------------------------
By default, the Hermes 2 installer creates a keystore for both ebMS and AS2 plugins. You can use the keystores provided, or create your own customized keystore.
For information about how to create a keystore and generate a public certificate, please refer to the section `How to generate a PKCS12 Keystore and Certificate`_.


Core module configuration
^^^^^^^^^^^^^^^^^^^^^^^^^
The configurations for keystores are defined in the system module configuration files. The component named ``keystore-manager`` determines the details of the keystore.
   
   * AS2: :file:`as2.module.core.xml`
   * ebMS: :file:`ebms.module.core.xml`

Here are descriptions of the ``keystore-manager`` parameters:

+------------------------+----------------------------------------------------------------------------------------------+
| ``keystore-location``  | Where the keystore file can be found. There is a small difference between ebMS and AS2.      |
|                        | In AS2, the keystore file is located in the :file:`security` folder of the plugin and        |
|                        | only the filename of the keystore needs to be specified. In ebMS, an absolute path           |
|                        | is required for this field.                                                                  |
+------------------------+----------------------------------------------------------------------------------------------+
| ``keystore-password``  | The password to access the keystore file.                                                    |
+------------------------+----------------------------------------------------------------------------------------------+
| ``key-alias``          | This value identifies the key in the keystore that will be used for signing.                 |
+------------------------+----------------------------------------------------------------------------------------------+
| ``key-password``       | The password to access the private key (usually the same as the keystore password).          |
+------------------------+----------------------------------------------------------------------------------------------+
| ``keystore-type``      | The type of keystore. Currently, Hermes 2 only supports PKCS12.                              |
+------------------------+----------------------------------------------------------------------------------------------+
| ``keystore-provider``  | The class provider to handle the keystore. By default, it is                                 |
|                        | ``org.bouncycastle.jce.provider.BouncyCastleProvider``.                                      |
+------------------------+----------------------------------------------------------------------------------------------+


Partnership settings for receiver
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
The receiver needs to upload the public certificate provided by the sender in order to be able to verify the signature. This will be done using the partnership maintenance page.

.. image:: /_static/images/message_signing/partnership_cert_upload.png

The value of :guilabel:`Signing Required` must be set to ``true``. For details on partnership settings, please see :doc:`ebms_partnership` or :doc:`as2_partnership`.

.. image:: /_static/images/message_signing/partnership_ssl_setting.png


.. _send-message-using-https:

How to send messages using HTTPS
--------------------------------
SSL server authentication
^^^^^^^^^^^^^^^^^^^^^^^^^
To enable server authentication in Tomcat, a truststore and a keystore have to be configured in Hermes 2 and Tomcat respectively.

On the sending side, a truststore is defined in :file:`corvus.properties.xml`, which is where the certificates of trusted servers are stored.
When the sending Hermes 2 tries to establish a secure connection, the receiving Hermes 2 will provide a public certificate for the sender to identify their identity.
If this certificate is self-signed, it should be added to the truststore defined on the sending side.

On the receiving side, a keystore is defined in the :file:`server.xml` of Tomcat. The keystore contains its paired private key and public certificate.
If the keystore is self-signed, the certificate has to be exported, then imported to the trustore of the sending Hermes 2.

The details of this procedure are shown below.
For information about how to create a keystore and generate a public certificate, please refer to the section `How to generate a PKCS12 Keystore and Certificate`_.


Receiver configuration
""""""""""""""""""""""
Once a keystore has been created, :file:`server.xml` needs to be modified to specify the keystore parameters.
   
   #. Uncomment the connector definition on port ``8443``.
   #. Add the following attributes for keystore configuration.

+--------------------+--------------------------------------------------------------------------------------------------------------+
| ``keystoreFile``   | An absolute file path to the keystore file.                                                                  |
+--------------------+--------------------------------------------------------------------------------------------------------------+
| ``keystorePass``   | The password to access the keystore.                                                                         |
+--------------------+--------------------------------------------------------------------------------------------------------------+
| ``keystoreType``   | The type of keystore. Both PKCS12 and JKS are supported.                                                     |
+--------------------+--------------------------------------------------------------------------------------------------------------+
| ``keyalias``       | Optional. If the keystore contains more than one key pair, specify the target key-pair with an alias.        |
+--------------------+--------------------------------------------------------------------------------------------------------------+
| ``clientAuth``     | Set this to ``false`` to indicate only Server Authentication is needed.                                      |
+--------------------+--------------------------------------------------------------------------------------------------------------+


Sender configuration
""""""""""""""""""""
As mentioned before, a truststore needs to be configured. In this example, a JKS keystore is used as a truststore as it is much simpler to import a self-signed certificate.

If there is no keystore file found, :program:`Keytool` can be used to create a new keystore:

.. code-block:: sh

   keytool -importcert -file {filepath-and-name-of-certificate} -alias {key-alias} -keystore {filepath-and-name-of-keystore} -storetype jks -storepass {password}

The program will display the certificate information and ask for confirmation. Enter ``yes`` after verifying the details.

.. image:: /_static/images/message_signing/keytool_truststore.png

Open :file:`corvus.properties.xml`. The definition of the truststore can be found under the ``environment`` component.

Here are descriptions of the parameters:

+----------------------+-----------------------------------------------------------------+
| ``trustStore``       | The absolute file path to the keystore.                         |
+----------------------+-----------------------------------------------------------------+
| ``trustStorePass``   | The password to access the keystore.                            |
+----------------------+-----------------------------------------------------------------+
| ``trustStoreType``   | The type of the keystore. Both PKCS12 and JKS are supported.    |
+----------------------+-----------------------------------------------------------------+

If asynchronous replies are enabled for the receiving partnership, the same configuration needs to be made for Hermes 2 on both sides, however the roles are reversed.


SSL client authentication
^^^^^^^^^^^^^^^^^^^^^^^^^
In addition to server authentication, client authentication can also be applied to Hermes 2 to achieve secure connections for message deliveries.

Once the server authentication is complete, the receiving Hermes 2 will ask for the identity of the sending Hermes 2.
The sender will provide a public certificate to the receiver, which will be compared to the trusted certificates in the truststore.


Receiver configuration
""""""""""""""""""""""
In order to store trusted certificates, a truststore needs to be declared in the :file:`server.xml` of Tomcat.

Here are descriptions of the attributes:

+--------------------+-------------------------------------------------------------------+
| ``keystoreFile``   | The absolute file path to the keystore.                           |
+--------------------+-------------------------------------------------------------------+
| ``keystorePass``   | The password to access the keystore.                              |
+--------------------+-------------------------------------------------------------------+
| ``keystoreType``   | The type of the keystore. Both PKCS12 and JKS are supported.      |
+--------------------+-------------------------------------------------------------------+
| ``clientAuth``     | Set this to ``true`` to enforce client authentication.            |
+--------------------+-------------------------------------------------------------------+


Sender configuration
""""""""""""""""""""
To store the private key and public certificate pair that identifies the sender, a keystore is needed.

Here are descriptions of the parameters:

+--------------------------------------+-------------------------------------------------+
| ``javax.net.ssl.keyStore``           | The absolute file path to the keystore.         |
+--------------------------------------+-------------------------------------------------+
| ``javax.net.ssl.keyStorePassword``   | The password to access the keystore.            |
+--------------------------------------+-------------------------------------------------+
| ``javax.net.ssl.keyStoreType``       | The type of the keystore.                       |
+--------------------------------------+-------------------------------------------------+


.. _generate-cert:

How to generate a PKCS12 keystore and certificate
-------------------------------------------------
To create a keystore and certificate, :program:`Keytool` or :program:`OpenSSL` can be used.


Using Keytool
^^^^^^^^^^^^^
:program:`Keytool` is provided with Java SDK.


1. Invoke ``keytool`` with parameters
"""""""""""""""""""""""""""""""""""""
.. code-block:: sh
      
   keytool -genkey -alias {key-alias} -keyalg RSA -keystore {filepath-and-name-of-keystore} -storetype pkcs12 -storepass {password} -keypass {password}
   
The same password value is used for ``keypass`` and ``storepass`` in this command.

.. image:: /_static/images/message_signing/keytool_command.png


2. Input more detailed information
""""""""""""""""""""""""""""""""""
.. image:: /_static/images/message_signing/keytool_command_detail.png

After entering the information, a keystore will be created. It can be verified using :program:`Keytool`.

.. code-block:: sh
   
   keytool -list -keystore {filepath-and-name-of-keystore} -storetype pkcs12

The password specified in the ``storepass`` attribute is needed to access the keystore.

.. image:: /_static/images/message_signing/keytool_list_keystore.png


3. Export certificate
"""""""""""""""""""""
The private key has been generated and stored in the keystore, but a public certificate is still needed for the receiver to verify signatures.

.. code-block:: sh
   
   keytool -exportcert -alias {key-alias} -keystore {filepath-and-name-of-keystore} -storetype pkcs12 -file {filepath-and-name-of-certificate}

Enter the password specified in the ``storepass`` attribute to access the keystore.

.. image:: /_static/images/message_signing/keytool_generate_certificate.png

The certificate can be verified with the following command:

.. code-block:: sh
   
   keytool -printcert -file {filepath-and-name-of-certificate}

.. image:: /_static/images/message_signing/keytool_printcert.png


Using OpenSSL
^^^^^^^^^^^^^
:program:`OpenSSL` can be found `here <https://www.openssl.org/>`_.


1. Generate private key
"""""""""""""""""""""""
Invoke ``openssl`` to enter the :program:`OpenSSL` environment, then execute the following:

.. code-block:: sh
   
   genrsa -out {filepath-and-name-of-key} {length-in-bits}

.. image:: /_static/images/message_signing/openssl_genrsa_1024.png


2. Generate certificate signing request
"""""""""""""""""""""""""""""""""""""""
.. code-block:: sh
   
   req -new -key {filepath-and-name-of-key} -out {filepath-and-name-of-signing-request}

.. image:: /_static/images/message_signing/openssl_create_csr.png


3. Generate self-signed certificate
"""""""""""""""""""""""""""""""""""
.. code-block:: sh
   
   x509 -req -days {number-of-days-valid} -in {filepath-and-name-of-signing-request} -signkey {filepath-and-name-of-key} -sha1 -out {filepath-and-name-of-certificate}

.. image:: /_static/images/message_signing/openssl_gen_cert.png


4. Export to keystore in PKCS12 format
""""""""""""""""""""""""""""""""""""""
.. code-block:: sh
   
   pkcs12 -name {key-alias} -export -in {filepath-and-name-of-certificate} -inkey {filepath-and-name-of-key} -out {filepath-and-name-of-keystore}

.. image:: /_static/images/message_signing/openssl_pkcs12.png