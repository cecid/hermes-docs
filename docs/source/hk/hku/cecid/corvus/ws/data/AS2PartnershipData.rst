AS2PartnershipData
==================

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class AS2PartnershipData extends KVPairData

   The \ ``AS2PartnershipData``\  is

   :author: Twinsen Tsang

Fields
------
ALG_ENCRYPT_3DES
^^^^^^^^^^^^^^^^

.. java:field:: public static final String ALG_ENCRYPT_3DES
   :outertype: AS2PartnershipData

   The constant field for 3DES Encryption.

ALG_ENCRYPT_RC2
^^^^^^^^^^^^^^^

.. java:field:: public static final String ALG_ENCRYPT_RC2
   :outertype: AS2PartnershipData

   The constant field for RC2 Encryption.

ALG_MIC_MD5
^^^^^^^^^^^

.. java:field:: public static final String ALG_MIC_MD5
   :outertype: AS2PartnershipData

   The constant field for MD5 Message-Integrity-Check.

ALG_MIC_SHA1
^^^^^^^^^^^^

.. java:field:: public static final String ALG_MIC_SHA1
   :outertype: AS2PartnershipData

   The constant field for SHA1 Message-Integrity-Check.

ALG_SIGN_MD5
^^^^^^^^^^^^

.. java:field:: public static final String ALG_SIGN_MD5
   :outertype: AS2PartnershipData

   The constant field for MD5 Signing.

ALG_SIGN_SHA1
^^^^^^^^^^^^^

.. java:field:: public static final String ALG_SIGN_SHA1
   :outertype: AS2PartnershipData

   The constant field for SHA1 Signing.

PARAM_CLASS_SET
^^^^^^^^^^^^^^^

.. java:field:: static final Class[] PARAM_CLASS_SET
   :outertype: AS2PartnershipData

PARAM_KEY_SET
^^^^^^^^^^^^^

.. java:field:: public static final String[] PARAM_KEY_SET
   :outertype: AS2PartnershipData

   This is the key set for XML serialization / de-serialization.

PARAM_PREFIX
^^^^^^^^^^^^

.. java:field:: public static final String PARAM_PREFIX
   :outertype: AS2PartnershipData

   This is the parameters prefix for serialization / de-serialization.

Constructors
------------
AS2PartnershipData
^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AS2PartnershipData()
   :outertype: AS2PartnershipData

   Default Constructor.

Methods
-------
getAS2From
^^^^^^^^^^

.. java:method:: public String getAS2From()
   :outertype: AS2PartnershipData

   :return: AS2 From.

getAs2To
^^^^^^^^

.. java:method:: public String getAs2To()
   :outertype: AS2PartnershipData

   :return: AS2 To.

getEncryptAlgorithm
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getEncryptAlgorithm()
   :outertype: AS2PartnershipData

   :return: encrpytion algorithm.

getEncryptCert
^^^^^^^^^^^^^^

.. java:method:: public byte[] getEncryptCert()
   :outertype: AS2PartnershipData

   :return: encryption certificate in byte array.

getMicAlgorithm
^^^^^^^^^^^^^^^

.. java:method:: public String getMicAlgorithm()
   :outertype: AS2PartnershipData

   :return: checksum algorithm.

getPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public String getPartnershipId()
   :outertype: AS2PartnershipData

   :return: The partnership id for this partnership.

getReceiptAddress
^^^^^^^^^^^^^^^^^

.. java:method:: public String getReceiptAddress()
   :outertype: AS2PartnershipData

   :return: Get receipt address.

getRecipientAddress
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getRecipientAddress()
   :outertype: AS2PartnershipData

   :return: Get recipient address of the message.

getRetries
^^^^^^^^^^

.. java:method:: public int getRetries()
   :outertype: AS2PartnershipData

   :return: retries.

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public int getRetryInterval()
   :outertype: AS2PartnershipData

   :return: retry interval.

getSignAlgorithm
^^^^^^^^^^^^^^^^

.. java:method:: public String getSignAlgorithm()
   :outertype: AS2PartnershipData

   :return: signing algorithm.

getSubject
^^^^^^^^^^

.. java:method:: public String getSubject()
   :outertype: AS2PartnershipData

   :return: Get the subject of the message.

getVerifyCert
^^^^^^^^^^^^^

.. java:method:: public byte[] getVerifyCert()
   :outertype: AS2PartnershipData

   :return: verification certificate in byte array.

isDisabled
^^^^^^^^^^

.. java:method:: public boolean isDisabled()
   :outertype: AS2PartnershipData

   :return: the partnership is disabled ?

isHostnameVerified
^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isHostnameVerified()
   :outertype: AS2PartnershipData

   :return: True if hostname is verified.

isInboundEncryptRequired
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isInboundEncryptRequired()
   :outertype: AS2PartnershipData

   :return: true if inbound encryption is required.

isInboundSignRequired
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isInboundSignRequired()
   :outertype: AS2PartnershipData

   :return: true if inbound signing is required.

isOutboundCompressRequired
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isOutboundCompressRequired()
   :outertype: AS2PartnershipData

   :return: true if outbound compression is required.

