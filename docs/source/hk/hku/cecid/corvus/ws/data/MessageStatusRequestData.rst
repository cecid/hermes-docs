.. java:import:: java.util Calendar

.. java:import:: java.math BigInteger

.. java:import:: hk.hku.cecid.corvus.util DateUtil

MessageStatusRequestData
========================

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class MessageStatusRequestData extends KVPairData

   The \ ``MessageStatusRequestData``\  is the data structures representing the parameters set for message status request query. This is the WSDL schema for the message status WS request.

   .. parsed-literal::

      <xs:sequence>
       <xs:element name="partnershipId" type="xs:string" minOccurs="0"/>
       <xs:element name="channelType" type="xs:string" minOccurs="0"/>
       <xs:element name="channelId" type="xs:string" minOccurs="0"/>
       <xs:element name="folderName" type="xs:string" minOccurs="0"/>
       <xs:element name="fileName" type="xs:string" minOccurs="0"/>
       <xs:element name="fromTimestamp" type="xs:dateTime" minOccurs="0"/>
       <xs:element name="toTimestamp" type="xs:dateTime" minOccurs="0"/>
       <xs:element name="numOfRecords" type="xs:integer" minOccurs="0"/>
       <xs:element name="conversationId" type="xs:string" minOccurs="0"/>
       <xs:element name="messageId" type="xs:string" minOccurs="0"/>
       <xs:element name="messageType" type="xs:string" minOccurs="0"/>
       <xs:element name="messageStatus" type="xs:string" minOccurs="0"/>
       <xs:element name="protocol" type="xs:string" minOccurs="0"/>
       <xs:element name="locale" type="xs:string" minOccurs="0"/>
       <xs:element name="levelOfDetails" type="xs:integer" minOccurs="0"/>
       <xs:element name="offset" type="xs:integer" minOccurs="0"/>
      </xs:sequence>

   Creation Date: 12/3/2007

   :author: Twinsen Tsang

Fields
------
CONFIG_KEY_SET
^^^^^^^^^^^^^^

.. java:field:: public static final String[] CONFIG_KEY_SET
   :outertype: MessageStatusRequestData

   This is the configuration key set for XML serialization / de-serialization.

CONFIG_PREFIX
^^^^^^^^^^^^^

.. java:field:: public static final String CONFIG_PREFIX
   :outertype: MessageStatusRequestData

   This is the prefix for serialization / de-serialization.

PARAM_KEY_SET
^^^^^^^^^^^^^

.. java:field:: public static final String[] PARAM_KEY_SET
   :outertype: MessageStatusRequestData

   This is the key set for XML serialization / de-serialization.

PARAM_PREFIX
^^^^^^^^^^^^

.. java:field:: public static final String PARAM_PREFIX
   :outertype: MessageStatusRequestData

   This is the prefix for serialzation / de-serialization.

Constructors
------------
MessageStatusRequestData
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public MessageStatusRequestData()
   :outertype: MessageStatusRequestData

   Default Constructor.

Methods
-------
getChannelId
^^^^^^^^^^^^

.. java:method:: public String getChannelId()
   :outertype: MessageStatusRequestData

   Gets the channelId value for this MessageStatusRequestData.

   :return: channelId

getChannelType
^^^^^^^^^^^^^^

.. java:method:: public String getChannelType()
   :outertype: MessageStatusRequestData

   Gets the channelType value for this MessageStatusRequestData.

   :return: channelType

getConversationId
^^^^^^^^^^^^^^^^^

.. java:method:: public String getConversationId()
   :outertype: MessageStatusRequestData

   Gets the conversationId value for this MessageStatusRequestData.

   :return: conversationId

getFileName
^^^^^^^^^^^

.. java:method:: public String getFileName()
   :outertype: MessageStatusRequestData

   Gets the fileName value for this MessageStatusRequestData.

   :return: fileName

