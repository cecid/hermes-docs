.. java:import:: hk.hku.cecid.edi.as2.dao AS2DAOHandler

.. java:import:: hk.hku.cecid.edi.as2.module IncomingMessageProcessor

.. java:import:: hk.hku.cecid.edi.as2.module OutgoingMessageProcessor

.. java:import:: hk.hku.cecid.edi.as2.module PayloadRepository

.. java:import:: hk.hku.cecid.piazza.commons.module ModuleException

.. java:import:: hk.hku.cecid.piazza.commons.module ModuleGroup

.. java:import:: hk.hku.cecid.piazza.commons.module PluginProcessor

.. java:import:: hk.hku.cecid.piazza.commons.security KeyStoreManager

.. java:import:: hk.hku.cecid.piazza.commons.spa Plugin

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginException

.. java:import:: javax.activation CommandMap

.. java:import:: javax.activation MailcapCommandMap

AS2PlusProcessor
================

.. java:package:: hk.hku.cecid.edi.as2
   :noindex:

.. java:type:: public class AS2PlusProcessor extends PluginProcessor

   AS2Processor

   :author: Hugo Y. K. Lam

Methods
-------
getIncomingMessageProcessor
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public IncomingMessageProcessor getIncomingMessageProcessor()
   :outertype: AS2PlusProcessor

getInstance
^^^^^^^^^^^

.. java:method:: public static AS2PlusProcessor getInstance()
   :outertype: AS2PlusProcessor

getKeyStoreManager
^^^^^^^^^^^^^^^^^^

.. java:method:: public KeyStoreManager getKeyStoreManager()
   :outertype: AS2PlusProcessor

getModuleGroupImpl
^^^^^^^^^^^^^^^^^^

.. java:method:: @Override protected ModuleGroup getModuleGroupImpl()
   :outertype: AS2PlusProcessor

getOutgoingMessageProcessor
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public OutgoingMessageProcessor getOutgoingMessageProcessor()
   :outertype: AS2PlusProcessor

getOutgoingPayloadRepository
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public PayloadRepository getOutgoingPayloadRepository()
   :outertype: AS2PlusProcessor

processActivation
^^^^^^^^^^^^^^^^^

.. java:method:: public void processActivation(Plugin plugin) throws PluginException
   :outertype: AS2PlusProcessor

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.PluginHandler.processActivation(hk.hku.cecid.piazza.commons.spa.Plugin)`

setModuleGroupImpl
^^^^^^^^^^^^^^^^^^

.. java:method:: @Override protected void setModuleGroupImpl(ModuleGroup moduleGroup)
   :outertype: AS2PlusProcessor

