.. java:import:: hk.hku.cecid.piazza.commons.module Component

.. java:import:: hk.hku.cecid.piazza.commons.util Instance

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: java.io FileInputStream

.. java:import:: java.io InputStream

.. java:import:: java.security KeyStore

.. java:import:: java.security Provider

.. java:import:: java.security Security

.. java:import:: java.util Properties

KeyStoreComponent
=================

.. java:package:: hk.hku.cecid.piazza.commons.security
   :noindex:

.. java:type:: abstract class KeyStoreComponent extends Component

   KeyStoreComponent is a module component which embeds a key store.

   :author: Hugo Y. K. Lam

Fields
------
alias
^^^^^

.. java:field::  String alias
   :outertype: KeyStoreComponent

   The alias name.

keyPass
^^^^^^^

.. java:field::  char[] keyPass
   :outertype: KeyStoreComponent

   The key password

keyStore
^^^^^^^^

.. java:field::  KeyStore keyStore
   :outertype: KeyStoreComponent

   The embeded key store.

location
^^^^^^^^

.. java:field::  String location
   :outertype: KeyStoreComponent

   The key store location.

provider
^^^^^^^^

.. java:field::  Object provider
   :outertype: KeyStoreComponent

   The key store provider.

storePass
^^^^^^^^^

.. java:field::  char[] storePass
   :outertype: KeyStoreComponent

   The key store password

storeType
^^^^^^^^^

.. java:field::  String storeType
   :outertype: KeyStoreComponent

   The key store type.

Constructors
------------
KeyStoreComponent
^^^^^^^^^^^^^^^^^

.. java:constructor:: public KeyStoreComponent()
   :outertype: KeyStoreComponent

   Creates a new instance of KeyStoreComponent.

Methods
-------
init
^^^^

.. java:method:: protected void init() throws KeyStoreManagementException
   :outertype: KeyStoreComponent

   Initializes this key store component.

   Component parameters:

   ..

   * keystore-location: the key store location
   * keystore-password: the key store password
   * key-alias: the alias name
   * key-password: the key password
   * keystore-type: the key store type.
   * keystore-provider: the key store provider

   :throws KeyStoreManagementException: if unable to initialize the key store component.

   **See also:** :java:ref:`.init(String,String,String,String,String,Object)`, :java:ref:`hk.hku.cecid.piazza.commons.module.Component.init()`

init
^^^^

.. java:method:: protected void init(KeyStore keyStore, String alias, String keyPass) throws KeyStoreManagementException
   :outertype: KeyStoreComponent

   Initializes this key store component.

   :param keyStore:
   :param alias: the alias name.
   :param keyPass: the key password.
   :throws KeyStoreManagementException: if unable to initialize the key store component.

init
^^^^

.. java:method:: protected void init(String location, String storePass, String alias, String keyPass, String storeType, Object provider) throws KeyStoreManagementException
   :outertype: KeyStoreComponent

   Initializes this key store component.

   :param location: the key store location.
   :param storePass: the key store password.
   :param alias: the alias name.
   :param keyPass: the key password.
   :param storeType: the key store type.
   :param provider: the key store provider.
   :throws KeyStoreManagementException: if unable to initialize the key store component.

