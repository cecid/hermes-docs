.. java:import:: java.sql Timestamp

.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

MessageDVO
==========

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public interface MessageDVO extends DVO

   The \ ``MessageDataSourceDVO``\  is a implementation of interface \ ``MesageDVO``\  and representing one persistence record in the table \ *message*\ .

   :author: Donahue Sze, Twinsen Tsang (modifier)

Methods
-------
getAckRequested
^^^^^^^^^^^^^^^

.. java:method:: public String getAckRequested()
   :outertype: MessageDVO

   :return: Returns the ackRequested.

getAckSignRequested
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getAckSignRequested()
   :outertype: MessageDVO

getAction
^^^^^^^^^

.. java:method:: public String getAction()
   :outertype: MessageDVO

   :return: Returns the action.

getConvId
^^^^^^^^^

.. java:method:: public String getConvId()
   :outertype: MessageDVO

   :return: Returns the convId.

getCpaId
^^^^^^^^

.. java:method:: public String getCpaId()
   :outertype: MessageDVO

   :return: Returns the cpaId.

getDupElimination
^^^^^^^^^^^^^^^^^

.. java:method:: public String getDupElimination()
   :outertype: MessageDVO

   :return: Returns the dupElimination.

getFromPartyId
^^^^^^^^^^^^^^

.. java:method:: public String getFromPartyId()
   :outertype: MessageDVO

   :return: Returns the fromPartyId.

getFromPartyRole
^^^^^^^^^^^^^^^^

.. java:method:: public String getFromPartyRole()
   :outertype: MessageDVO

   :return: Returns the fromPartyRole.

getHasResendAsNew
^^^^^^^^^^^^^^^^^

.. java:method:: public String getHasResendAsNew()
   :outertype: MessageDVO

   :return: "true" if message has triggered "Resend as New", "false" if otherwise.

getMessageBox
^^^^^^^^^^^^^

.. java:method:: public String getMessageBox()
   :outertype: MessageDVO

   :return: Returns the messageType.

getMessageId
^^^^^^^^^^^^

.. java:method:: public String getMessageId()
   :outertype: MessageDVO

   :return: Returns the messageId.

getMessageType
^^^^^^^^^^^^^^

.. java:method:: public String getMessageType()
   :outertype: MessageDVO

   :return: Returns the messageType.

getPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public String getPartnershipId()
   :outertype: MessageDVO

getPrimalMessageId
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getPrimalMessageId()
   :outertype: MessageDVO

   :return: String primalMessageId refer to the message that triggered "Resend as New"

getPrincipalId
^^^^^^^^^^^^^^

.. java:method:: public String getPrincipalId()
   :outertype: MessageDVO

   :return: Returns the principal id of this message.

getRefToMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public String getRefToMessageId()
   :outertype: MessageDVO

   :return: Returns the refToMessageId.

getSequenceGroup
^^^^^^^^^^^^^^^^

.. java:method:: public int getSequenceGroup()
   :outertype: MessageDVO

getSequenceNo
^^^^^^^^^^^^^

.. java:method:: public int getSequenceNo()
   :outertype: MessageDVO

   :return: Returns the sequenceNo.

getSequenceStatus
^^^^^^^^^^^^^^^^^

.. java:method:: public int getSequenceStatus()
   :outertype: MessageDVO

getService
^^^^^^^^^^

.. java:method:: public String getService()
   :outertype: MessageDVO

   :return: Returns the service.

getStatus
^^^^^^^^^

.. java:method:: public String getStatus()
   :outertype: MessageDVO

   :return: Returns the status.

getStatusDescription
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getStatusDescription()
   :outertype: MessageDVO

getSyncReply
^^^^^^^^^^^^

.. java:method:: public String getSyncReply()
   :outertype: MessageDVO

   :return: Return whether the response EbMS message should be included in same SOAP connection.

getTimeStamp
^^^^^^^^^^^^

.. java:method:: public Timestamp getTimeStamp()
   :outertype: MessageDVO

   :return: Returns the timeStamp.

getTimeToLive
^^^^^^^^^^^^^

.. java:method:: public Timestamp getTimeToLive()
   :outertype: MessageDVO

   :return: Returns the timeToLive.

getTimeoutTimestamp
^^^^^^^^^^^^^^^^^^^

.. java:method:: public Timestamp getTimeoutTimestamp()
   :outertype: MessageDVO

   :return: Returns the timeout timestamp for this message. return null if the message does not requires acknowledgment.

getToPartyId
^^^^^^^^^^^^

.. java:method:: public String getToPartyId()
   :outertype: MessageDVO

   :return: Returns the toPartyId.

getToPartyRole
^^^^^^^^^^^^^^

.. java:method:: public String getToPartyRole()
   :outertype: MessageDVO

   :return: Returns the toPartyRole.

setAckRequested
^^^^^^^^^^^^^^^

.. java:method:: public void setAckRequested(String ackRequested)
   :outertype: MessageDVO

   :param ackRequested: The ackRequested to set.