getFolderName
^^^^^^^^^^^^^

.. java:method:: public String getFolderName()
   :outertype: MessageStatusRequestData

   Gets the folderName value for this MessageStatusRequestData.

   :return: folderName

getFromTimestamp
^^^^^^^^^^^^^^^^

.. java:method:: public String getFromTimestamp()
   :outertype: MessageStatusRequestData

   Gets the fromTimestamp value for this MessageStatusRequestData.

   :return: fromTimestamp

getLevelOfDetails
^^^^^^^^^^^^^^^^^

.. java:method:: public BigInteger getLevelOfDetails()
   :outertype: MessageStatusRequestData

   Gets the levelOfDetails value for this MessageStatusRequestData. The default value is 1.

   :return: levelOfDetails

getLocale
^^^^^^^^^

.. java:method:: public String getLocale()
   :outertype: MessageStatusRequestData

   Gets the locale value for this MessageStatusRequestData.

   :return: locale

getMessageId
^^^^^^^^^^^^

.. java:method:: public String getMessageId()
   :outertype: MessageStatusRequestData

   Gets the messageId value for this MessageStatusRequestData.

   :return: messageId

getMessageStatus
^^^^^^^^^^^^^^^^

.. java:method:: public String getMessageStatus()
   :outertype: MessageStatusRequestData

   Gets the messageStatus value for this MessageStatusRequestData.

   :return: messageStatus

getMessageType
^^^^^^^^^^^^^^

.. java:method:: public String getMessageType()
   :outertype: MessageStatusRequestData

   Gets the messageType value for this MessageStatusRequestData.

   :return: messageType

getNumOfRecords
^^^^^^^^^^^^^^^

.. java:method:: public BigInteger getNumOfRecords()
   :outertype: MessageStatusRequestData

   Gets the numOfRecords value for this MessageStatusRequestData. The default value is 1.

   :return: numOfRecords

getOffset
^^^^^^^^^

.. java:method:: public BigInteger getOffset()
   :outertype: MessageStatusRequestData

   Gets the offset value for this MessageStatusRequestData. The default value is 1.

   :return: offset

getPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public String getPartnershipId()
   :outertype: MessageStatusRequestData

   Gets the partnershipId value for this MessageStatusRequestData.

   :return: partnershipId

getPassword
^^^^^^^^^^^

.. java:method:: public String getPassword()
   :outertype: MessageStatusRequestData

   Get the password for authentication.

getProtocol
^^^^^^^^^^^

.. java:method:: public String getProtocol()
   :outertype: MessageStatusRequestData

   Gets the protocol value for this MessageStatusRequestData.

   :return: protocol

getToTimestamp
^^^^^^^^^^^^^^

.. java:method:: public String getToTimestamp()
   :outertype: MessageStatusRequestData

   Gets the toTimestamp value for this MessageStatusRequestData.

   :return: toTimestamp

getUsername
^^^^^^^^^^^

.. java:method:: public String getUsername()
   :outertype: MessageStatusRequestData

   Get the username for authentication.

   :return: Get the username for authentication.

getWSEndpoint
^^^^^^^^^^^^^

.. java:method:: public String getWSEndpoint()
   :outertype: MessageStatusRequestData

   Get the web service end point for this MessageStatusRequestData.

setChannelId
^^^^^^^^^^^^

.. java:method:: public void setChannelId(String channelId)
   :outertype: MessageStatusRequestData

   Sets the channelId value for this MessageStatusRequestData.

   :param channelId:

setChannelType
^^^^^^^^^^^^^^

.. java:method:: public void setChannelType(String channelType)
   :outertype: MessageStatusRequestData

   Sets the channelType value for this MessageStatusRequestData.

   :param channelType:

setConversationId
^^^^^^^^^^^^^^^^^

.. java:method:: public void setConversationId(String conversationId)
   :outertype: MessageStatusRequestData

   Sets the conversationId value for this MessageStatusRequestData.

   :param conversationId:

