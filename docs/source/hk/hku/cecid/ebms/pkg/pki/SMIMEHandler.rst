.. java:import:: java.security Security

.. java:import:: javax.activation CommandMap

.. java:import:: javax.activation MailcapCommandMap

.. java:import:: org.bouncycastle.jce.provider BouncyCastleProvider

SMIMEHandler
============

.. java:package:: hk.hku.cecid.ebms.pkg.pki
   :noindex:

.. java:type:: public class SMIMEHandler

   It is the base class of SMIMEEncrypter and SMIMEDecrypter. The BouncyCastle 's SMIME engine only works properly with BouncyCastle 's JCE provider. The subclass should call the method initiate(), which add the BouncyCastle 's Provider and setup which DataHandler for what types of content type.

Methods
-------
initiate
^^^^^^^^

.. java:method:: static void initiate()
   :outertype: SMIMEHandler

   Add the BouncyCastle 's Provider and setup which DataHandler for what types of content type.

