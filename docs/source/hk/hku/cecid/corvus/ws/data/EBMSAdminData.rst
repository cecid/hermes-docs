EBMSAdminData
=============

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class EBMSAdminData extends AdminData

   The \ ``EBMSAdminData``\  is data structure for holding the administration data for EbMS plugin.

   :author: Twinsen Tsang

Fields
------
CONFIG_PREFIX
^^^^^^^^^^^^^

.. java:field:: public static final String CONFIG_PREFIX
   :outertype: EBMSAdminData

   This is the configuration prefix for serialization / de-serialization.

PARAM_PREFIX
^^^^^^^^^^^^

.. java:field:: public static final String PARAM_PREFIX
   :outertype: EBMSAdminData

   This is the parameter prefix for serialization / de-serialization.

Constructors
------------
EBMSAdminData
^^^^^^^^^^^^^

.. java:constructor:: public EBMSAdminData()
   :outertype: EBMSAdminData

   Create an instance of \ ``EBMSAdminData``\  with default value.

   ..

   #. User-name: corvus
   #. Password : corvus
   #. Manage Partnership End-point : http://localhost:8080/corvus/admin/ebms/partnership
   #. Envelop Query End-point : http://localhost:8080/corvus/admin/ebms/repository
   #. Partnership Operation : 1
   #. Message Box Criteria: INBOX
   #. Message ID Criteria: changme-messageid

