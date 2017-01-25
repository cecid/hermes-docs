EBMSConfigData
==============

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class EBMSConfigData extends KVPairData

   The \ ``EBMSConfigData``\  is the data structure representing the parameters set for EbMS runtime configuration. This is the WSDL schema for the message status WS request.

   .. parsed-literal::

      <active-module-status> true | false </active-module-status>
      <incollector-interval>15000</incollector-interval>
      <incollector-maxthread>0</incollector-maxthread>
      <outcollector-interval>15000</outcollector-interval>
      <outcollector-maxthread>0</outcollector-maxthread>
      <mailcollector-interval>15000</mailcollector-interval>
      <mailcollector-maxthread>0</mailcollector-maxthread>

   :author: Twinsen

Fields
------
CONFIG_KEY_SET
^^^^^^^^^^^^^^

.. java:field:: public static final String[] CONFIG_KEY_SET
   :outertype: EBMSConfigData

   This is the configuration key set for XML serialization / de-serialization.

CONFIG_PREFIX
^^^^^^^^^^^^^

.. java:field:: public static final String CONFIG_PREFIX
   :outertype: EBMSConfigData

   This is the configuration prefix for serialization / de-serialization.

PARAM_KEY_SET
^^^^^^^^^^^^^

.. java:field:: public static final String[] PARAM_KEY_SET
   :outertype: EBMSConfigData

   This is the key set for XML serialization / de-serialization.

PARAM_PREFIX
^^^^^^^^^^^^

.. java:field:: public static final String PARAM_PREFIX
   :outertype: EBMSConfigData

   This is the param prefix for serialzation / de-serialization.

Constructors
------------
EBMSConfigData
^^^^^^^^^^^^^^

.. java:constructor:: public EBMSConfigData()
   :outertype: EBMSConfigData

   Default Constructor.

Methods
-------
getActiveModuleStatus
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getActiveModuleStatus()
   :outertype: EBMSConfigData

   :return: Get the active module status wanted to set for this data.

getActiveModuleStatusBn
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean getActiveModuleStatusBn()
   :outertype: EBMSConfigData

   :return: Get the boolean value for ths active module status wanted to set for this data.

getInCollectorExecInterval
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getInCollectorExecInterval()
   :outertype: EBMSConfigData

   Get the execution interval for incoming collector in this data.

   :return: the execution interval for incoming collector in this data.

getInCollectorMaxThread
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getInCollectorMaxThread()
   :outertype: EBMSConfigData

   Get the maximum thread for incoming message in this data.

   :return: the maximum thread for incoming message in this data.

getMailCollectorExecInterval
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getMailCollectorExecInterval()
   :outertype: EBMSConfigData

   Get the execution interval for mail collector in this data.

   :return: the execution interval for mail collector in this data.

getMailCollectorMaxThread
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getMailCollectorMaxThread()
   :outertype: EBMSConfigData

   Get the maximum thread for mail message in this data.

   :return: the maximum thread for mail message in this data.

getOutCollectorExecInterval
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getOutCollectorExecInterval()
   :outertype: EBMSConfigData

   Get the execution interval for outgoing collector in this data.

   :return: the execution interval for outgoing collector in this data.

getOutCollectorMaxThread
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getOutCollectorMaxThread()
   :outertype: EBMSConfigData

   Get the maximum thread for outgoing message in this data.

   :return: the maximum thread for outgoing message in this data.

getSendEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public String getSendEndpoint()
   :outertype: EBMSConfigData

   :return: Get the web service endpoint for sending as2 config message to corvus.

setActiveModuleStatus
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setActiveModuleStatus(boolean newStatus)
   :outertype: EBMSConfigData

   Set the new active module status wanted for this data.

   :param newStatus: the new active module status wanted for this data.

setInCollectorExecInterval
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setInCollectorExecInterval(long newInterval)
   :outertype: EBMSConfigData

   :param newInterval: the new execution interval for incoming collector for this data.

setInCollectorMaxThread
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setInCollectorMaxThread(long maxThread)
   :outertype: EBMSConfigData

   :param maxThread: the maximum thread for incoming message for this data.

setMailCollectorExecInterval
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setMailCollectorExecInterval(long newInterval)
   :outertype: EBMSConfigData

   :param newInterval: the new execution interval for mail collector for this data.

setMailCollectorMaxThread
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setMailCollectorMaxThread(long maxThread)
   :outertype: EBMSConfigData

   :param maxThread: the maximum thread for mail message for this data.

setOutCollectorExecInterval
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setOutCollectorExecInterval(long newInterval)
   :outertype: EBMSConfigData

   :param newInterval: the new execution interval for outgoing collector for this data.

setOutCollectorMaxThread
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setOutCollectorMaxThread(long maxThread)
   :outertype: EBMSConfigData

   :param maxThread: the maximum thread for outgoing message for this data.

setSendEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public void setSendEndpoint(String endpoint)
   :outertype: EBMSConfigData

   Set the web service endpoint for sending as2 config message to corvus.

   :param endpoint: The web service endpoint for sending as2 config message to corvus.

