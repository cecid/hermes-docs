.. java:import:: java.util Calendar

.. java:import:: java.util HashMap

.. java:import:: java.util Map

.. java:import:: hk.hku.cecid.corvus.util DateUtil

MessageStatusResponseData
=========================

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class MessageStatusResponseData extends KVPairData

   The \ ``MessageStatusResponseData``\  is the data structures representing the parameters set for the response in the message status requestquery.  This is the WSDL schema for the message status WS request.

   .. parsed-literal::

      <xs:complexType name="MessageInfo.Type">
       <xs:sequence>
        <xs:element name="messageId" type="xs:string"/>
        <xs:element name="messageType" type="xs:string"/>
        <xs:element name="timestamp" type="xs:dateTime"/>
        <xs:element name="messageStatus" type="xs:string"/>
        <xs:element name="messageDetail" type="xs:string" minOccurs="0"/>
        <xs:element name="partnershipId" type="xs:string" minOccurs="0"/>
        <xs:element name="channelType" type="xs:string" minOccurs="0"/>
        <xs:element name="channelId" type="xs:string" minOccurs="0"/>
        <xs:element name="folderName" type="xs:string" minOccurs="0"/>
        <xs:element name="fileName" type="xs:string" minOccurs="0"/>
        <xs:element name="conversationId" type="xs:string" minOccurs="0"/>
       </xs:sequence>
      </xs:complexType>

   Creation Date: 19/3/2007

   :author: Twinsen Tsang

Fields
------
PARAM_KEY_SET
^^^^^^^^^^^^^

.. java:field:: public static final String[] PARAM_KEY_SET
   :outertype: MessageStatusResponseData

   This is the key set for XML serialization / de-serialization.

Constructors
------------
MessageStatusResponseData
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public MessageStatusResponseData()
   :outertype: MessageStatusResponseData

   Default Constructor.

Methods
-------
getChannelId
^^^^^^^^^^^^

.. java:method:: public String getChannelId()
   :outertype: MessageStatusResponseData

   Gets the channelId value for this MessageInfoType.

   :return: channelId

getChannelType
^^^^^^^^^^^^^^

.. java:method:: public String getChannelType()
   :outertype: MessageStatusResponseData

   Gets the channelType value for this MessageInfoType.

   :return: channelType

getConversationId
^^^^^^^^^^^^^^^^^

.. java:method:: public String getConversationId()
   :outertype: MessageStatusResponseData

   Gets the conversationId value for this MessageInfoType.

   :return: conversationId

getFileName
^^^^^^^^^^^

.. java:method:: public String getFileName()
   :outertype: MessageStatusResponseData

   Gets the fileName value for this MessageInfoType.

   :return: fileName

getFolderName
^^^^^^^^^^^^^

.. java:method:: public String getFolderName()
   :outertype: MessageStatusResponseData

   Gets the folderName value for this MessageInfoType.

   :return: folderName

getMessageDetail
^^^^^^^^^^^^^^^^

.. java:method:: public String getMessageDetail()
   :outertype: MessageStatusResponseData

   Gets the messageDetail value for this MessageInfoType.

   :return: messageDetail

getMessageId
^^^^^^^^^^^^

.. java:method:: public String getMessageId()
   :outertype: MessageStatusResponseData

   Gets the messageId value for this MessageInfoType.

   :return: messageId

getMessageStatus
^^^^^^^^^^^^^^^^

.. java:method:: public String getMessageStatus()
   :outertype: MessageStatusResponseData

   Gets the messageStatus value for this MessageInfoType.

   :return: messageStatus

getMessageType
^^^^^^^^^^^^^^

.. java:method:: public String getMessageType()
   :outertype: MessageStatusResponseData

   Gets the messageType value for this MessageInfoType.

   :return: messageType

getPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public String getPartnershipId()
   :outertype: MessageStatusResponseData

   Gets the partnershipId value for this MessageInfoType.

   :return: partnershipId

getProperties
^^^^^^^^^^^^^

.. java:method:: public Map getProperties()
   :outertype: MessageStatusResponseData

   :return: the properties set for this MessageStatusResponseData.

getTimestamp
^^^^^^^^^^^^

.. java:method:: public String getTimestamp()
   :outertype: MessageStatusResponseData

   Gets the timestamp value for this MessageInfoType.

   :return: timestamp

setChannelId
^^^^^^^^^^^^

.. java:method:: public void setChannelId(String channelId)
   :outertype: MessageStatusResponseData

   Sets the channelId value for this MessageInfoType.

   :param channelId:

setChannelType
^^^^^^^^^^^^^^

.. java:method:: public void setChannelType(String channelType)
   :outertype: MessageStatusResponseData

   Sets the channelType value for this MessageInfoType.

   :param channelType:

setConversationId
^^^^^^^^^^^^^^^^^

.. java:method:: public void setConversationId(String conversationId)
   :outertype: MessageStatusResponseData

   Sets the conversationId value for this MessageInfoType.

   :param conversationId:

setFileName
^^^^^^^^^^^

.. java:method:: public void setFileName(String fileName)
   :outertype: MessageStatusResponseData

   Sets the fileName value for this MessageInfoType.

   :param fileName:

setFolderName
^^^^^^^^^^^^^

.. java:method:: public void setFolderName(String folderName)
   :outertype: MessageStatusResponseData

   Sets the folderName value for this MessageInfoType.

   :param folderName:

setMessageDetail
^^^^^^^^^^^^^^^^

.. java:method:: public void setMessageDetail(String messageDetail)
   :outertype: MessageStatusResponseData

   Sets the messageDetail value for this MessageInfoType.

   :param messageDetail:

setMessageId
^^^^^^^^^^^^

.. java:method:: public void setMessageId(String messageId)
   :outertype: MessageStatusResponseData

   Sets the messageId value for this MessageInfoType.

   :param messageId:

setMessageStatus
^^^^^^^^^^^^^^^^

.. java:method:: public void setMessageStatus(String messageStatus)
   :outertype: MessageStatusResponseData

   Sets the messageStatus value for this MessageInfoType.

   :param messageStatus:

setMessageType
^^^^^^^^^^^^^^

.. java:method:: public void setMessageType(String messageType)
   :outertype: MessageStatusResponseData

   Sets the messageType value for this MessageInfoType.

   :param messageType:

setPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public void setPartnershipId(String partnershipId)
   :outertype: MessageStatusResponseData

   Sets the partnershipId value for this MessageInfoType.

   :param partnershipId:

setProperties
^^^^^^^^^^^^^

.. java:method:: public void setProperties(HashMap hm)
   :outertype: MessageStatusResponseData

   Set the message status request properties and overwrite the existing one.

   :param hm: The new properties set.

setTimestamp
^^^^^^^^^^^^

.. java:method:: public void setTimestamp(Calendar timestamp)
   :outertype: MessageStatusResponseData

   Sets the timestamp value for this MessageInfoType.

   :param timestamp:

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: MessageStatusResponseData

   toString method().