setFileName
^^^^^^^^^^^

.. java:method:: public void setFileName(String fileName)
   :outertype: MessageStatusRequestData

   Sets the fileName value for this MessageStatusRequestData.

   :param fileName:

setFolderName
^^^^^^^^^^^^^

.. java:method:: public void setFolderName(String folderName)
   :outertype: MessageStatusRequestData

   Sets the folderName value for this MessageStatusRequestData.

   :param folderName:

setFromTimestamp
^^^^^^^^^^^^^^^^

.. java:method:: public void setFromTimestamp(Calendar fromTimestamp)
   :outertype: MessageStatusRequestData

   Sets the fromTimestamp value for this MessageStatusRequestData.

   :param fromTimestamp:

setLevelOfDetails
^^^^^^^^^^^^^^^^^

.. java:method:: public void setLevelOfDetails(BigInteger levelOfDetails)
   :outertype: MessageStatusRequestData

   Sets the levelOfDetails value for this MessageStatusRequestData.

   :param levelOfDetails:

setLocale
^^^^^^^^^

.. java:method:: public void setLocale(String locale)
   :outertype: MessageStatusRequestData

   Sets the locale value for this MessageStatusRequestData.

   :param locale:

setMessageId
^^^^^^^^^^^^

.. java:method:: public void setMessageId(String messageId)
   :outertype: MessageStatusRequestData

   Sets the messageId value for this MessageStatusRequestData.

   :param messageId:

setMessageStatus
^^^^^^^^^^^^^^^^

.. java:method:: public void setMessageStatus(String messageStatus)
   :outertype: MessageStatusRequestData

   Sets the messageStatus value for this MessageStatusRequestData.

   :param messageStatus:

setMessageType
^^^^^^^^^^^^^^

.. java:method:: public void setMessageType(String messageType)
   :outertype: MessageStatusRequestData

   Sets the messageType value for this MessageStatusRequestData.

   :param messageType:

setNumOfRecords
^^^^^^^^^^^^^^^

.. java:method:: public void setNumOfRecords(BigInteger numOfRecords)
   :outertype: MessageStatusRequestData

   Sets the numOfRecords value for this MessageStatusRequestData.

   :param numOfRecords:

setOffset
^^^^^^^^^

.. java:method:: public void setOffset(BigInteger offset)
   :outertype: MessageStatusRequestData

   Sets the offset value for this MessageStatusRequestData.

   :param offset:

setPartnershipId
^^^^^^^^^^^^^^^^

.. java:method:: public void setPartnershipId(String partnershipId)
   :outertype: MessageStatusRequestData

   Sets the partnershipId value for this MessageStatusRequestData.

   :param partnershipId:

setPassword
^^^^^^^^^^^

.. java:method:: public void setPassword(String password)
   :outertype: MessageStatusRequestData

   Set the password for authentication.

setProtocol
^^^^^^^^^^^

.. java:method:: public void setProtocol(String protocol)
   :outertype: MessageStatusRequestData

   Sets the protocol value for this MessageStatusRequestData.

   :param protocol:

setToTimestamp
^^^^^^^^^^^^^^

.. java:method:: public void setToTimestamp(Calendar toTimestamp)
   :outertype: MessageStatusRequestData

   Sets the toTimestamp value for this MessageStatusRequestData.

   :param toTimestamp:

setUsername
^^^^^^^^^^^

.. java:method:: public void setUsername(String username)
   :outertype: MessageStatusRequestData

   Set the username for authentication.

   :param username: The username for authentication.

setWSEndpoint
^^^^^^^^^^^^^

.. java:method:: public void setWSEndpoint(String endpoint)
   :outertype: MessageStatusRequestData

   Set the web service end point for this MessageStatusRequestData.

   :param endpoint: The new web service end point.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: MessageStatusRequestData

   toString method().

