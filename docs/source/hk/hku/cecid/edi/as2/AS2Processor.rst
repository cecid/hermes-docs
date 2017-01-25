.. java:import:: hk.hku.cecid.edi.as2.dao AS2DAOHandler

.. java:import:: hk.hku.cecid.edi.as2.module IncomingMessageProcessor

.. java:import:: hk.hku.cecid.edi.as2.module MessageRepository

.. java:import:: hk.hku.cecid.edi.as2.module PayloadRepository

.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.module ModuleException

.. java:import:: hk.hku.cecid.piazza.commons.module ModuleGroup

.. java:import:: hk.hku.cecid.piazza.commons.module SystemModule

.. java:import:: hk.hku.cecid.piazza.commons.security KeyStoreManager

.. java:import:: hk.hku.cecid.piazza.commons.spa Plugin

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginException

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginHandler

.. java:import:: javax.activation CommandMap

.. java:import:: javax.activation MailcapCommandMap

AS2Processor
============

.. java:package:: hk.hku.cecid.edi.as2
   :noindex:

.. java:type:: public class AS2Processor implements PluginHandler

   AS2Processor

   :author: Hugo Y. K. Lam

Fields
------
core
^^^^

.. java:field:: public static SystemModule core
   :outertype: AS2Processor

Methods
-------
getIncomingMessageProcessor
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static IncomingMessageProcessor getIncomingMessageProcessor()
   :outertype: AS2Processor

getIncomingPayloadRepository
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static PayloadRepository getIncomingPayloadRepository()
   :outertype: AS2Processor

getKeyStoreManager
^^^^^^^^^^^^^^^^^^

.. java:method:: public static KeyStoreManager getKeyStoreManager()
   :outertype: AS2Processor

getMessageRepository
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static MessageRepository getMessageRepository()
   :outertype: AS2Processor

getModuleGroup
^^^^^^^^^^^^^^

.. java:method:: public static ModuleGroup getModuleGroup()
   :outertype: AS2Processor

getOutgoingPayloadRepository
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static PayloadRepository getOutgoingPayloadRepository()
   :outertype: AS2Processor

getSystemModule
^^^^^^^^^^^^^^^

.. java:method:: public static SystemModule getSystemModule()
   :outertype: AS2Processor

processActivation
^^^^^^^^^^^^^^^^^

.. java:method:: public void processActivation(Plugin plugin) throws PluginException
   :outertype: AS2Processor

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.PluginHandler.processActivation(hk.hku.cecid.piazza.commons.spa.Plugin)`

processDeactivation
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void processDeactivation(Plugin plugin) throws PluginException
   :outertype: AS2Processor

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.PluginHandler.processDeactivation(hk.hku.cecid.piazza.commons.spa.Plugin)`