setAckSignRequested
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setAckSignRequested(String ackSignRequested)
   :outertype: MessageDVO

setAction
^^^^^^^^^

.. java:method:: public void setAction(String action)
   :outertype: MessageDVO

   :param action: The action to set.

setConvId
^^^^^^^^^

.. java:method:: public void setConvId(String convId)
   :outertype: MessageDVO

   :param convId: The convId to set.

setCpaId
^^^^^^^^

.. java:method:: public void setCpaId(String cpaId)
   :outertype: MessageDVO

   :param cpaId: The cpaId to set.

setDupElimination
^^^^^^^^^^^^^^^^^

.. java:method:: public void setDupElimination(String dupElimination)
   :outertype: MessageDVO

   :param dupElimination: The dupElimination to set.

setFromPartyId
^^^^^^^^^^^^^^

.. java:method:: public void setFromPartyId(String fromPartyId)
   :outertype: MessageDVO

   :param fromPartyId: The fromPartyId to set.

setFromPartyRole
^^^^^^^^^^^^^^^^

.. java:method:: public void setFromPartyRole(String fromPartyRole)
   :outertype: MessageDVO

   :param fromPartyRole: The fromPartyRole to set.

setHasResendAsNew
^^^^^^^^^^^^^^^^^

.. java:method:: public void setHasResendAsNew(String hasResendAsNew)
   :outertype: MessageDVO

   :param hasResendAsNew: Set to "true" if message has triggered "Resend as New", "false" if otherwise

setMessageBox
^^^^^^^^^^^^^

.. java:method:: public void setMessageBox(String messageBox)
   :outertype: MessageDVO

   :param messageBox: The messageBox to set.

setMessageId
^^^^^^^^^^^^

.. java:method:: public void setMessageId(String messageId)
   :outertype: MessageDVO

   :param messageId: The messageId to set.

setMessageType
^^^^^^^^^^^^^^

.. java:method:: public void setMessageType(String messageType)
   :outertype: MessageDVO

   :param messageType: The messageType to set.

setPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public void setPartnershipId(String partnershipId)
   :outertype: MessageDVO

setPrimalMessageId
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setPrimalMessageId(String primalMessageId)
   :outertype: MessageDVO

   Set the primalMessageID which represent the message triggered "Resend as New"

   :param primalMessageId:

setPrincipalId
^^^^^^^^^^^^^^

.. java:method:: public void setPrincipalId(String principalId)
   :outertype: MessageDVO

   :param principalId: The principalId to set.

setRefToMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public void setRefToMessageId(String refToMessageId)
   :outertype: MessageDVO

   :param refToMessageId: The refToMessageId to set.

setSequenceGroup
^^^^^^^^^^^^^^^^

.. java:method:: public void setSequenceGroup(int sequenceGroup)
   :outertype: MessageDVO

setSequenceNo
^^^^^^^^^^^^^

.. java:method:: public void setSequenceNo(int sequenceNo)
   :outertype: MessageDVO

   :param sequenceNo: The sequenceNo to set.

setSequenceStatus
^^^^^^^^^^^^^^^^^

.. java:method:: public void setSequenceStatus(int sequenceStatus)
   :outertype: MessageDVO

setService
^^^^^^^^^^

.. java:method:: public void setService(String service)
   :outertype: MessageDVO

   :param service: The service to set.

setStatus
^^^^^^^^^

.. java:method:: public void setStatus(String status)
   :outertype: MessageDVO

   :param status: The status to set.

setStatusDescription
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setStatusDescription(String statusDescription)
   :outertype: MessageDVO

setSyncReply
^^^^^^^^^^^^

.. java:method:: public void setSyncReply(String syncReply)
   :outertype: MessageDVO

   The available \ ``syncReply``\  option in EbMS are listed below:

   ..

   #. mshSignalsOnly (same connection reply)
   #. none (different connection reply)

   :param syncReply: The syncReply option for this message.

setTimeStamp
^^^^^^^^^^^^

.. java:method:: public void setTimeStamp(Timestamp timeStamp)
   :outertype: MessageDVO

   :param timeStamp: The timeStamp to set.

setTimeToLive
^^^^^^^^^^^^^

.. java:method:: public void setTimeToLive(Timestamp timeToLive)
   :outertype: MessageDVO

   :param timeToLive: The timeToLive to set.

setTimeoutTimestamp
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setTimeoutTimestamp(Timestamp timeoutTimestamp)
   :outertype: MessageDVO

   :param timeoutTimestamp: The timeout timestamp for this message.

setToPartyId
^^^^^^^^^^^^

.. java:method:: public void setToPartyId(String toPartyId)
   :outertype: MessageDVO

   :param toPartyId: The toPartyId to set.

setToPartyRole
^^^^^^^^^^^^^^

.. java:method:: public void setToPartyRole(String toPartyRole)
   :outertype: MessageDVO

   :param toPartyRole: The toPartyRole to set.

