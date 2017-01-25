AS2ConfigData
=============

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class AS2ConfigData extends KVPairData

   The \ ``AS2ConfigData``\  is the data structure representing the parameters set for as2 runtime configuration. This is the sample WSDL request for the message status WS request.

   .. parsed-literal::

      <active-module-status> true | false </active-module-status>
      <inmessage-interval>15000</inmessage-interval>
      <inmessage-maxthread>0</inmessage-maxthread>
      <outmessage-interval>15000</outmessage-interval>
      <outmessage-maxthread>0</outmessage-maxthread>
      <outpayload-interval>15000</outpayload-interval>
      <outpayload-maxthread>0</outpayload-maxthread>

   :author: Twinsen Tsang

Fields
------
CONFIG_KEY_SET
^^^^^^^^^^^^^^

.. java:field:: public static final String[] CONFIG_KEY_SET
   :outertype: AS2ConfigData

   This is the configuration key set for XML serialization / de-serialization.

CONFIG_PREFIX
^^^^^^^^^^^^^

.. java:field:: public static final String CONFIG_PREFIX
   :outertype: AS2ConfigData

   This is the configuration prefix for serialization / de-serialization.

PARAM_KEY_SET
^^^^^^^^^^^^^

.. java:field:: public static final String[] PARAM_KEY_SET
   :outertype: AS2ConfigData

   This is the key set for XML serialization / de-serialization.

PARAM_PREFIX
^^^^^^^^^^^^

.. java:field:: public static final String PARAM_PREFIX
   :outertype: AS2ConfigData

   This is the param prefix for serialzation / de-serialization.

stressMode
^^^^^^^^^^

.. java:field:: public boolean stressMode
   :outertype: AS2ConfigData

   This is special flag for stress test mode. In stress test mode, messages are bumped into Hermes2 before start processing. so we need to switch off the active module before bumping the message. and restart after bumping. At the result, we need a flag for switch on / off active task module.

Constructors
------------
AS2ConfigData
^^^^^^^^^^^^^

.. java:constructor:: public AS2ConfigData()
   :outertype: AS2ConfigData

   Default Constructor.

Methods
-------
getActiveModuleStatus
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getActiveModuleStatus()
   :outertype: AS2ConfigData

   :return: Get the active module status wanted to set for this data.

getActiveModuleStatusBn
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean getActiveModuleStatusBn()
   :outertype: AS2ConfigData

   :return: Get the boolean value for ths active module status wanted to set for this data.

getInMessageExecInterval
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getInMessageExecInterval()
   :outertype: AS2ConfigData

   Get the execution interval for incoming message in this data.

   :return: the execution interval for incoming message in this data.

getInMessageMaxThread
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getInMessageMaxThread()
   :outertype: AS2ConfigData

   Get the maximum thread for incoming message in this data.

   :return: the maximum thread for incoming message in this data.

getOutMessageExecInterval
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getOutMessageExecInterval()
   :outertype: AS2ConfigData

   Get the execution interval for outgoing message in this data.

   :return: the execution interval for outgoing message in this data.

getOutMessageMaxThread
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getOutMessageMaxThread()
   :outertype: AS2ConfigData

   Get the maximum thread for outgoing message in this data.

   :return: the maximum thread for outgoing message in this data.

getOutPayloadExecInterval
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getOutPayloadExecInterval()
   :outertype: AS2ConfigData

   Get the execution interval for outgoing payload in this data.

   :return: the execution interval for outgoing payload in this data.

getOutPayloadMaxThread
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getOutPayloadMaxThread()
   :outertype: AS2ConfigData

   Get the maximum thread for outgoing payload in this data.

   :return: the maximum thread for outgoing payload in this data.

getSendEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public String getSendEndpoint()
   :outertype: AS2ConfigData

   :return: Get the web service endpoint for sending as2 config message to corvus.

setActiveModuleStatus
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setActiveModuleStatus(boolean newStatus)
   :outertype: AS2ConfigData

   Set the new active module status wanted for this data.

   :param newStatus: the new active module status wanted for this data.

setInMessageExecInterval
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setInMessageExecInterval(long newInterval)
   :outertype: AS2ConfigData

   :param newInterval: the new execution interval for incoming message for this data.

setInMessageMaxThread
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setInMessageMaxThread(long maxThread)
   :outertype: AS2ConfigData

   :param maxThread: the maximum thread for incoming message for this data.

setOutMessageExecInterval
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setOutMessageExecInterval(long newInterval)
   :outertype: AS2ConfigData

   :param newInterval: the new execution interval for outgoing message for this data.

setOutMessageMaxThread
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setOutMessageMaxThread(long maxThread)
   :outertype: AS2ConfigData

   :param maxThread: the maximum thread for outgoing message for this data.

setOutPayloadExecInterval
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setOutPayloadExecInterval(long newInterval)
   :outertype: AS2ConfigData

   :param newInterval: the new execution interval for outgoing payload for this data.

setOutPayloadMaxThread
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setOutPayloadMaxThread(long maxThread)
   :outertype: AS2ConfigData

   :param maxThread: the maximum thread for outgoing payload for this data.

setSendEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public void setSendEndpoint(String endpoint)
   :outertype: AS2ConfigData

   Set the web service endpoint for sending as2 config message to corvus.

   :param endpoint: The web service endpoint for sending as2 config message to corvus.

