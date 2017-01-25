.. java:import:: java.io Serializable

KeyStoreFileProp
================

.. java:package:: hk.hku.cecid.ebms.pkg.pki
   :noindex:

.. java:type:: public class KeyStoreFileProp implements Serializable

   This class represents the data structure for holding parameters for accessing a keystore file. Since the parameters will be serialized to the file system, some fields (particularly password will be scrambled.

   :author: kcyee

Fields
------
password
^^^^^^^^

.. java:field:: protected char[] password
   :outertype: KeyStoreFileProp

   Internal storage for the keystore password

type
^^^^

.. java:field:: protected String type
   :outertype: KeyStoreFileProp

   Internal storage for the keystore type

Constructors
------------
KeyStoreFileProp
^^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreFileProp(String type, char[] password)
   :outertype: KeyStoreFileProp

   Constructor that initializes the object with keystore parameters

   :param type: the keystore type
   :param password: the keystore password

Methods
-------
decrypt
^^^^^^^

.. java:method:: protected char[] decrypt(char[] password)
   :outertype: KeyStoreFileProp

   Decrypts the password. This is a helper function called internally to unscramble the password from storage.

   :param password: the text to be decrypted
   :return: the decrypted password

encrypt
^^^^^^^

.. java:method:: protected char[] encrypt(char[] password)
   :outertype: KeyStoreFileProp

   Encrypts the password. This is a helper function called internally to scramble the password for storage.

   :param password: the password to be encrypted
   :return: the encrypted text

getPassword
^^^^^^^^^^^

.. java:method:: public char[] getPassword()
   :outertype: KeyStoreFileProp

   Gets the keystore password

   :return: the keystore password

getType
^^^^^^^

.. java:method:: public String getType()
   :outertype: KeyStoreFileProp

   Gets the keystore type

   :return: the keystore type