isOutboundEncryptRequired
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isOutboundEncryptRequired()
   :outertype: AS2PartnershipData

   :return: true if outbound encryption is required.

isOutboundSignRequired
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isOutboundSignRequired()
   :outertype: AS2PartnershipData

   :return: True if outbound signing is required.

isReceiptRequired
^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isReceiptRequired()
   :outertype: AS2PartnershipData

   :return: True if receipt required.

isReceiptSignRequired
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isReceiptSignRequired()
   :outertype: AS2PartnershipData

   :return: true if receipt signing is required.

isSyncReply
^^^^^^^^^^^

.. java:method:: public boolean isSyncReply()
   :outertype: AS2PartnershipData

   :return: the message required sync reply

setAs2From
^^^^^^^^^^

.. java:method:: public void setAs2From(String as2From)
   :outertype: AS2PartnershipData

   :param as2From: AS2 From.

setAs2To
^^^^^^^^

.. java:method:: public void setAs2To(String as2To)
   :outertype: AS2PartnershipData

   :param as2To: AS2 To.

setEncryptAlgorithm
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setEncryptAlgorithm(String encryptAlgorithm)
   :outertype: AS2PartnershipData

   :param encryptAlgorithm: encryption algorithm.

setEncryptCert
^^^^^^^^^^^^^^

.. java:method:: public void setEncryptCert(byte[] encryptCert)
   :outertype: AS2PartnershipData

   :param encryptCert: encryption certificate in byte array.

setIsDisabled
^^^^^^^^^^^^^

.. java:method:: public void setIsDisabled(boolean isDisabled)
   :outertype: AS2PartnershipData

   Set the partnership is enabled or not.

   :param isDisabled: the flag whether the partnership is enabled or not.

setIsHostnameVerified
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsHostnameVerified(boolean isHostnameVerified)
   :outertype: AS2PartnershipData

   :param isHostnameVerified: true if the hostname is verified.

setIsInboundEncryptRequired
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsInboundEncryptRequired(boolean isInboundEncryptRequired)
   :outertype: AS2PartnershipData

   :param isInboundEncryptRequired: true if inbound encrpytion is required.

setIsInboundSignRequired
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsInboundSignRequired(boolean isInboundSignRequired)
   :outertype: AS2PartnershipData

   :param isInboundSignRequired: true if inbound signing is required.

setIsOutboundCompressRequired
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsOutboundCompressRequired(boolean isOutboundCompressRequired)
   :outertype: AS2PartnershipData

   :param isOutboundCompressRequired: true if outbound compression is required.

setIsOutboundEncryptRequired
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsOutboundEncryptRequired(boolean isOutboundEncryptRequired)
   :outertype: AS2PartnershipData

   :param isOutboundEncryptRequired: true if outbound encryption is required.

setIsOutboundSignRequired
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsOutboundSignRequired(boolean isOutboundSignRequired)
   :outertype: AS2PartnershipData

   :param isOutboundSignRequired: true if outbound signing is required.

setIsReceiptRequired
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsReceiptRequired(boolean isReceiptRequired)
   :outertype: AS2PartnershipData

   :param isReceiptRequired: true if receipt required.

setIsReceiptSignRequired
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsReceiptSignRequired(boolean isReceiptSignRequired)
   :outertype: AS2PartnershipData

   :param isReceiptSignRequired: true if receipt signing is required.

setIsSyncReply
^^^^^^^^^^^^^^

.. java:method:: public void setIsSyncReply(boolean isSyncReply)
   :outertype: AS2PartnershipData

   Set the message require sync reply

   :param isSyncReply:

setMicAlgorithm
^^^^^^^^^^^^^^^

.. java:method:: public void setMicAlgorithm(String micAlgorithm)
   :outertype: AS2PartnershipData

   :param micAlgorithm: checksum algorithm.

setPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public void setPartnershipId(String partnershipId)
   :outertype: AS2PartnershipData

   :param partnershipId: The partnership id for this partnership.

setReceiptAddress
^^^^^^^^^^^^^^^^^

.. java:method:: public void setReceiptAddress(String receiptAddress)
   :outertype: AS2PartnershipData

   :param receiptAddress: the receipt address

setRecipientAddress
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setRecipientAddress(String recipientAddress)
   :outertype: AS2PartnershipData

   :param recipientAddress: the recipient address of the message.

setRetries
^^^^^^^^^^

.. java:method:: public void setRetries(int retries)
   :outertype: AS2PartnershipData

   :param retries: Retries.

setRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public void setRetryInterval(int retryInterval)
   :outertype: AS2PartnershipData

   :param retryInterval: retries interval.

setSignAlgorithm
^^^^^^^^^^^^^^^^

.. java:method:: public void setSignAlgorithm(String signAlgorithm)
   :outertype: AS2PartnershipData

   :param signAlgorithm: signing algorithm.

setSubject
^^^^^^^^^^

.. java:method:: public void setSubject(String subject)
   :outertype: AS2PartnershipData

   :param subject: the subject of the message.

setVerifyCert
^^^^^^^^^^^^^

.. java:method:: public void setVerifyCert(byte[] verifyCert)
   :outertype: AS2PartnershipData

   :param verifyCert: verification certificate in byte array.

