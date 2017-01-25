.. java:import:: java.security.cert X509Certificate

.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

PartnershipDVO
==============

.. java:package:: hk.hku.cecid.edi.as2.dao
   :noindex:

.. java:type:: public interface PartnershipDVO extends DVO

   :author: Donahue Sze

Fields
------
ALG_ENCRYPT_3DES
^^^^^^^^^^^^^^^^

.. java:field:: public static final String ALG_ENCRYPT_3DES
   :outertype: PartnershipDVO

ALG_ENCRYPT_RC2
^^^^^^^^^^^^^^^

.. java:field:: public static final String ALG_ENCRYPT_RC2
   :outertype: PartnershipDVO

ALG_MIC_MD5
^^^^^^^^^^^

.. java:field:: public static final String ALG_MIC_MD5
   :outertype: PartnershipDVO

ALG_MIC_SHA1
^^^^^^^^^^^^

.. java:field:: public static final String ALG_MIC_SHA1
   :outertype: PartnershipDVO

ALG_SIGN_MD5
^^^^^^^^^^^^

.. java:field:: public static final String ALG_SIGN_MD5
   :outertype: PartnershipDVO

ALG_SIGN_SHA1
^^^^^^^^^^^^^

.. java:field:: public static final String ALG_SIGN_SHA1
   :outertype: PartnershipDVO

Methods
-------
getAS2From
^^^^^^^^^^

.. java:method:: public String getAS2From()
   :outertype: PartnershipDVO

getAs2To
^^^^^^^^

.. java:method:: public String getAs2To()
   :outertype: PartnershipDVO

getEffectiveVerifyCertificate
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public X509Certificate getEffectiveVerifyCertificate()
   :outertype: PartnershipDVO

getEncryptAlgorithm
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getEncryptAlgorithm()
   :outertype: PartnershipDVO

getEncryptCert
^^^^^^^^^^^^^^

.. java:method:: public byte[] getEncryptCert()
   :outertype: PartnershipDVO

getEncryptX509Certificate
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public X509Certificate getEncryptX509Certificate()
   :outertype: PartnershipDVO

getMicAlgorithm
^^^^^^^^^^^^^^^

.. java:method:: public String getMicAlgorithm()
   :outertype: PartnershipDVO

getPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public String getPartnershipId()
   :outertype: PartnershipDVO

getReceiptAddress
^^^^^^^^^^^^^^^^^

.. java:method:: public String getReceiptAddress()
   :outertype: PartnershipDVO

getRecipientAddress
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getRecipientAddress()
   :outertype: PartnershipDVO

getRetries
^^^^^^^^^^

.. java:method:: public int getRetries()
   :outertype: PartnershipDVO

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public int getRetryInterval()
   :outertype: PartnershipDVO

getSignAlgorithm
^^^^^^^^^^^^^^^^

.. java:method:: public String getSignAlgorithm()
   :outertype: PartnershipDVO

getSubject
^^^^^^^^^^

.. java:method:: public String getSubject()
   :outertype: PartnershipDVO

getVerifyCert
^^^^^^^^^^^^^

.. java:method:: public byte[] getVerifyCert()
   :outertype: PartnershipDVO

getVerifyX509Certificate
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public X509Certificate getVerifyX509Certificate()
   :outertype: PartnershipDVO

isDisabled
^^^^^^^^^^

.. java:method:: public boolean isDisabled()
   :outertype: PartnershipDVO

isHostnameVerified
^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isHostnameVerified()
   :outertype: PartnershipDVO

isInboundEncryptRequired
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isInboundEncryptRequired()
   :outertype: PartnershipDVO

isInboundSignRequired
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isInboundSignRequired()
   :outertype: PartnershipDVO

isOutboundCompressRequired
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isOutboundCompressRequired()
   :outertype: PartnershipDVO

isOutboundEncryptRequired
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isOutboundEncryptRequired()
   :outertype: PartnershipDVO

isOutboundSignRequired
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isOutboundSignRequired()
   :outertype: PartnershipDVO

isReceiptRequired
^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isReceiptRequired()
   :outertype: PartnershipDVO

isReceiptSignRequired
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isReceiptSignRequired()
   :outertype: PartnershipDVO

isSyncReply
^^^^^^^^^^^

.. java:method:: public boolean isSyncReply()
   :outertype: PartnershipDVO

setAs2From
^^^^^^^^^^

.. java:method:: public void setAs2From(String as2From)
   :outertype: PartnershipDVO

setAs2To
^^^^^^^^

.. java:method:: public void setAs2To(String as2To)
   :outertype: PartnershipDVO

setEncryptAlgorithm
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setEncryptAlgorithm(String encryptAlgorithm)
   :outertype: PartnershipDVO

setEncryptCert
^^^^^^^^^^^^^^

.. java:method:: public void setEncryptCert(byte[] encryptCert)
   :outertype: PartnershipDVO

setIsDisabled
^^^^^^^^^^^^^

.. java:method:: public void setIsDisabled(boolean isDisabled)
   :outertype: PartnershipDVO

setIsHostnameVerified
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsHostnameVerified(boolean isHostnameVerified)
   :outertype: PartnershipDVO

setIsInboundEncryptRequired
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsInboundEncryptRequired(boolean isInboundEncryptRequired)
   :outertype: PartnershipDVO

setIsInboundSignRequired
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsInboundSignRequired(boolean isInboundSignRequired)
   :outertype: PartnershipDVO

setIsOutboundCompressRequired
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsOutboundCompressRequired(boolean isOutboundEncryptRequired)
   :outertype: PartnershipDVO

setIsOutboundEncryptRequired
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsOutboundEncryptRequired(boolean isOutboundEncryptRequired)
   :outertype: PartnershipDVO

setIsOutboundSignRequired
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsOutboundSignRequired(boolean isOutboundSignRequired)
   :outertype: PartnershipDVO

setIsReceiptRequired
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsReceiptRequired(boolean isReceiptRequired)
   :outertype: PartnershipDVO

setIsReceiptSignRequired
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsReceiptSignRequired(boolean isReceiptSignRequired)
   :outertype: PartnershipDVO

setIsSyncReply
^^^^^^^^^^^^^^

.. java:method:: public void setIsSyncReply(boolean IsSyncReply)
   :outertype: PartnershipDVO

setMicAlgorithm
^^^^^^^^^^^^^^^

.. java:method:: public void setMicAlgorithm(String micAlgorithm)
   :outertype: PartnershipDVO

setPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public void setPartnershipId(String partnershipId)
   :outertype: PartnershipDVO

setReceiptAddress
^^^^^^^^^^^^^^^^^

.. java:method:: public void setReceiptAddress(String receiptAddress)
   :outertype: PartnershipDVO

setRecipientAddress
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setRecipientAddress(String recipientAddress)
   :outertype: PartnershipDVO

setRetries
^^^^^^^^^^

.. java:method:: public void setRetries(int retries)
   :outertype: PartnershipDVO

setRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public void setRetryInterval(int retryInterval)
   :outertype: PartnershipDVO

setSignAlgorithm
^^^^^^^^^^^^^^^^

.. java:method:: public void setSignAlgorithm(String signAlgorithm)
   :outertype: PartnershipDVO

setSubject
^^^^^^^^^^

.. java:method:: public void setSubject(String subject)
   :outertype: PartnershipDVO

setVerifyCert
^^^^^^^^^^^^^

.. java:method:: public void setVerifyCert(byte[] verifyCert)
   :outertype: PartnershipDVO

