Configuring Secure Messaging
============================
.. _send-message-using-https:

How to send messages using HTTPS
--------------------------------
SSL server authentication
^^^^^^^^^^^^^^^^^^^^^^^^^
To enable server authentication in Tomcat, a truststore and a keystore have to be configured in Hermes and Tomcat respectively.

On the sending side, a truststore is defined in :file:`corvus.properties.xml`, which is where the certificates of trusted servers are stored.
When the sending Hermes tries to establish a secure connection, the receiving Hermes will provide a public certificate for the sender to identify their identity.
If this certificate is self-signed, it should be added to the truststore defined on the sending side.

On the receiving side, a keystore is defined in the :file:`server.xml` of Tomcat. The keystore contains its paired private key and public certificate.
If the keystore is self-signed, the certificate has to be exported, then imported to the trustore of the sending Hermes.

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

If asynchronous replies are enabled for the receiving partnership, the same configuration needs to be made for Hermes on both sides, however the roles are reversed.


SSL client authentication
^^^^^^^^^^^^^^^^^^^^^^^^^
In addition to server authentication, client authentication can also be applied to Hermes to achieve secure connections for message deliveries.

Once the server authentication is complete, the receiving Hermes will ask for the identity of the sending Hermes.
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


1. Invoke ``keytool`` with parameters.

   .. code-block:: sh
      
      keytool -genkey -alias {key-alias} -keyalg RSA -keystore {filepath-and-name-of-keystore} -storetype pkcs12 -storepass {password} -keypass {password}
   
   The same password value is used for ``keypass`` and ``storepass`` in this command.

   .. image:: /_static/images/message_signing/keytool_command.png


#. Input more detailed information.

   .. image:: /_static/images/message_signing/keytool_command_detail.png

   After entering the information, a keystore will be created. It can be verified using :program:`Keytool`.

   .. code-block:: sh
   
      keytool -list -keystore {filepath-and-name-of-keystore} -storetype pkcs12

   The password specified in the ``storepass`` attribute is needed to access the keystore.

   .. image:: /_static/images/message_signing/keytool_list_keystore.png


#. Export certificate.

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


1. Generate private key.

   Invoke ``openssl`` to enter the :program:`OpenSSL` environment, then execute the following:

   .. code-block:: sh
   
      genrsa -out {filepath-and-name-of-key} {length-in-bits}

   .. image:: /_static/images/message_signing/openssl_genrsa_1024.png


#. Generate certificate signing request.

   .. code-block:: sh
   
      req -new -key {filepath-and-name-of-key} -out {filepath-and-name-of-signing-request}

   .. image:: /_static/images/message_signing/openssl_create_csr.png


#. Generate self-signed certificate.

   .. code-block:: sh
   
      x509 -req -days {number-of-days-valid} -in {filepath-and-name-of-signing-request} -signkey {filepath-and-name-of-key} -sha1 -out {filepath-and-name-of-certificate}

   .. image:: /_static/images/message_signing/openssl_gen_cert.png


#. Export to keystore in PKCS12 format.

   .. code-block:: sh
   
      pkcs12 -name {key-alias} -export -in {filepath-and-name-of-certificate} -inkey {filepath-and-name-of-key} -out {filepath-and-name-of-keystore}

   .. image:: /_static/images/message_signing/openssl_pkcs12.png



.. _support-params:

Supported Parameters
--------------------
The following key pair algorithms and signature algorithms have been tested:

Key pair algorithm (``keyalg``)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

+-------------+-------------------------------------------------------------+
|``DSA``      | Generates keypairs for the Digital Signature Algorithm      |
+-------------+-------------------------------------------------------------+
|``RSA`` [1]_ | Generates keypairs for the RSA algorithm (Signature/Cipher) |
+-------------+-------------------------------------------------------------+

.. [1] ``RSA`` has been test with ``keysize=`` 1024, 2048, 4096.

Signature algorithm (``sigalg``)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

