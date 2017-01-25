CorvusStatusQueryData
=====================

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class CorvusStatusQueryData extends KVPairData

   The \ ``CorvusStatusQueryData``\  is the data structure representing the parameters set for status query web services for all protocol using Corvus level. This is the sample WSDL request for the status query WS request.

   .. parsed-literal::

      <messageId> 20070418-124233-75006@147.8.177.42 </messageId>

   Creation Date: 2/5/2007

   :author: Twinsen Tsang

Fields
------
CONFIG_KEY_SET
^^^^^^^^^^^^^^

.. java:field:: public static final String[] CONFIG_KEY_SET
   :outertype: CorvusStatusQueryData

   This is the configuration key set for XML serialization / de-serialization.

PARAM_KEY_SET
^^^^^^^^^^^^^

.. java:field:: public static final String[] PARAM_KEY_SET
   :outertype: CorvusStatusQueryData

   This is the key set for XML serialization / de-serialization.

configPrefix
^^^^^^^^^^^^

.. java:field:: public String configPrefix
   :outertype: CorvusStatusQueryData

   This is the configuration prefix for serialization / de-serialization.

paramPrefix
^^^^^^^^^^^

.. java:field:: public String paramPrefix
   :outertype: CorvusStatusQueryData

   This is the param prefix for serialzation / de-serialization.

Constructors
------------
CorvusStatusQueryData
^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public CorvusStatusQueryData(String ConfigXPath, String ParamXPath)
   :outertype: CorvusStatusQueryData

   Explicit Constructor.

   :param ConfigXPath: The XPath for the configuration data in status query.
   :param ParamXPath: The XPath for the paramter data in status query.

Methods
-------
getQueryMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public String getQueryMessageId()
   :outertype: CorvusStatusQueryData

   :return: The message id to query the status.

getSendEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public String getSendEndpoint()
   :outertype: CorvusStatusQueryData

   :return: Get the web service endpoint for sending status query message to corvus.

setQueryMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public void setQueryMessageId(String messageId)
   :outertype: CorvusStatusQueryData

   :param messageId: The message id to query the status.

setSendEndpoint
^^^^^^^^^^^^^^^

.. java:method:: public void setSendEndpoint(String endpoint)
   :outertype: CorvusStatusQueryData

   Set the web service endpoint for sending status query message to corvus.

   :param endpoint: The web service endpoint for sending status query message to corvus.

