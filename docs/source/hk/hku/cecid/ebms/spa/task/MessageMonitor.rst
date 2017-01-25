.. java:import:: java.util Date

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.module ActiveModule

.. java:import:: hk.hku.cecid.piazza.commons.module ModuleException

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageClassifier

MessageMonitor
==============

.. java:package:: hk.hku.cecid.ebms.spa.task
   :noindex:

.. java:type:: public class MessageMonitor extends ActiveModule

   The \ ``MessageMonitor``\  is a monitor which correct all Creation Date: 14/05/2007

   :author: Twinsen Tsang

Constructors
------------
MessageMonitor
^^^^^^^^^^^^^^

.. java:constructor:: public MessageMonitor(String descriptorLocation, ClassLoader loader, boolean shouldInitialize)
   :outertype: MessageMonitor

   Creates a new instance of MessageMonitor.

   :param descriptorLocation: the module descriptor.
   :param loader: the class loader for this module.
   :param shouldInitialize: true if the module should be initialized.
   :throws ModuleException: if errors encountered when loading the module descriptor.

Methods
-------
execute
^^^^^^^

.. java:method:: public boolean execute()
   :outertype: MessageMonitor

   The method is invoked constantly with interval defined in the configuration descriptor or 60 second by default. It update the status of all timed-out message to PENDING so that they can be re-sending by Outbox Collector.

   :return: true if this method should be invoked again after a defined interval.

   **See also:** :java:ref:`hk.hku.cecid.ebms.spa.task.OutboxCollector`, :java:ref:`hk.hku.cecid.ebms.spa.task.OutboxTask`

init
^^^^

.. java:method:: public void init()
   :outertype: MessageMonitor

   Invoke for initialization.

initialize
^^^^^^^^^^

.. java:method:: public void initialize()
   :outertype: MessageMonitor

   Post/Lazy initialization. This method is invoked at the firs time only this module execute. The purpose of this can guarantee the DAO Factory has been initialized successfully before creating it.