+------------------+---------------------------------------------------------------+
|``SHA1withRSA``   | The signature algorithm with SHA-* and the RSA encryption     |
+------------------+ algorithm as defined in the OSI Interoperability Workship,    |
|``SHA256withRSA`` | using the padding conversions described in PKCS1.             |
+------------------+                                                               |
|``SHA512withRSA`` |                                                               |
+------------------+---------------------------------------------------------------+
|``MD5withRSA``    | The MD2/MD5 with RSA encryption algorithm which users the     |
+------------------+ MD2/MD5 digest algorithm and RSA to cread and verify RSA      |
|``MD2withRSA``    | digital signatures as defined in PKCS1.                       |
+------------------+---------------------------------------------------------------+
|``SHA1withDSA``   | The DSA with SHA-1 signature algorithm which uses the         |
|                  | SHA-1 digest algorithm and DSA to create and verify DSA       |
|             	   | digital signatures as defined in FIPS PUB 186.                |
+------------------+---------------------------------------------------------------+


Parameter combinations
^^^^^^^^^^^^^^^^^^^^^^
The following combinations of algorithms and parameters have been tested with ebMS and AS2:

ebMS
""""

+------------------------+-----------------------------------------------+-----------------------------------------------+
| tool                   | Keytool                                       | OpenSSL                                       |
+------------------------+---------------+---------------+---------------+---------------+---------------+---------------+
| keysize                | 1024          | 2048          | 4096          | 1024          | 2048          | 4096          |
+===========+============+===============+===============+===============+===============+===============+===============+
| ``RSA``   | ``SHA1``   | ok            | ok            | ok            | ok            | ok            | ok            |
|           +------------+---------------+---------------+---------------+---------------+---------------+---------------+
|           | ``SHA256`` | ok            | ok            | ok            | ok            | ok            | ok            |
|           +------------+---------------+---------------+---------------+---------------+---------------+---------------+
|           | ``MD5``    | ok            | ok            | ok            | ok            | ok            | ok            |
|           +------------+---------------+---------------+---------------+---------------+---------------+---------------+
|           | ``SHA512`` | not supported | ok            | not supported | not supported | ok            | not supported |
|           +------------+---------------+---------------+---------------+---------------+---------------+---------------+
|           | ``MD2``    | not supported | ok            | not supported | not supported | not supported | not supported |
+-----------+------------+---------------+---------------+---------------+---------------+---------------+---------------+
| ``DSA``   | ``SHA1``   | ok            | not supported | not supported | ok            | not supported | not supported |
+-----------+------------+---------------+---------------+---------------+---------------+---------------+---------------+

AS2
"""

+------------------------+-----------------------------------------------+-----------------------------------------------+
| tool                   | Keytool                                       | OpenSSL                                       |
+------------------------+---------------+---------------+---------------+---------------+---------------+---------------+
| keysize                | 1024          | 2048          | 4096          | 1024          | 2048          | 4096          |
+===========+============+===============+===============+===============+===============+===============+===============+
| ``RSA``   | ``SHA1``   | ok            | ok            | ok            | ok            | ok            | ok            |
|           +------------+---------------+---------------+---------------+---------------+---------------+---------------+
|           | ``SHA256`` | ok            | ok            | ok            | ok            | ok            | ok            |
|           +------------+---------------+---------------+---------------+---------------+---------------+---------------+
|           | ``MD5``    | ok            | ok            | ok            | ok            | ok            | not supported |
|           +------------+---------------+---------------+---------------+---------------+---------------+---------------+
|           | ``SHA512`` | not supported | ok            | not supported | not supported | ok            | not supported |
|           +------------+---------------+---------------+---------------+---------------+---------------+---------------+
|           | ``MD2``    | not supported | ok            | not supported | not supported | not supported | not supported |
+-----------+------------+---------------+---------------+---------------+---------------+---------------+---------------+
| ``DSA``   | ``SHA1``   | not supported | not supported | not supported | not supported | not supported | not supported |
+-----------+------------+---------------+---------------+---------------+---------------+---------------+---------------+

See also
--------
*  :ref:`configuration-for-secure-messaging`
* `Wiki Public Key Infrastructure (Wiki) <https://en.wikipedia.org/wiki/Public_key_infrastructure>`_
* `Public Key Infrastructure (FreeMagazine) <http://searchsecurity.techtarget.com/definition/PKI>`_
