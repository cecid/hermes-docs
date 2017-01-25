EBMSPartnershipData
===================

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class EBMSPartnershipData extends KVPairData

   The \ ``EBMSPartnershipData``\  is a duplicate-class data-structures for representing a EBMS partnership DVO object. It reduces the dependency from "corvus-ebms-core.jar" which changed quite frequently.

   :author: Twinsen Tsang

Fields
------
PARAM_CLASS_SET
^^^^^^^^^^^^^^^

.. java:field:: static final Class[] PARAM_CLASS_SET
   :outertype: EBMSPartnershipData

PARAM_KEY_SET
^^^^^^^^^^^^^

.. java:field:: public static final String[] PARAM_KEY_SET
   :outertype: EBMSPartnershipData

   This is the key set for XML serialization / de-serialization.

PARAM_PREFIX
^^^^^^^^^^^^

.. java:field:: public static final String PARAM_PREFIX
   :outertype: EBMSPartnershipData

   This is the parameter prefix for serialization / de-serialization.

Constructors
------------
EBMSPartnershipData
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EBMSPartnershipData()
   :outertype: EBMSPartnershipData

   Default constructor.

Methods
-------
getAckRequested
^^^^^^^^^^^^^^^

.. java:method:: public String getAckRequested()
   :outertype: EBMSPartnershipData

   :return: The acknowledgment requested.

getAckSignRequested
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getAckSignRequested()
   :outertype: EBMSPartnershipData

   :return: The acknowledgment signing requested.

getAction
^^^^^^^^^

.. java:method:: public String getAction()
   :outertype: EBMSPartnershipData

   :return: Returns the action.

getActor
^^^^^^^^

.. java:method:: public String getActor()
   :outertype: EBMSPartnershipData

   :return: The actor.

getCpaId
^^^^^^^^

.. java:method:: public String getCpaId()
   :outertype: EBMSPartnershipData

   :return: Returns the CPA ID.

getDisabled
^^^^^^^^^^^

.. java:method:: public String getDisabled()
   :outertype: EBMSPartnershipData

   :return: Returns the disabled.

getDsAlgorithm
^^^^^^^^^^^^^^

.. java:method:: public String getDsAlgorithm()
   :outertype: EBMSPartnershipData

   :return: The digital signing algorithm.

getDupElimination
^^^^^^^^^^^^^^^^^

.. java:method:: public String getDupElimination()
   :outertype: EBMSPartnershipData

   :return: The duplicated elimination.

getEncryptAlgorithm
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getEncryptAlgorithm()
   :outertype: EBMSPartnershipData

   :return: The encryption algorithm.

getEncryptCert
^^^^^^^^^^^^^^

.. java:method:: public byte[] getEncryptCert()
   :outertype: EBMSPartnershipData

   :return: The certificate for encryption in byte array.

getEncryptRequested
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getEncryptRequested()
   :outertype: EBMSPartnershipData

   :return: The checksum algorithm.

getIsHostnameVerified
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getIsHostnameVerified()
   :outertype: EBMSPartnershipData

   :return: True if the hostname is verified.

getMdAlgorithm
^^^^^^^^^^^^^^

.. java:method:: public String getMdAlgorithm()
   :outertype: EBMSPartnershipData

   :return: The digital signing algorithm.

getMessageOrder
^^^^^^^^^^^^^^^

.. java:method:: public String getMessageOrder()
   :outertype: EBMSPartnershipData

   :return: The messageOrder.

getPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public String getPartnershipId()
   :outertype: EBMSPartnershipData

   :return: Returns the channel ID.

getPersistDuration
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getPersistDuration()
   :outertype: EBMSPartnershipData

   :return: The persistDuration.

getRetries
^^^^^^^^^^

.. java:method:: public int getRetries()
   :outertype: EBMSPartnershipData

   :return: The retries.

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public int getRetryInterval()
   :outertype: EBMSPartnershipData

   :return: The retryInterval.

getService
^^^^^^^^^^

.. java:method:: public String getService()
   :outertype: EBMSPartnershipData

   :return: Returns the service.

getSignCert
^^^^^^^^^^^

.. java:method:: public byte[] getSignCert()
   :outertype: EBMSPartnershipData

   :return: The certificate for verification in byte array.

getSignRequested
^^^^^^^^^^^^^^^^

.. java:method:: public String getSignRequested()
   :outertype: EBMSPartnershipData

   :return: The signing requested.

getSyncReplyMode
^^^^^^^^^^^^^^^^

.. java:method:: public String getSyncReplyMode()
   :outertype: EBMSPartnershipData

   :return: Returns the syncReplyMode.

getTransportEndpoint
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getTransportEndpoint()
   :outertype: EBMSPartnershipData

   :return: The transportEndpoint.

