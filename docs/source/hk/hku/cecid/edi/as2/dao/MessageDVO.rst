.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

.. java:import:: java.util Date

MessageDVO
==========

.. java:package:: hk.hku.cecid.edi.as2.dao
   :noindex:

.. java:type:: public interface MessageDVO extends DVO

   :author: Donahue Sze

Fields
------
MSGBOX_IN
^^^^^^^^^

.. java:field:: public static String MSGBOX_IN
   :outertype: MessageDVO

MSGBOX_OUT
^^^^^^^^^^

.. java:field:: public static String MSGBOX_OUT
   :outertype: MessageDVO

STATUS_DELIVERED
^^^^^^^^^^^^^^^^

.. java:field:: public static String STATUS_DELIVERED
   :outertype: MessageDVO

STATUS_DELIVERY_FAILURE
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String STATUS_DELIVERY_FAILURE
   :outertype: MessageDVO

STATUS_PENDING
^^^^^^^^^^^^^^

.. java:field:: public static String STATUS_PENDING
   :outertype: MessageDVO

STATUS_PROCESSED
^^^^^^^^^^^^^^^^

.. java:field:: public static String STATUS_PROCESSED
   :outertype: MessageDVO

STATUS_PROCESSED_ERROR
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String STATUS_PROCESSED_ERROR
   :outertype: MessageDVO

STATUS_PROCESSING
^^^^^^^^^^^^^^^^^

.. java:field:: public static String STATUS_PROCESSING
   :outertype: MessageDVO

STATUS_RECEIVED
^^^^^^^^^^^^^^^

.. java:field:: public static String STATUS_RECEIVED
   :outertype: MessageDVO

Methods
-------
getAs2From
^^^^^^^^^^

.. java:method:: public String getAs2From()
   :outertype: MessageDVO

   :return: Returns the AS2 From.

getAs2To
^^^^^^^^

.. java:method:: public String getAs2To()
   :outertype: MessageDVO

   :return: Returns the AS2 To.

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

getMicValue
^^^^^^^^^^^

.. java:method:: public String getMicValue()
   :outertype: MessageDVO

   :return: Returns the MIC value.

getOriginalMessageId
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getOriginalMessageId()
   :outertype: MessageDVO

   :return: Returns the originalToMessageId.

getPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public String getPartnershipId()
   :outertype: MessageDVO

getPrimalMessageId
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getPrimalMessageId()
   :outertype: MessageDVO

   :return: String primalMessageId refer to the message that triggered "Resend as New"

getReceiptUrl
^^^^^^^^^^^^^

.. java:method:: public String getReceiptUrl()
   :outertype: MessageDVO

getStatus
^^^^^^^^^

.. java:method:: public String getStatus()
   :outertype: MessageDVO

   :return: Returns the status.

getStatusDescription
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getStatusDescription()
   :outertype: MessageDVO

getTimeStamp
^^^^^^^^^^^^

.. java:method:: public Date getTimeStamp()
   :outertype: MessageDVO

   :return: Returns the timeStamp.

isAcknowledged
^^^^^^^^^^^^^^

.. java:method:: public boolean isAcknowledged()
   :outertype: MessageDVO

isReceipt
^^^^^^^^^

.. java:method:: public boolean isReceipt()
   :outertype: MessageDVO

isReceiptRequested
^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isReceiptRequested()
   :outertype: MessageDVO

setAs2From
^^^^^^^^^^

.. java:method:: public void setAs2From(String as2From)
   :outertype: MessageDVO

   :param as2From: The AS2 From to set.

setAs2To
^^^^^^^^

.. java:method:: public void setAs2To(String as2To)
   :outertype: MessageDVO

   :param as2To: The AS2 To to set.

setHasResendAsNew
^^^^^^^^^^^^^^^^^

.. java:method:: public void setHasResendAsNew(String hasResendAsNew)
   :outertype: MessageDVO

   :param hasResendAsNew: Set to "true" if message has triggered "Resend as New", "false" if otherwise

setIsAcknowledged
^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsAcknowledged(boolean isAcknowledged)
   :outertype: MessageDVO

   :param isAcknowledged: The isAcknowledged to set.

setIsReceipt
^^^^^^^^^^^^

.. java:method:: public void setIsReceipt(boolean isReceipt)
   :outertype: MessageDVO

   :param isReceipt: The isReceipt to set.

setIsReceiptRequested
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setIsReceiptRequested(boolean isReceiptRequested)
   :outertype: MessageDVO

   :param isReceiptRequested: The isReceiptRequested to set.

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

setMicValue
^^^^^^^^^^^

.. java:method:: public void setMicValue(String micValue)
   :outertype: MessageDVO

   :param micValue: The MIC value to set.

setOriginalMessageId
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setOriginalMessageId(String originalToMessageId)
   :outertype: MessageDVO

   :param originalToMessageId: The originalToMessageId to set.

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

setReceiptUrl
^^^^^^^^^^^^^

.. java:method:: public void setReceiptUrl(String url)
   :outertype: MessageDVO

setStatus
^^^^^^^^^

.. java:method:: public void setStatus(String status)
   :outertype: MessageDVO

   :param status: The status to set.

setStatusDescription
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setStatusDescription(String desc)
   :outertype: MessageDVO

setTimeStamp
^^^^^^^^^^^^

.. java:method:: public void setTimeStamp(Date timeStamp)
   :outertype: MessageDVO

   :param timeStamp: The timeStamp to set.

