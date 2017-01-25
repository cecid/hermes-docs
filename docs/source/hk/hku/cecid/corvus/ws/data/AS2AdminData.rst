.. java:import:: hk.hku.cecid.corvus.http PartnershipOp

AS2AdminData
============

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class AS2AdminData extends AdminData

   The \ ``EBMSAdminData``\  is data structure for holding the administration data for EbMS plugin.

   :author: Twinsen Tsang

Fields
------
CONFIG_PREFIX
^^^^^^^^^^^^^

.. java:field:: public static final String CONFIG_PREFIX
   :outertype: AS2AdminData

   This is the configuration prefix for serialization / de-serialization.

PARAM_PREFIX
^^^^^^^^^^^^

.. java:field:: public static final String PARAM_PREFIX
   :outertype: AS2AdminData

   This is the parameter prefix for serialzation / de-serialization.

Constructors
------------
AS2AdminData
^^^^^^^^^^^^

.. java:constructor:: public AS2AdminData()
   :outertype: AS2AdminData

   Create an instance of \ ``EBMSAdminData``\  with default value.

   ..

   #. Username : corvus
   #. Password : corvus
   #. Manage Partnership End-point : http://localhost:8080/corvus/admin/as2/partnership
   #. Envelop Query End-point : http://localhost:8080/corvus/admin/as2/repository
   #. Partnership Operation : 1
   #. Message Box Criteria: INBOX
   #. Message ID Criteria: changem-messageid

