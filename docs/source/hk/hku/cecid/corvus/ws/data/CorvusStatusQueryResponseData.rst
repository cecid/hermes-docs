CorvusStatusQueryResponseData
=============================

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class CorvusStatusQueryResponseData extends KVPairData

   The \ ``CorvusStatusQueryResponseData``\  is the data structure representing the \ **general**\  response data set for status query web services in corvus level. This is the sample WSDL request for the status query WS request.

   .. parsed-literal::

         <status> The current status of message </status>
      <statusDescription> The current status description of message </statusDescription>
      <ackMessageId> The message id of acknowledgment / receipt if any </ackMessageId>
      <ackStatus> The status of acknowledgment / receipt if any </ackStatus>
      <ackStatusDescription> The status description of acknowledgment / receipt if any </ackStatusDescription>

   Creation Date: 10/05/2007

   :author: Twinsen Tsang

Constructors
------------
CorvusStatusQueryResponseData
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public CorvusStatusQueryResponseData(String[] paramKeySet)
   :outertype: CorvusStatusQueryResponseData

   Default Constructor.

Methods
-------
getACKMessageId
^^^^^^^^^^^^^^^

.. java:method:: public String getACKMessageId()
   :outertype: CorvusStatusQueryResponseData

   :return: the message ID of the acknowledgment corresponding to the message being queried.

getACKStatus
^^^^^^^^^^^^

.. java:method:: public String getACKStatus()
   :outertype: CorvusStatusQueryResponseData

   :return: the status of the acknowledgment corresponding to the message being queried.

getACKStatusDescription
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getACKStatusDescription()
   :outertype: CorvusStatusQueryResponseData

   :return: the status description of the acknowledgment corresponding to the message being queried.

getMessageId
^^^^^^^^^^^^

.. java:method:: public String getMessageId()
   :outertype: CorvusStatusQueryResponseData

   :return: the message ID of the message being queried.

getStatus
^^^^^^^^^

.. java:method:: public String getStatus()
   :outertype: CorvusStatusQueryResponseData

   :return: the current status of Message.

getStatusDescription
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getStatusDescription()
   :outertype: CorvusStatusQueryResponseData

   :return: the current status description of Message.

