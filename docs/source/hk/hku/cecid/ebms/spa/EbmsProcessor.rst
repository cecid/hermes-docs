.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.module ModuleException

.. java:import:: hk.hku.cecid.piazza.commons.module ModuleGroup

.. java:import:: hk.hku.cecid.piazza.commons.module SystemModule

.. java:import:: hk.hku.cecid.piazza.commons.security KeyStoreManager

.. java:import:: hk.hku.cecid.piazza.commons.spa Plugin

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginException

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginHandler

EbmsProcessor
=============

.. java:package:: hk.hku.cecid.ebms.spa
   :noindex:

.. java:type:: public class EbmsProcessor implements PluginHandler

   :author: Donahue Sze

Fields
------
ACTIVE_MODULE_INBOX_COLLECTOR
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String ACTIVE_MODULE_INBOX_COLLECTOR
   :outertype: EbmsProcessor

   Inbox collector active task module ID name

ACTIVE_MODULE_MAIL_COLLECTOR
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String ACTIVE_MODULE_MAIL_COLLECTOR
   :outertype: EbmsProcessor

   POP mail collector active task module ID name

ACTIVE_MODULE_OUTBOX_COLLECTOR
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String ACTIVE_MODULE_OUTBOX_COLLECTOR
   :outertype: EbmsProcessor

   Outbox collector active task module ID name

core
^^^^

.. java:field:: public static SystemModule core
   :outertype: EbmsProcessor

Methods
-------
getKeyStoreManagerForDecryption
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static KeyStoreManager getKeyStoreManagerForDecryption()
   :outertype: EbmsProcessor

getKeyStoreManagerForSignature
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static KeyStoreManager getKeyStoreManagerForSignature()
   :outertype: EbmsProcessor

getModuleGroup
^^^^^^^^^^^^^^

.. java:method:: public static ModuleGroup getModuleGroup()
   :outertype: EbmsProcessor

   :return: the Ebms module group

processActivation
^^^^^^^^^^^^^^^^^

.. java:method:: public void processActivation(Plugin plugin) throws PluginException
   :outertype: EbmsProcessor

processDeactivation
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void processDeactivation(Plugin arg0) throws PluginException
   :outertype: EbmsProcessor

