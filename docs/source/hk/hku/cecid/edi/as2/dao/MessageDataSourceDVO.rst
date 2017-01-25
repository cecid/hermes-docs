.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDVO

.. java:import:: hk.hku.cecid.piazza.commons.util Convertor

.. java:import:: java.util Date

MessageDataSourceDVO
====================

.. java:package:: hk.hku.cecid.edi.as2.dao
   :noindex:

.. java:type:: public class MessageDataSourceDVO extends DataSourceDVO implements MessageDVO

   :author: Donahue Sze

Constructors
------------
MessageDataSourceDVO
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public MessageDataSourceDVO()
   :outertype: MessageDataSourceDVO

Methods
-------
getAs2From
^^^^^^^^^^

.. java:method:: public String getAs2From()
   :outertype: MessageDataSourceDVO

   :return: Returns the AS2 From.

getAs2To
^^^^^^^^

.. java:method:: public String getAs2To()
   :outertype: MessageDataSourceDVO

   :return: Returns the AS2 To.

getHasResendAsNew
^^^^^^^^^^^^^^^^^

.. java:method:: public String getHasResendAsNew()
   :outertype: MessageDataSourceDVO

   :return: "true" if message has triggered "Resend as New", "false" if otherwise

getMessageBox
^^^^^^^^^^^^^

.. java:method:: public String getMessageBox()
   :outertype: MessageDataSourceDVO

   :return: Returns the messageBox.

getMessageId
^^^^^^^^^^^^

.. java:method:: public String getMessageId()
   :outertype: MessageDataSourceDVO

   :return: Returns the messageId.

getMicValue
^^^^^^^^^^^

.. java:method:: public String getMicValue()
   :outertype: MessageDataSourceDVO

   :return: Returns the MIC value.

getOriginalMessageId
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getOriginalMessageId()
   :outertype: MessageDataSourceDVO

   :return: Returns the originalToMessageId.

getPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public String getPartnershipId()
   :outertype: MessageDataSourceDVO

getPrimalMessageId
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getPrimalMessageId()
   :outertype: MessageDataSourceDVO

   :return: The primalMessageID which represent the message triggered "Resend as New"

getReceiptUrl
^^^^^^^^^^^^^

.. java:method:: public String getReceiptUrl()
   :outertype: MessageDataSourceDVO

   getReceiptUrl

   :return: @see hk.hku.cecid.edi.as2.dao.MessageDVO#getReceiptUrl()

getStatus
^^^^^^^^^

.. java:method:: public String getStatus()
   :outertype: MessageDataSourceDVO

   :return: Returns the status.

getStatusDescription
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getStatusDescription()
   :outertype: MessageDataSourceDVO

   getStatusDescription

   :return: String

   **See also:** :java:ref:`hk.hku.cecid.edi.as2.dao.MessageDVO.getStatusDescription()`

getTimeStamp
^^^^^^^^^^^^

.. java:method:: public Date getTimeStamp()
   :outertype: MessageDataSourceDVO

   :return: Returns the timeStamp.

isAcknowledged
^^^^^^^^^^^^^^

.. java:method:: public boolean isAcknowledged()
   :outertype: MessageDataSourceDVO

   isAcknowledged

   :return: @see hk.hku.cecid.edi.as2.dao.MessageDVO#isAcknowledged()

isReceipt
^^^^^^^^^

.. java:method:: public boolean isReceipt()
   :outertype: MessageDataSourceDVO

   isReceipt

   :return: @see hk.hku.cecid.edi.as2.dao.MessageDVO#isReceipt()

isReceiptRequested
^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isReceiptRequested()
   :outertype: MessageDataSourceDVO

   isReceiptRequested

   :return: @see hk.hku.cecid.edi.as2.dao.MessageDVO#isReceiptRequested()

setAs2From
^^^^^^^^^^

.. java:method:: public void setAs2From(String as2From)
   :outertype: MessageDataSourceDVO

   :param as2From: The AS2 From to set.

setAs2To
^^^^^^^^

.. java:method:: public void setAs2To(String as2To)
   :outertype: MessageDataSourceDVO

   :param as2To: The AS2 To to set.

setHasResendAsNew
^^^^^^^^^^^^^^^^^

.. java:method:: public void setHasResendAsNew(String hasResendAsNew)
   :outertype: MessageDataSourceDVO

   :param hasResendAsNew: Set to "true" if message has triggered "Resend as New", "false" if otherwise

setIsAcknowledged
^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsAcknowledged(boolean isAcknowledged)
   :outertype: MessageDataSourceDVO

   setIsAcknowledged

   :param isAcknowledged:

   **See also:** :java:ref:`hk.hku.cecid.edi.as2.dao.MessageDVO.setIsAcknowledged(boolean)`

setIsReceipt
^^^^^^^^^^^^

.. java:method:: public void setIsReceipt(boolean isReceipt)
   :outertype: MessageDataSourceDVO

   setIsReceipt

   :param isReceipt:

   **See also:** :java:ref:`hk.hku.cecid.edi.as2.dao.MessageDVO.setIsReceipt(boolean)`

setIsReceiptRequested
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsReceiptRequested(boolean isReceiptRequested)
   :outertype: MessageDataSourceDVO

   setIsReceiptRequested

   :param isReceiptRequested:

   **See also:** :java:ref:`hk.hku.cecid.edi.as2.dao.MessageDVO.setIsReceiptRequested(boolean)`

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

setMicValue
^^^^^^^^^^^

.. java:method:: public void setMicValue(String micValue)
   :outertype: MessageDataSourceDVO

   :param micValue: The MIC value to set.

setOriginalMessageId
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setOriginalMessageId(String originalToMessageId)
   :outertype: MessageDataSourceDVO

   :param originalToMessageId: The originalToMessageId to set.

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

setReceiptUrl
^^^^^^^^^^^^^

.. java:method:: public void setReceiptUrl(String url)
   :outertype: MessageDataSourceDVO

   setReceiptUrl

   :param url:

   **See also:** :java:ref:`hk.hku.cecid.edi.as2.dao.MessageDVO.setReceiptUrl(java.lang.String)`

setStatus
^^^^^^^^^

.. java:method:: public void setStatus(String status)
   :outertype: MessageDataSourceDVO

   :param status: The service to set.

setStatusDescription
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setStatusDescription(String desc)
   :outertype: MessageDataSourceDVO

   setStatusDescription

   :param desc:

   **See also:** :java:ref:`hk.hku.cecid.edi.as2.dao.MessageDVO.setStatusDescription(java.lang.String)`

setTimeStamp
^^^^^^^^^^^^

.. java:method:: public void setTimeStamp(Date timeStamp)
   :outertype: MessageDataSourceDVO

   :param timeStamp: The timeStamp to set.

