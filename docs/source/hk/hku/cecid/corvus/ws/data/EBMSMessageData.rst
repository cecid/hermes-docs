EBMSMessageData
===============

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class EBMSMessageData extends KVPairData

   The \ ``EBMSMessageData``\  is the data structure representing the parameters set for sending ebms message with payload to Hermes2.  This is the sample WSDL request for the sending EbMS message WS request. *

   .. parsed-literal::

      <cpaId> ebmscpaid </cpaId>
      <service> http://localhost:8080/corvus/httpd/ebms/inbound <service>
      <action> action </action>
      <convId> convId </convId>
      <fromPartyId> fromPartyId </fromPartyId>
      <fromPartyType> fromPartyType </fromPartyType>
      <toPartyId> toPartyId </toPartyId>
      <toPartyType> toPartyType </toPartyType>
      <refToMessageId> </refToMessageId>
      <serviceType> </serviceType>

   This is the sample WSDL request for the retrieve EbMS message WS request.*

   .. parsed-literal::

      <messageId> target-messageId </messageId>

   The first three parameters are derived from \ :java:ref:`EBMSPartnershipData.getCpaId()`\ , \ :java:ref:`EBMSPartnershipData.getService()`\  and \ :java:ref:`EBMSPartnershipData.getAction()`\

   :author: Twinsen Tsang

Fields
------
CONFIG_KEY_SET
^^^^^^^^^^^^^^

.. java:field:: public static final String[] CONFIG_KEY_SET
   :outertype: EBMSMessageData

   This is the configuration key set for XML serialization / de-serialization.

CONFIG_PREFIX
^^^^^^^^^^^^^

.. java:field:: public static final String CONFIG_PREFIX
   :outertype: EBMSMessageData

   This is the configuration prefix for serialization / de-serialization.

PARAM_KEY_SET
^^^^^^^^^^^^^

.. java:field:: public static final String[] PARAM_KEY_SET
   :outertype: EBMSMessageData

   This is the key set for XML serialization / de-serialization.

PARAM_PREFIX
^^^^^^^^^^^^

.. java:field:: public static final String PARAM_PREFIX
   :outertype: EBMSMessageData

   This is the parameters prefix for serialization / de-serialization.

isDirty
^^^^^^^

.. java:field:: public boolean isDirty
   :outertype: EBMSMessageData

   It the data is dirty.

Constructors
------------
EBMSMessageData
^^^^^^^^^^^^^^^

.. java:constructor:: public EBMSMessageData()
   :outertype: EBMSMessageData

   Default Constructor.

Methods
-------
getConversationId
^^^^^^^^^^^^^^^^^

.. java:method:: public String getConversationId()
   :outertype: EBMSMessageData

   :return: the conversationId

getFromPartyId
^^^^^^^^^^^^^^

.. java:method:: public String getFromPartyId()
   :outertype: EBMSMessageData

   :return: the fromPartyId

getFromPartyType
^^^^^^^^^^^^^^^^

.. java:method:: public String getFromPartyType()
   :outertype: EBMSMessageData

   :return: the fromPartyType

getMessageIdForReceive
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getMessageIdForReceive()
   :outertype: EBMSMessageData

   :return: the targeted Message ID for message receiver.

getRecvEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public String getRecvEndpoint()
   :outertype: EBMSMessageData

   :return: Get the web service End-point for receiving ebMS message from CORVUS.

getRecvlistEndpoint
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getRecvlistEndpoint()
   :outertype: EBMSMessageData

   :return: Get the web service End-point for receiving a list of ebMS message which are ready to download from CORVUS.

getRefToMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public String getRefToMessageId()
   :outertype: EBMSMessageData

   :return: the refToMessageId

getSendEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public String getSendEndpoint()
   :outertype: EBMSMessageData

   :return: Get the web service End-point for sending ebMS message to CORVUS.

getServiceType
^^^^^^^^^^^^^^

.. java:method:: public String getServiceType()
   :outertype: EBMSMessageData

   :return: the service type.

getToPartyId
^^^^^^^^^^^^

.. java:method:: public String getToPartyId()
   :outertype: EBMSMessageData

   :return: the toPartyId

getToPartyType
^^^^^^^^^^^^^^

.. java:method:: public String getToPartyType()
   :outertype: EBMSMessageData

   :return: the toPartyType

setConversationId
^^^^^^^^^^^^^^^^^

.. java:method:: public void setConversationId(String conversationId)
   :outertype: EBMSMessageData

   :param conversationId: the conversationId to set

setFromPartyId
^^^^^^^^^^^^^^

.. java:method:: public void setFromPartyId(String fromPartyId)
   :outertype: EBMSMessageData

   :param fromPartyId: the fromPartyId to set

setFromPartyType
^^^^^^^^^^^^^^^^

.. java:method:: public void setFromPartyType(String fromPartyType)
   :outertype: EBMSMessageData

   :param fromPartyType: the fromPartyType to set

setMessageIdForReceive
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setMessageIdForReceive(String value)
   :outertype: EBMSMessageData

   Set the Message ID that targeted to retrieve

   :param value: The MessageId of the message.

setRecvEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public void setRecvEndpoint(String endpoint)
   :outertype: EBMSMessageData

   Set the web service End-point for receiving ebMS message from CORVUS.

   :param endpoint: The web service End-point for receiving ebMS message from CORVUS.

setRecvlistEndpoint
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setRecvlistEndpoint(String endpoint)
   :outertype: EBMSMessageData

   Set the web service End-point for receiving a list of ebMS message which are ready to download from CORVUS.

   :param endpoint: the web service End-point for receiving a list of ebMS message which are ready to download from CORVUS.

setRefToMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public void setRefToMessageId(String refToMessageId)
   :outertype: EBMSMessageData

   :param refToMessageId: the refToMessageId to set

setSendEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public void setSendEndpoint(String endpoint)
   :outertype: EBMSMessageData

   Set the web service End-point for sending ebMS message to CORVUS.

   :param endpoint: The web service End-point for sending ebMS message to CORVUS.

setServiceType
^^^^^^^^^^^^^^

.. java:method:: public void setServiceType(String serviceType)
   :outertype: EBMSMessageData

   :param serviceType: the service type to set.

setToPartyId
^^^^^^^^^^^^

.. java:method:: public void setToPartyId(String toPartyId)
   :outertype: EBMSMessageData

   :param toPartyId: the toPartyId to set

setToPartyType
^^^^^^^^^^^^^^

.. java:method:: public void setToPartyType(String toPartyType)
   :outertype: EBMSMessageData

   :param toPartyType: the toPartyType to set

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: EBMSMessageData

