.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io InputStream

.. java:import:: java.security.cert CertificateFactory

.. java:import:: java.security.cert X509Certificate

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDVO

PartnershipDataSourceDVO
========================

.. java:package:: hk.hku.cecid.edi.as2.dao
   :noindex:

.. java:type:: public class PartnershipDataSourceDVO extends DataSourceDVO implements PartnershipDVO

   :author: Donahue Sze

Methods
-------
getAS2From
^^^^^^^^^^

.. java:method:: public String getAS2From()
   :outertype: PartnershipDataSourceDVO

getAs2To
^^^^^^^^

.. java:method:: public String getAs2To()
   :outertype: PartnershipDataSourceDVO

getEffectiveVerifyCertificate
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public X509Certificate getEffectiveVerifyCertificate()
   :outertype: PartnershipDataSourceDVO

getEncryptAlgorithm
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getEncryptAlgorithm()
   :outertype: PartnershipDataSourceDVO

getEncryptCert
^^^^^^^^^^^^^^

.. java:method:: public byte[] getEncryptCert()
   :outertype: PartnershipDataSourceDVO

getEncryptX509Certificate
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public X509Certificate getEncryptX509Certificate()
   :outertype: PartnershipDataSourceDVO

getMicAlgorithm
^^^^^^^^^^^^^^^

.. java:method:: public String getMicAlgorithm()
   :outertype: PartnershipDataSourceDVO

getPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public String getPartnershipId()
   :outertype: PartnershipDataSourceDVO

getReceiptAddress
^^^^^^^^^^^^^^^^^

.. java:method:: public String getReceiptAddress()
   :outertype: PartnershipDataSourceDVO

getRecipientAddress
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getRecipientAddress()
   :outertype: PartnershipDataSourceDVO

getRetries
^^^^^^^^^^

.. java:method:: public int getRetries()
   :outertype: PartnershipDataSourceDVO

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public int getRetryInterval()
   :outertype: PartnershipDataSourceDVO

getSignAlgorithm
^^^^^^^^^^^^^^^^

.. java:method:: public String getSignAlgorithm()
   :outertype: PartnershipDataSourceDVO

getSubject
^^^^^^^^^^

.. java:method:: public String getSubject()
   :outertype: PartnershipDataSourceDVO

getVerifyCert
^^^^^^^^^^^^^

.. java:method:: public byte[] getVerifyCert()
   :outertype: PartnershipDataSourceDVO

getVerifyX509Certificate
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public X509Certificate getVerifyX509Certificate()
   :outertype: PartnershipDataSourceDVO

isDisabled
^^^^^^^^^^

.. java:method:: public boolean isDisabled()
   :outertype: PartnershipDataSourceDVO

isHostnameVerified
^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isHostnameVerified()
   :outertype: PartnershipDataSourceDVO

isInboundEncryptRequired
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isInboundEncryptRequired()
   :outertype: PartnershipDataSourceDVO

isInboundSignRequired
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isInboundSignRequired()
   :outertype: PartnershipDataSourceDVO

isOutboundCompressRequired
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isOutboundCompressRequired()
   :outertype: PartnershipDataSourceDVO

isOutboundEncryptRequired
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isOutboundEncryptRequired()
   :outertype: PartnershipDataSourceDVO

isOutboundSignRequired
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isOutboundSignRequired()
   :outertype: PartnershipDataSourceDVO

isReceiptRequired
^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isReceiptRequired()
   :outertype: PartnershipDataSourceDVO

isReceiptSignRequired
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isReceiptSignRequired()
   :outertype: PartnershipDataSourceDVO

isSyncReply
^^^^^^^^^^^

.. java:method:: public boolean isSyncReply()
   :outertype: PartnershipDataSourceDVO

setAs2From
^^^^^^^^^^

.. java:method:: public void setAs2From(String as2From)
   :outertype: PartnershipDataSourceDVO

setAs2To
^^^^^^^^

.. java:method:: public void setAs2To(String as2To)
   :outertype: PartnershipDataSourceDVO

setEncryptAlgorithm
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setEncryptAlgorithm(String encryptAlgorithm)
   :outertype: PartnershipDataSourceDVO

setEncryptCert
^^^^^^^^^^^^^^

.. java:method:: public void setEncryptCert(byte[] encryptCert)
   :outertype: PartnershipDataSourceDVO

setIsDisabled
^^^^^^^^^^^^^

.. java:method:: public void setIsDisabled(boolean isDisabled)
   :outertype: PartnershipDataSourceDVO

setIsHostnameVerified
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsHostnameVerified(boolean isHostnameVerified)
   :outertype: PartnershipDataSourceDVO

setIsInboundEncryptRequired
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsInboundEncryptRequired(boolean isInboundEncryptRequired)
   :outertype: PartnershipDataSourceDVO

setIsInboundSignRequired
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsInboundSignRequired(boolean isInboundSignRequired)
   :outertype: PartnershipDataSourceDVO

setIsOutboundCompressRequired
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsOutboundCompressRequired(boolean isOutboundCompressRequired)
   :outertype: PartnershipDataSourceDVO

setIsOutboundEncryptRequired
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsOutboundEncryptRequired(boolean isOutboundEncryptRequired)
   :outertype: PartnershipDataSourceDVO

setIsOutboundSignRequired
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsOutboundSignRequired(boolean isOutboundSignRequired)
   :outertype: PartnershipDataSourceDVO

setIsReceiptRequired
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsReceiptRequired(boolean isReceiptRequired)
   :outertype: PartnershipDataSourceDVO

setIsReceiptSignRequired
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsReceiptSignRequired(boolean isReceiptSignRequired)
   :outertype: PartnershipDataSourceDVO

setIsSyncReply
^^^^^^^^^^^^^^

.. java:method:: public void setIsSyncReply(boolean isSyncReply)
   :outertype: PartnershipDataSourceDVO

setMicAlgorithm
^^^^^^^^^^^^^^^

.. java:method:: public void setMicAlgorithm(String micAlgorithm)
   :outertype: PartnershipDataSourceDVO

setPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public void setPartnershipId(String partnershipId)
   :outertype: PartnershipDataSourceDVO

setReceiptAddress
^^^^^^^^^^^^^^^^^

.. java:method:: public void setReceiptAddress(String receiptAddress)
   :outertype: PartnershipDataSourceDVO

setRecipientAddress
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setRecipientAddress(String recipientAddress)
   :outertype: PartnershipDataSourceDVO

setRetries
^^^^^^^^^^

.. java:method:: public void setRetries(int retries)
   :outertype: PartnershipDataSourceDVO

setRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public void setRetryInterval(int retryInterval)
   :outertype: PartnershipDataSourceDVO

setSignAlgorithm
^^^^^^^^^^^^^^^^

.. java:method:: public void setSignAlgorithm(String signAlgorithm)
   :outertype: PartnershipDataSourceDVO

setSubject
^^^^^^^^^^

.. java:method:: public void setSubject(String subject)
   :outertype: PartnershipDataSourceDVO

setVerifyCert
^^^^^^^^^^^^^

.. java:method:: public void setVerifyCert(byte[] verifyCert)
   :outertype: PartnershipDataSourceDVO

