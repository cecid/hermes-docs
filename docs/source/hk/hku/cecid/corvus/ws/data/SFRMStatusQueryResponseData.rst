.. java:import:: java.sql Timestamp

SFRMStatusQueryResponseData
===========================

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class SFRMStatusQueryResponseData extends KVPairData

   The \ ``SFRMStatusQueryResponseData``\  is the data structure representing the response data set for SFRM Message Status Query serivce. This is the sample WSDL response for the SFRM status query WS request.

   .. parsed-literal::

      <messageInfo>
      <status> The current status of message </status>
      <statusDescription> The current status description of message </statusDescription>
      <numberOfSegments> Maximum number of segments </numberOfSegments>
      <numberOfProcessedSegments> Number of processed segments </numberOfProcessedSegments>
      <lastUpdatedTime>  The last updated timestamp  </lastUpdatedTime>
      </messageInfo>

   Creation Date: 10/5/2007

   :author: Twinsen Tsang

Fields
------
PARAM_KEY_SET
^^^^^^^^^^^^^

.. java:field:: public static final String[] PARAM_KEY_SET
   :outertype: SFRMStatusQueryResponseData

   This is the key set for XML serialization / de-serialization.

Constructors
------------
SFRMStatusQueryResponseData
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SFRMStatusQueryResponseData()
   :outertype: SFRMStatusQueryResponseData

   Default Constructor.

Methods
-------
getLastUpdatedTimestamp
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public Timestamp getLastUpdatedTimestamp()
   :outertype: SFRMStatusQueryResponseData

   The last updated timestamp define the last time that the SFRM message was being processing. (last activity time).

   :return: the last active time for thie SFRM Message.

getMessageId
^^^^^^^^^^^^

.. java:method:: public String getMessageId()
   :outertype: SFRMStatusQueryResponseData

   :return: the message ID of the SFRM message being queried.

getNumberOfProcessedSegments
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int getNumberOfProcessedSegments()
   :outertype: SFRMStatusQueryResponseData

   :return: the number of processed segments for this SFRM Message.

getNumberOfSegments
^^^^^^^^^^^^^^^^^^^

.. java:method:: public int getNumberOfSegments()
   :outertype: SFRMStatusQueryResponseData

   :return: the number of segments for this SFRM Message.

getStatus
^^^^^^^^^

.. java:method:: public String getStatus()
   :outertype: SFRMStatusQueryResponseData

   :return: the current status of SFRM Message.

getStatusDescription
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getStatusDescription()
   :outertype: SFRMStatusQueryResponseData

   :return: the current status description of SFRM Message.