getTransportProtocol
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getTransportProtocol()
   :outertype: EBMSPartnershipData

   :return: The transportProtocol.

setAckRequested
^^^^^^^^^^^^^^^

.. java:method:: public void setAckRequested(String ackRequested)
   :outertype: EBMSPartnershipData

   :param ackRequested: The acknowledgment requested to set.

setAckSignRequested
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setAckSignRequested(String ackSignRequested)
   :outertype: EBMSPartnershipData

   :param ackSignRequested: The acknowledgment signing requested to set.

setAction
^^^^^^^^^

.. java:method:: public void setAction(String action)
   :outertype: EBMSPartnershipData

   :param action: The action to set.

setActor
^^^^^^^^

.. java:method:: public void setActor(String actor)
   :outertype: EBMSPartnershipData

   :param actor: The actor to set.

setCpaId
^^^^^^^^

.. java:method:: public void setCpaId(String cpaId)
   :outertype: EBMSPartnershipData

   :param cpaId: The CPA ID to set.

setDisabled
^^^^^^^^^^^

.. java:method:: public void setDisabled(String disabled)
   :outertype: EBMSPartnershipData

   :param disabled: The disabled to set.

setDsAlgorithm
^^^^^^^^^^^^^^

.. java:method:: public void setDsAlgorithm(String dsAlgorithm)
   :outertype: EBMSPartnershipData

   :param dsAlgorithm: The digital signing algorithm to set.

setDupElimination
^^^^^^^^^^^^^^^^^

.. java:method:: public void setDupElimination(String dupElimination)
   :outertype: EBMSPartnershipData

   :param dupElimination: The duplicated elimination to set.

setEncryptAlgorithm
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setEncryptAlgorithm(String encryptAlgorithm)
   :outertype: EBMSPartnershipData

   :param encryptAlgorithm: The encryption algorithm to set.

setEncryptCert
^^^^^^^^^^^^^^

.. java:method:: public void setEncryptCert(byte[] encryptCert)
   :outertype: EBMSPartnershipData

   :param encryptCert: The certificate for encryption in byte array.

setEncryptRequested
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setEncryptRequested(String encryptRequested)
   :outertype: EBMSPartnershipData

   :param encryptRequested: The encryption requested to set.

setIsHostnameVerified
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsHostnameVerified(String isHostnameVerified)
   :outertype: EBMSPartnershipData

   :param isHostnameVerified: True if the hostname verified to set.

setMdAlgorithm
^^^^^^^^^^^^^^

.. java:method:: public void setMdAlgorithm(String mdAlgorithm)
   :outertype: EBMSPartnershipData

   :param mdAlgorithm: The checksum algorithm to set.

setMessageOrder
^^^^^^^^^^^^^^^

.. java:method:: public void setMessageOrder(String messageOrder)
   :outertype: EBMSPartnershipData

   :param messageOrder: The messageOrder to set.

setPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public void setPartnershipId(String partnershipId)
   :outertype: EBMSPartnershipData

   :param partnershipId: The partnership ID to set.

setPersistDuration
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setPersistDuration(String persistDuration)
   :outertype: EBMSPartnershipData

   :param persistDuration: The persistDuration to set.

setRetries
^^^^^^^^^^

.. java:method:: public void setRetries(int retries)
   :outertype: EBMSPartnershipData

   :param retries: The retries to set.

setRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public void setRetryInterval(int retryInterval)
   :outertype: EBMSPartnershipData

   :param retryInterval: The retryInterval to set.

setService
^^^^^^^^^^

.. java:method:: public void setService(String service)
   :outertype: EBMSPartnershipData

   :param service: The service to set.

setSignCert
^^^^^^^^^^^

.. java:method:: public void setSignCert(byte[] signCert)
   :outertype: EBMSPartnershipData

   :param signCert: The certificate for verification to set in byte array.

setSignRequested
^^^^^^^^^^^^^^^^

.. java:method:: public void setSignRequested(String signRequested)
   :outertype: EBMSPartnershipData

   :param signRequested: The signing requested to set.

setSyncReplyMode
^^^^^^^^^^^^^^^^

.. java:method:: public void setSyncReplyMode(String syncReplyMode)
   :outertype: EBMSPartnershipData

   :param syncReplyMode: The syncReplyMode to set.

setTransportEndpoint
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setTransportEndpoint(String transportEndpoint)
   :outertype: EBMSPartnershipData

   :param transportEndpoint: The transportEndpoint to set.

setTransportProtocol
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setTransportProtocol(String transportProtocol)
   :outertype: EBMSPartnershipData

   :param transportProtocol: The transportProtocol to set.

