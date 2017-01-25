.. java:import:: java.util Map

.. java:import:: java.util HashMap

.. java:import:: java.util LinkedHashMap

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSAdminData

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSPartnershipData

EBMSPartnershipSender
=====================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class EBMSPartnershipSender extends PartnershipSender

   The \ ``EBMSPartnershipSender``\  is a client service sender using HTTP protocol for maintaining the set of EBMS Partnership in Hermes 2 Messaging Gateway.  To use it you have to provide the configuration instance called \ ``EBMSAdminData``\ . it defines the URL end-point and credential for connecting to your Hermes 2 Restricted area.  An Example for adding partnership :

   .. parsed-literal::

      // Create an administrative data for configuration.
      EBMSAdminData adminData = new EBMSAdminData();
      adminData.setManagePartnershipEndpoint("Your H2O location");
      adminData.setUsername("Your username for logging H2O");
      adminData.setPassword("Your password for logging H2O");
      // Create a partnership data for doing maintenance operation.
      EBMSPartnershipData pData = new EBMSPartnershipData();
                  .
                  .
                  .
      EBMSPartnershipData sender = new EBMSPartnershipData(someLogger, adminData, pData);
      sender.setExecuteOperation(PartnershipOp.Add);
      sender.run();

   \ **Note for setting the manage partnership end-point**\  You should add /admin/ebms/partnership to your H2O host. For example, 'http://localhost:8080/admin/ebms/partnership'. \ **Technical Information**\  The \ ``EBMSPartnershipSender``\  will generate a HTTP multi-part request to the manage partnership end-point. The request includes all parameter extracted from the \ ``EBMSPartnershipData``\ , each of them is represented as either text/plain multi-part, or application binary multi-part (for the \ ``certificates``\ ). The type of partnership operation to execute also append at the end of the HTTP request in a text multi-part form.

   :author: Twinsen Tsang

   **See also:** :java:ref:`hk.hku.cecid.corvus.ws.data.EBMSAdminData`, :java:ref:`hk.hku.cecid.corvus.ws.data.EBMSPartnershipData`, :java:ref:`hk.hku.cecid.corvus.http.PartnershipOp`

Fields
------
PARTNERSHIP_DATA_2_FROM_PARAM_NAME_MAPPING
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final Map PARTNERSHIP_DATA_2_FROM_PARAM_NAME_MAPPING
   :outertype: EBMSPartnershipSender

PARTNERSHIP_OP_2_WORD
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final Map PARTNERSHIP_OP_2_WORD
   :outertype: EBMSPartnershipSender

Constructors
------------
EBMSPartnershipSender
^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EBMSPartnershipSender(FileLogger logger, EBMSAdminData ad, EBMSPartnershipData p)
   :outertype: EBMSPartnershipSender

   Explicit Constructor. Create an instance of \ ``EBMSPartnershipSender``\

   :param logger: The logger for log the sending process.
   :param ad: The \ ``EBMSAdminData``\  for locating the HTTP end-point the request send to.
   :param p: The \ ``EBMSPartnershipData``\

Methods
-------
getPartnershipMapping
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public Map getPartnershipMapping()
   :outertype: EBMSPartnershipSender

getPartnershipOperationMapping
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public Map getPartnershipOperationMapping()
   :outertype: EBMSPartnershipSender

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: EBMSPartnershipSender

   The main method is for CLI mode.

run
^^^

.. java:method:: public void run()
   :outertype: EBMSPartnershipSender

   The main method for executing the partnership operation request.

   **See also:** :java:ref:`hk.hku.cecid.corvus.http.HttpSender.run()`

