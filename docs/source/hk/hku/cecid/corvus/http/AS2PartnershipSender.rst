.. java:import:: java.util HashMap

.. java:import:: java.util Map

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data AS2PartnershipData

.. java:import:: hk.hku.cecid.corvus.ws.data AS2AdminData

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

AS2PartnershipSender
====================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class AS2PartnershipSender extends PartnershipSender

   The \ ``AS2PartnershipSender``\  is a client service sender using HTTP protocol for maintaining the set of AS2 Partnership in Hermes 2 Messaging Gateway.  To use it you have to provide the configuration instance called \ ``AS2AdminData``\ . it defines the URL end-point and credential for connecting to your Hermes 2 Restricted area.  An Example for adding partnership :

   .. parsed-literal::

      // Create an administrative data for configuration.
      AS2AdminData adminData = new AS2AdminData();
      adminData.setManagePartnershipEndpoint("Your H2O location");
      adminData.setUsername("Your username for logging H2O");
      adminData.setPassword("Your password for logging H2O");
      // Create a partnership data for doing maintenance operation.
      AS2PartnershipData pData = new AS2PartnershipData();
                  .
                  .
                  .
      AS2PartnershipSender sender = new AS2PartnershipSender(someLogger, adminData, pData);
      sender.setExecuteOperation(PartnershipOp.Add);
      sender.run();

   \ **Note for setting the manage partnership end-point**\  You should add /admin/as2/partnership to your H2O host. For example, 'http://localhost:8080/admin/as2/partnership'. \ **Technical Information**\  The \ ``AS2PartnershipSender``\  will generate a HTTP multi-part request to the manage partnership end-point. The request includes all parameter extracted from the \ ``AS2Partnership``\ , each of them is represented as either text/plain multi-part, or application binary multi-part (for the \ ``certificates``\ ). The type of partnership operation to execute also append at the end of the HTTP request in a text multi-part form.

   :author: Twinsen Tsang

   **See also:** :java:ref:`hk.hku.cecid.corvus.ws.data.AS2AdminData`, :java:ref:`hk.hku.cecid.corvus.ws.data.AS2PartnershipData`, :java:ref:`hk.hku.cecid.corvus.http.PartnershipOp`

Fields
------
PARTNERSHIP_DATA_2_FROM_PARAM_NAME_MAPPING
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final Map PARTNERSHIP_DATA_2_FROM_PARAM_NAME_MAPPING
   :outertype: AS2PartnershipSender

PARTNERSHIP_OP_2_WORD
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final Map PARTNERSHIP_OP_2_WORD
   :outertype: AS2PartnershipSender

Constructors
------------
AS2PartnershipSender
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AS2PartnershipSender(FileLogger logger, AS2AdminData ad, AS2PartnershipData p)
   :outertype: AS2PartnershipSender

   Explicit Constructor. Create an instance of \ ``AS2PartnershipSender``\ .

   :param logger: The logger for log the sending process.
   :param ad: The \ ``AS2AdminData``\  for locating the HTTP end-point the request send to.
   :param p: The \ ``AS2PartnershipData``\  you want to add/delete/update.
   :throws NullPointerException: When \ ``p``\  is null. When the manage partnership end-point from \ ``ad``\  is null or empty.

Methods
-------
getPartnershipMapping
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public Map getPartnershipMapping()
   :outertype: AS2PartnershipSender

getPartnershipOperationMapping
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public Map getPartnershipOperationMapping()
   :outertype: AS2PartnershipSender

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: AS2PartnershipSender

   The main method is for CLI mode.

run
^^^

.. java:method:: public void run()
   :outertype: AS2PartnershipSender

   The main method for executing the partnership operation request.

   **See also:** :java:ref:`hk.hku.cecid.corvus.http.HttpSender.run()`

