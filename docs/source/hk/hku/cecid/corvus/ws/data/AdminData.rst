.. java:import:: hk.hku.cecid.corvus.http PartnershipOp

.. java:import:: hk.hku.cecid.corvus.ws.data KVPairData

AdminData
=========

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: abstract class AdminData extends KVPairData

   The \ ``AdminData``\  is

   :author: Twinsen Tsang

Fields
------
CONFIG_KEY_SET
^^^^^^^^^^^^^^

.. java:field:: public static final String[] CONFIG_KEY_SET
   :outertype: AdminData

   This is the configuration key set for XML serialization / de-serialization.

PARAM_KEY_SET
^^^^^^^^^^^^^

.. java:field:: public static final String[] PARAM_KEY_SET
   :outertype: AdminData

   For consistent, used for \ :java:ref:`DataFactory.createEBMSAdminDataFromXML(hk.hku.cecid.piazza.commons.util.PropertyTree)`\

Constructors
------------
AdminData
^^^^^^^^^

.. java:constructor:: public AdminData(int maxCapacity)
   :outertype: AdminData

   Default constructor.

Methods
-------
getEnvelopQueryEndpoint
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getEnvelopQueryEndpoint()
   :outertype: AdminData

   :return: The end-point for query the message envelop of EBMS partnership.

getManagePartnershipEndpoint
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getManagePartnershipEndpoint()
   :outertype: AdminData

   :return: The end-point for managing the set of EBMS partnership.

getMessageBoxCriteria
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getMessageBoxCriteria()
   :outertype: AdminData

   [USED ONLY BY EnvelopQuerySender]

   :return: the message box acting as the criteria for search the message envelop.

getMessageIdCriteria
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getMessageIdCriteria()
   :outertype: AdminData

   [USED ONLY BY EnvelopQuerySender]

   :return: the message id acting as the criteria for search the message envelop.

getPartnershipOperation
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int getPartnershipOperation()
   :outertype: AdminData

   [USED ONLY BY PartnershipSender]

   :throws NumberFormatException: If the data format of the value of partnership operation is invalid.
   :return: The partnership operation you have set, either 0, 1, 2.

getPassword
^^^^^^^^^^^

.. java:method:: public char[] getPassword()
   :outertype: AdminData

   :return: The password for authenticate the administrator page.

getUsername
^^^^^^^^^^^

.. java:method:: public String getUsername()
   :outertype: AdminData

   :return: The user name for authenticate administrator page.

setEnvelopQueryEndpoint
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setEnvelopQueryEndpoint(String envelopQueryEndpoint)
   :outertype: AdminData

   Set the end-point for query the message envelop of EBMS partnership.

   :param envelopQueryEndpoint: The end-point for query the message envelop of EBMS partnership.

setManagePartnershipEndpoint
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setManagePartnershipEndpoint(String manPartnershipEndpoint)
   :outertype: AdminData

   Set the end-point for managing the set of EBMS partnership.

   :param manPartnershipEndpoint: The end-point for managing the set of EBMS partnership.

setMessageBoxCriteria
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setMessageBoxCriteria(String messageBox)
   :outertype: AdminData

   [USED ONLY BY EnvelopQuerySender] Set the message box acting as the criteria for search the message envelop.

   :param messageBox: the message box acting as the criteria for search the message envelop.

setMessageIdCriteria
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setMessageIdCriteria(String messageId)
   :outertype: AdminData

   [USED ONLY BY EnvelopQuerySender] Set the message id acting as the criteria for search the message envelop.

   :param messageId: the message id acting as the criteria for search the message envelop.

setPartnershipOperation
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setPartnershipOperation(int pOp)
   :outertype: AdminData

   [USED ONLY BY PartnershipSender]

   :param pOp: The partnership operation you want to set, either 0, 1, 2.

   **See also:** :java:ref:`hk.hku.cecid.corvus.http.PartnershipOp`, :java:ref:`hk.hku.cecid.corvus.http.EBMSPartnershipSender`

setPassword
^^^^^^^^^^^

.. java:method:: public void setPassword(String password)
   :outertype: AdminData

   :param password: the password for authenticate administrator page

setUsername
^^^^^^^^^^^

.. java:method:: public void setUsername(String username)
   :outertype: AdminData

   :param username: The user name for authenticate administrator page.

