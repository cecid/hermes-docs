.. java:import:: java.sql Timestamp

.. java:import:: java.sql Types

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDVO

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds NullableObject

MessageDataSourceDVO
====================

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public class MessageDataSourceDVO extends DataSourceDVO implements MessageDVO

   The \ ``MessageDataSourceDVO``\  is a implementation of interface \ ``MesageDVO``\  and representing one persistence record in the table \ *message*\ .

   :author: Donahue Sze, Twinsen Tsang (modifier)

Constructors
------------
MessageDataSourceDVO
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public MessageDataSourceDVO()
   :outertype: MessageDataSourceDVO

Methods
-------
getAckRequested
^^^^^^^^^^^^^^^

.. java:method:: public String getAckRequested()
   :outertype: MessageDataSourceDVO

   :return: Returns the ackRequested.

getAckSignRequested
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getAckSignRequested()
   :outertype: MessageDataSourceDVO

   :return: String

getAction
^^^^^^^^^

.. java:method:: public String getAction()
   :outertype: MessageDataSourceDVO

   :return: Returns the action.

getConvId
^^^^^^^^^

.. java:method:: public String getConvId()
   :outertype: MessageDataSourceDVO

   :return: Returns the conversation id of the message record.

getCpaId
^^^^^^^^

.. java:method:: public String getCpaId()
   :outertype: MessageDataSourceDVO

   :return: Returns the cpaId.

getDupElimination
^^^^^^^^^^^^^^^^^

.. java:method:: public String getDupElimination()
   :outertype: MessageDataSourceDVO

   :return: Returns the dupElimination.

getFromPartyId
^^^^^^^^^^^^^^

.. java:method:: public String getFromPartyId()
   :outertype: MessageDataSourceDVO

   :return: Returns the fromPartyId.

getFromPartyRole
^^^^^^^^^^^^^^^^

.. java:method:: public String getFromPartyRole()
   :outertype: MessageDataSourceDVO

   :return: Returns the fromPartyRole.

getHasResendAsNew
^^^^^^^^^^^^^^^^^

.. java:method:: public String getHasResendAsNew()
   :outertype: MessageDataSourceDVO

   :return: "true" if message has triggered "Resend as New", "false" if otherwise

getMessageBox
^^^^^^^^^^^^^

.. java:method:: public String getMessageBox()
   :outertype: MessageDataSourceDVO

   :return: Returns the messageType.

getMessageId
^^^^^^^^^^^^

.. java:method:: public String getMessageId()
   :outertype: MessageDataSourceDVO

   :return: Returns the messageId.

getMessageType
^^^^^^^^^^^^^^

.. java:method:: public String getMessageType()
   :outertype: MessageDataSourceDVO

   :return: Returns the messageType.

getPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public String getPartnershipId()
   :outertype: MessageDataSourceDVO

getPrimalMessageId
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getPrimalMessageId()
   :outertype: MessageDataSourceDVO

   :return: The primalMessageID which represent the message triggered "Resend as New"

getPrincipalId
^^^^^^^^^^^^^^

.. java:method:: public String getPrincipalId()
   :outertype: MessageDataSourceDVO

   :return: Returns the principalId.

getRefToMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public String getRefToMessageId()
   :outertype: MessageDataSourceDVO

   :return: Returns the refToMessageId.

getSequenceGroup
^^^^^^^^^^^^^^^^

.. java:method:: public int getSequenceGroup()
   :outertype: MessageDataSourceDVO

   :return: Returns the sequenceGroup.

getSequenceNo
^^^^^^^^^^^^^

.. java:method:: public int getSequenceNo()
   :outertype: MessageDataSourceDVO

   :return: Returns the sequenceNo.

getSequenceStatus
^^^^^^^^^^^^^^^^^

.. java:method:: public int getSequenceStatus()
   :outertype: MessageDataSourceDVO

getService
^^^^^^^^^^

.. java:method:: public String getService()
   :outertype: MessageDataSourceDVO

   :return: Returns the service.

getStatus
^^^^^^^^^

.. java:method:: public String getStatus()
   :outertype: MessageDataSourceDVO

   :return: Returns the status.

getStatusDescription
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getStatusDescription()
   :outertype: MessageDataSourceDVO

getSyncReply
^^^^^^^^^^^^

.. java:method:: public String getSyncReply()
   :outertype: MessageDataSourceDVO

   :return: Return whether the response EbMS message should be included in same SOAP connection.

getTimeStamp
^^^^^^^^^^^^

.. java:method:: public Timestamp getTimeStamp()
   :outertype: MessageDataSourceDVO

   :return: Returns the timeStamp.

getTimeToLive
^^^^^^^^^^^^^

.. java:method:: public Timestamp getTimeToLive()
   :outertype: MessageDataSourceDVO

   :return: Returns the timeToLive.

getTimeoutTimestamp
^^^^^^^^^^^^^^^^^^^

.. java:method:: public Timestamp getTimeoutTimestamp()
   :outertype: MessageDataSourceDVO

   :return: Returns the timeout timestamp for this message. return null if the message does not requires acknowledgment.

getToPartyId
^^^^^^^^^^^^

.. java:method:: public String getToPartyId()
   :outertype: MessageDataSourceDVO

   :return: Returns the toPartyId.

getToPartyRole
^^^^^^^^^^^^^^

.. java:method:: public String getToPartyRole()
   :outertype: MessageDataSourceDVO

   :return: Returns the toPartyRole.

setAckRequested
^^^^^^^^^^^^^^^

