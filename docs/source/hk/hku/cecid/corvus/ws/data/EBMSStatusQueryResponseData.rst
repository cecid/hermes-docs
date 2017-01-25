EBMSStatusQueryResponseData
===========================

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class EBMSStatusQueryResponseData extends CorvusStatusQueryResponseData

   The \ ``EBMSStatusQueryResponseData``\  is the data structure representing the response data set for EBMS status query web services. This is the sample WSDL request for the status query WS request.

   .. parsed-literal::

         <status> The current status of message </status>
      <statusDescription> The current status description of message </statusDescription>
      <ackMessageId> The message id of acknowledgment / receipt if any </ackMessageId>
      <ackStatus> The status of acknowledgment / receipt if any </ackStatus>
      <ackStatusDescription> The status description of acknowledgment / receipt if any </ackStatusDescription>

   Creation Date: 10/05/2007

   :author: Twinsen Tsang

Fields
------
PARAM_KEY_SET
^^^^^^^^^^^^^

.. java:field:: public static final String[] PARAM_KEY_SET
   :outertype: EBMSStatusQueryResponseData

   This is the key set for XML serialization / de-serialization.

Constructors
------------
EBMSStatusQueryResponseData
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EBMSStatusQueryResponseData()
   :outertype: EBMSStatusQueryResponseData

   Default Constructor.

