.. java:import:: java.io BufferedReader

.. java:import:: java.io File

.. java:import:: java.io InputStream

.. java:import:: java.io InputStreamReader

.. java:import:: java.util HashMap

.. java:import:: java.util List

.. java:import:: java.util Map

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws EBMSMessageHistoryQuerySender

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSAdminData

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSMessageHistoryRequestData

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

EBMSEnvelopQuerySender
======================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class EBMSEnvelopQuerySender extends EnvelopQuerySender

   The \ ``EBMSEnvelopQuerySender``\  is a client service sender using HTTP protocol for query the message envelop (i.e EDI Header + payload) from the Hermes 2 Messaging Gateway.  To use it you have to provide the configuration instance called \ ``AS2AdminData``\ . it defines the URL end-point and credential for connecting to your Hermes 2 Restricted area.  An Example for adding partnership :

   .. parsed-literal::

      // Create an admin data for configuration.
      EBMSAdminData adminData = new EBMSAdminData();
      adminData.setManagePartnershipEndpoint("Your H2O location");
      adminData.setUsername("Your username for logging H2O");
      adminData.setPassword("Your password for logging H2O");

      EBMSEnvelopQuerySender sender = new EBMSEnvelopQuerySender(someLogger, adminData, pData);
      sender.setMessageCriteriaToDownload("The message id you want to query", "INBOX or OUTBOX");
      sender.run();
      InputStream ins = sender.getEnvelopStream();
      // The envelop content ... process it.

   \ **Note for setting the manage partnership end-point**\  You should add /admin/ebms/partnership to your H2O host. For example, 'http://localhost:8080/admin/ebms/partnership'. Note that the client service does not guarantee \ **transactional**\  behavior meaning you are always able to down-load the envelop when invoking the client. (Different from the receiver Web service).

   :author: Twinsen Tsang

   **See also:** :java:ref:`hk.hku.cecid.corvus.ws.data.EBMSAdminData`

Constructors
------------
EBMSEnvelopQuerySender
^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EBMSEnvelopQuerySender(FileLogger logger, EBMSAdminData ad)
   :outertype: EBMSEnvelopQuerySender

   Explicit Constructor. Create an instance of \ ``AS2EnvelopQuerySender``\ .

   :param logger: The logger for log the sending process.
   :param ad: The \ ``EBMSAdminData``\  for locating the HTTP end-point the request send to.
   :throws NullPointerException: When \ ``p``\  is null. When the manage partnership end-point from \ ``ad``\  is null or empty.

Methods
-------
getMessageBoxMapping
^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected Map getMessageBoxMapping()
   :outertype: EBMSEnvelopQuerySender

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: EBMSEnvelopQuerySender

   The main method is for CLI mode.