.. java:method:: public void setAckRequested(String ackRequested)
   :outertype: MessageDataSourceDVO

   :param ackRequested: The ackRequested to set.

setAckSignRequested
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setAckSignRequested(String ackSignRequested)
   :outertype: MessageDataSourceDVO

   :param ackSignRequested:

setAction
^^^^^^^^^

.. java:method:: public void setAction(String action)
   :outertype: MessageDataSourceDVO

   :param action: The action to set.

setConvId
^^^^^^^^^

.. java:method:: public void setConvId(String convId)
   :outertype: MessageDataSourceDVO

   :param convId: The coversation id of this message record.

setCpaId
^^^^^^^^

.. java:method:: public void setCpaId(String cpaId)
   :outertype: MessageDataSourceDVO

   :param cpaId: The cpaId to set.

setDupElimination
^^^^^^^^^^^^^^^^^

.. java:method:: public void setDupElimination(String dupElimination)
   :outertype: MessageDataSourceDVO

   :param dupElimination: The dupElimination to set.

setFromPartyId
^^^^^^^^^^^^^^

.. java:method:: public void setFromPartyId(String fromPartyId)
   :outertype: MessageDataSourceDVO

   :param fromPartyId: The fromPartyId to set.

setFromPartyRole
^^^^^^^^^^^^^^^^

.. java:method:: public void setFromPartyRole(String fromPartyRole)
   :outertype: MessageDataSourceDVO

   :param fromPartyRole: The fromPartyRole to set.

setHasResendAsNew
^^^^^^^^^^^^^^^^^

.. java:method:: public void setHasResendAsNew(String hasResendAsNew)
   :outertype: MessageDataSourceDVO

   :param hasResendAsNew: Set to "true" if message has triggered "Resend as New", "false" if otherwise

setMessageBox
^^^^^^^^^^^^^

.. java:method:: public void setMessageBox(String messageBox)
   :outertype: MessageDataSourceDVO

   :param messageBox: The messageBox to set.

setMessageId
^^^^^^^^^^^^

.. java:method:: public void setMessageId(String messageId)
   :outertype: MessageDataSourceDVO

   :param messageId: The messageId to set.

setMessageType
^^^^^^^^^^^^^^

.. java:method:: public void setMessageType(String messageType)
   :outertype: MessageDataSourceDVO

   :param messageType: The messageType to set.

setPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public void setPartnershipId(String partnershipId)
   :outertype: MessageDataSourceDVO

setPrimalMessageId
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setPrimalMessageId(String primalMessageId)
   :outertype: MessageDataSourceDVO

   Set the primalMessageID which represent the message triggered "Resend as New"

   :param primalMessageId:

setPrincipalId
^^^^^^^^^^^^^^

.. java:method:: public void setPrincipalId(String principalId)
   :outertype: MessageDataSourceDVO

   :param principalId: The principalId to set.

setRefToMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public void setRefToMessageId(String refToMessageId)
   :outertype: MessageDataSourceDVO

   :param refToMessageId: The refToMessageId to set.

setSequenceGroup
^^^^^^^^^^^^^^^^

.. java:method:: public void setSequenceGroup(int sequenceGroup)
   :outertype: MessageDataSourceDVO

   :param sequenceGroup: The sequenceGroup to set.

setSequenceNo
^^^^^^^^^^^^^

.. java:method:: public void setSequenceNo(int sequenceNo)
   :outertype: MessageDataSourceDVO

   :param sequenceNo: The sequenceNo to set.

setSequenceStatus
^^^^^^^^^^^^^^^^^

.. java:method:: public void setSequenceStatus(int sequenceStatus)
   :outertype: MessageDataSourceDVO

setService
^^^^^^^^^^

.. java:method:: public void setService(String service)
   :outertype: MessageDataSourceDVO

   :param service: The service to set.

setStatus
^^^^^^^^^

.. java:method:: public void setStatus(String status)
   :outertype: MessageDataSourceDVO

   :param status: The status to set.

setStatusDescription
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setStatusDescription(String statusDescription)
   :outertype: MessageDataSourceDVO

setSyncReply
^^^^^^^^^^^^

.. java:method:: public void setSyncReply(String syncReply)
   :outertype: MessageDataSourceDVO

   The available \ ``syncReply``\  option in EbMS are listed below:

   ..

   #. mshSignalsOnly (same connection reply)
   #. none (different connection reply)

   :param syncReply: The syncReply option for this message.

setTimeStamp
^^^^^^^^^^^^

.. java:method:: public void setTimeStamp(Timestamp timeStamp)
   :outertype: MessageDataSourceDVO

   :param timeStamp: The timeStamp to set.

setTimeToLive
^^^^^^^^^^^^^

.. java:method:: public void setTimeToLive(Timestamp timeToLive)
   :outertype: MessageDataSourceDVO

   :param timeToLive: The timeToLive to set.

setTimeoutTimestamp
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setTimeoutTimestamp(Timestamp timeoutTimestamp)
   :outertype: MessageDataSourceDVO

   :param timeoutTimestamp: The timeout timestamp for this message.

setToPartyId
^^^^^^^^^^^^

.. java:method:: public void setToPartyId(String toPartyId)
   :outertype: MessageDataSourceDVO

   :param toPartyId: The toPartyId to set.

setToPartyRole
^^^^^^^^^^^^^^

.. java:method:: public void setToPartyRole(String toPartyRole)
   :outertype: MessageDataSourceDVO

   :param toPartyRole: The toPartyRole to set.

