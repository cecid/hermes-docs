AS2MessageData
==============

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class AS2MessageData extends KVPairData

   The \ ``AS2MessageData``\  is the data structure representing the parameters set for sending as2 messagw with payload to Hermes2. This is the sample WSDL request for the message status WS request.

   .. parsed-literal::

      <as2_from>as2loopback</as2_from>
      <as2_to>as2loopback</as2_to>
      <type>xml</type>

   The first three parameters are derived from \ :java:ref:`AS2PartnershipData.getAS2From()`\  and \ :java:ref:`AS2PartnershipData.getAs2To()`\ .

   :author: Twinsen Tsang

Fields
------
CONFIG_KEY_SET
^^^^^^^^^^^^^^

.. java:field:: public static final String[] CONFIG_KEY_SET
   :outertype: AS2MessageData

   This is the configuration key set for XML serialization / de-serialization.

CONFIG_PREFIX
^^^^^^^^^^^^^

.. java:field:: public static final String CONFIG_PREFIX
   :outertype: AS2MessageData

   This is the configuration prefix for serialization / de-serialization.

PARAM_KEY_SET
^^^^^^^^^^^^^

.. java:field:: public static final String[] PARAM_KEY_SET
   :outertype: AS2MessageData

   This is the key set for XML serialization / de-serialization.

PARAM_PREFIX
^^^^^^^^^^^^

.. java:field:: public static final String PARAM_PREFIX
   :outertype: AS2MessageData

   This is the param prefix for serialzation / de-serialization.

Constructors
------------
AS2MessageData
^^^^^^^^^^^^^^

.. java:constructor:: public AS2MessageData()
   :outertype: AS2MessageData

   Default Constructor.

Methods
-------
getMessageIdForReceive
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getMessageIdForReceive()
   :outertype: AS2MessageData

   Get the Message ID that targeted to retrieve

   :return: the value of Message ID in the AS2 message.

getRecvEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public String getRecvEndpoint()
   :outertype: AS2MessageData

   :return: Get the web service End-point for receiving AS2 message from CORVUS.

getRecvlistEndpoint
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getRecvlistEndpoint()
   :outertype: AS2MessageData

   :return: Get the web service End-point for receiving a list of AS2 message which are ready to down-load from CORVUS.

getSendEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public String getSendEndpoint()
   :outertype: AS2MessageData

   :return: Get the web service End-point for sending AS2 message to CORVUS.

getType
^^^^^^^

.. java:method:: public String getType()
   :outertype: AS2MessageData

   Get the type of the payload.

   :return: the type of payload in the AS2 message.

setMessageIdForReceive
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setMessageIdForReceive(String value)
   :outertype: AS2MessageData

   Set the Message ID that targeted to retrieve

   :param value: The Message ID of the AS2 message.

setRecvEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public void setRecvEndpoint(String endpoint)
   :outertype: AS2MessageData

   Set the web service End-point for receiving AS2 message from CORVUS.

   :param endpoint: The web service End-point for receiving AS2 message from CORVUS.

setRecvlistEndpoint
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setRecvlistEndpoint(String endpoint)
   :outertype: AS2MessageData

   Set the web service End-point for receiving a list of AS2 message which are ready to down-load from CORVUS.

   :param endpoint: the web service End-point for receiving a list of AS2 message which are ready to download from CORVUS.

setSendEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public void setSendEndpoint(String endpoint)
   :outertype: AS2MessageData

   Set the web service End-point for sending AS2 message to CORVUS.

   :param endpoint: The web service End-point for sending AS2 message to CORVUS.

setType
^^^^^^^

.. java:method:: public void setType(String type)
   :outertype: AS2MessageData

   Set the type of the payload.

   :param type: The type of payload in the AS2 message.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: AS2MessageData

   toString method.

