.. java:import:: java.io BufferedReader

.. java:import:: java.io File

.. java:import:: java.io InputStream

.. java:import:: java.io InputStreamReader

.. java:import:: java.util List

.. java:import:: java.util Map

.. java:import:: java.util HashMap

.. java:import:: java.util ArrayList

.. java:import:: org.apache.http.client.methods HttpRequestBase

.. java:import:: org.apache.http.client.methods HttpPost

.. java:import:: org.apache.http HttpEntity

.. java:import:: org.apache.http NameValuePair

.. java:import:: org.apache.http.message BasicNameValuePair

.. java:import:: org.apache.http.client.entity UrlEncodedFormEntity

.. java:import:: org.apache.http.client.utils URLEncodedUtils

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data KVPairData

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws AS2MessageHistoryQuerySender

.. java:import:: hk.hku.cecid.corvus.ws.data AS2AdminData

.. java:import:: hk.hku.cecid.corvus.ws.data AS2MessageHistoryRequestData

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

AS2EnvelopQuerySender
=====================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class AS2EnvelopQuerySender extends EnvelopQuerySender

   The \ ``AS2EnvelopQuerySender``\  is a client service sender using HTTP protocol for query the message envelop (i.e EDI Header + payload) from the Hermes 2 Messaging Gateway.  To use it you have to provide the configuration instance called \ ``AS2AdminData``\ . it defines the URL end-point and credential for connecting to your Hermes 2 Restricted area.  An Example for adding partnership :

   .. parsed-literal::

      // Create an admin data for configuration.
      AS2AdminData adminData = new AS2AdminData();
      adminData.setManagePartnershipEndpoint("Your H2O location");
      adminData.setUsername("Your username for logging H2O");
      adminData.setPassword("Your password for logging H2O");

      AS2EnvelopQuerySender sender = new AS2EnvelopQuerySender(someLogger, adminData, pData);
      sender.setMessageCriteriaToDownload("The message id you want to query", "INBOX or OUTBOX");
      sender.run();
      InputStream ins = sender.getEnvelopStream();
      // The envelop content ... process it.

   \ **Note for setting the manage partnership end-point**\  You should add /admin/as2/partnership to your H2O host. For example, 'http://localhost:8080/admin/as2/partnership'. Note that the client service does not guarantee \ **transactional**\  behavior meaning you are always able to down-load the envelop when invoking the client. (Different from the receiver Web service).

   :author: Twinsen Tsang

   **See also:** :java:ref:`hk.hku.cecid.corvus.ws.data.AS2AdminData`

Fields
------
DL_RECEIPT_FORM_PARAM
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: protected static final String DL_RECEIPT_FORM_PARAM
   :outertype: AS2EnvelopQuerySender

Constructors
------------
AS2EnvelopQuerySender
^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AS2EnvelopQuerySender(FileLogger logger, AS2AdminData ad)
   :outertype: AS2EnvelopQuerySender

   Explicit Constructor. Create an instance of \ ``AS2EnvelopQuerySender``\ .

   :param logger: The logger for log the sending process.
   :param ad: The \ ``AS2AdminData``\  for locating the HTTP end-point the request send to.
   :throws NullPointerException: When \ ``p``\  is null. When the manage partnership end-point from \ ``ad``\  is null or empty.

Methods
-------
getMessageBoxMapping
^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected Map getMessageBoxMapping()
   :outertype: AS2EnvelopQuerySender

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: AS2EnvelopQuerySender

   The main method is for CLI mode.

onCreateRequest
^^^^^^^^^^^^^^^

.. java:method:: protected HttpRequestBase onCreateRequest() throws Exception
   :outertype: AS2EnvelopQuerySender

