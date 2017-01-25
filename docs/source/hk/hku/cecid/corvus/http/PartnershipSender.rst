.. java:import:: java.io InputStream

.. java:import:: java.util ArrayList

.. java:import:: java.util Date

.. java:import:: java.util List

.. java:import:: java.util Map

.. java:import:: java.util Iterator

.. java:import:: org.apache.http.client.methods HttpRequestBase

.. java:import:: org.apache.http.client.methods HttpPost

.. java:import:: org.apache.http.client.methods CloseableHttpResponse

.. java:import:: org.apache.http.entity.mime MultipartEntityBuilder

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data KVPairData

PartnershipSender
=================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public abstract class PartnershipSender extends HttpSender implements PartnershipOp

   The \ ``PartnershipSender``\  is abstract base class for sending HTTP remote request to H2O for executing partnership maintenance operation.

   :author: Twinsen Tsang

Constructors
------------
PartnershipSender
^^^^^^^^^^^^^^^^^

.. java:constructor:: protected PartnershipSender(FileLogger logger, KVPairData d)
   :outertype: PartnershipSender

   Explicit Constructor. Create an instance of \ ``PartnershipSender``\

   :param logger: The logger for log the sending process.
   :param d: The data used for generate HTTP multi-part request. It must be a kind of partnership data.

PartnershipSender
^^^^^^^^^^^^^^^^^

.. java:constructor:: protected PartnershipSender(FileLogger logger, KVPairData d, String username, String password)
   :outertype: PartnershipSender

   Explicit Constructor. Create an instance of \ ``PartnershipSender``\

   :param logger: The logger for log the sending process.
   :param d: The data used for generate HTTP multi-part request. It must be a kind of partnership data.
   :param username: The username for authentication
   :param password: The password for authentication

Methods
-------
getExecuteOperation
^^^^^^^^^^^^^^^^^^^

.. java:method:: public int getExecuteOperation()
   :outertype: PartnershipSender

getPartnershipMapping
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public abstract Map getPartnershipMapping()
   :outertype: PartnershipSender

   Get the mapping of the partnership data key to HTTP form parameter name.  For example, if there are 3 data (with keys) in your partnership data and they are named as "dataKey0", "dataKey1" and "dataKey2", and you want the HTTP request going to execute containing multi-part parameters "formParam0", "formParam1" and "formParam2" with the value equal to the data value from "dataKey0", "dataKey1", "dataKey2" respectively, Then you should return the Map listed below:

   .. parsed-literal::

      Map m = new HashMap(); // Or LinkedHashMap() if you want to preserve the order.
      m.put("dataKey0", "fromParam0");
      m.put("dataKey1", "fromParam1");
      m.put("dataKey2", "fromParam2");
      return m;

   :return: The mapping of the partnership data key to HTTP form parameter name.

getPartnershipOperationMapping
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public abstract Map getPartnershipOperationMapping()
   :outertype: PartnershipSender

   Get the mapping of the partnership operation from integer to words.  By default, it is recommended to return a HashMap(Integer, String) with 3 mappings.  HashMap.get(0) = A word representing the add partnership action. HashMap.get(1) = A word representing the delete partnership action. HashMap.get(2) = A word representing the update partnership action.

   :return: The mapping of the partnership operation from integer to words.

getStatus
^^^^^^^^^

.. java:method:: public String getStatus()
   :outertype: PartnershipSender

   Get the last status result description after executing the operation.  If the sender has not been invoked by other to execute partnership operation, It returns "Not yet run".

   :return: the last status result description after executing the operation.

onCreateRequest
^^^^^^^^^^^^^^^

.. java:method:: protected HttpRequestBase onCreateRequest() throws Exception
   :outertype: PartnershipSender

   [@EVENT] This method is invoked when the sender is required to create a HTTP Request from configuration.  It generates a multi-part content embedded in the HTTP POST request. The multi-part content contains all partnership data with the parameter name retrieved from the partnership mapping. \ :java:ref:`getPartnershipMapping()`\ . Also the type of partnership operation is appended at the end of multi-part with parameter name equal to 'request_action' and it's value is extracted thru \ :java:ref:`getPartnershipOperationMapping()`\ .

onResponse
^^^^^^^^^^

.. java:method:: protected void onResponse() throws Exception
   :outertype: PartnershipSender

   [@EVENT] This method is invoked when receivedas2 the reply HTTP response from the server.  Verify the HTTP response (expected a HTML content) by PartnershipOpVerifer to check whether the partnership operation execute successfully or not.

   :throws SAXException: When fail to verify by PartnershipOpVerifer.

onStart
^^^^^^^

.. java:method:: protected void onStart()
   :outertype: PartnershipSender

   [@EVENT] The method \ ``onStart``\  log all new configuration.

setExecuteOperation
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setExecuteOperation(int pOp)
   :outertype: PartnershipSender

