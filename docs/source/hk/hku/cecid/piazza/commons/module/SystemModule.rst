.. java:import:: hk.hku.cecid.piazza.commons.dao DAOFactory

.. java:import:: hk.hku.cecid.piazza.commons.util Logger

.. java:import:: hk.hku.cecid.piazza.commons.util Messages

.. java:import:: hk.hku.cecid.piazza.commons.util PropertySheet

SystemModule
============

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public class SystemModule extends Module

   SystemModule is a module which contains some utility members which are common to a system.

   :author: Hugo Y. K. Lam

Fields
------
dao
^^^

.. java:field:: public final DAOFactory dao
   :outertype: SystemModule

   The system DAO factory, having a component name 'daofactory'.

log
^^^

.. java:field:: public final Logger log
   :outertype: SystemModule

   The system logger, having a component name 'logger'.

messages
^^^^^^^^

.. java:field:: public final Messages messages
   :outertype: SystemModule

   The system messages, having a component name 'messages'.

properties
^^^^^^^^^^

.. java:field:: public final PropertySheet properties
   :outertype: SystemModule

   The system properties, having a component name 'properties'.

Constructors
------------
SystemModule
^^^^^^^^^^^^

.. java:constructor:: public SystemModule(String descriptorLocation)
   :outertype: SystemModule

   Creates a new instance of SystemModule.

   :param descriptorLocation: the module descriptor.
   :throws ModuleException: if errors encountered when loading the module descriptor.

SystemModule
^^^^^^^^^^^^

.. java:constructor:: public SystemModule(String descriptorLocation, boolean shouldInitialize)
   :outertype: SystemModule

   Creates a new instance of SystemModule.

   :param descriptorLocation: the module descriptor.
   :param shouldInitialize: true if the module should be initialized.
   :throws ModuleException: if errors encountered when loading the module descriptor.

SystemModule
^^^^^^^^^^^^

.. java:constructor:: public SystemModule(String descriptorLocation, ClassLoader loader)
   :outertype: SystemModule

   Creates a new instance of SystemModule.

   :param descriptorLocation: the module descriptor.
   :param loader: the class loader for this module.
   :throws ModuleException: if errors encountered when loading the module descriptor.

SystemModule
^^^^^^^^^^^^

.. java:constructor:: public SystemModule(String descriptorLocation, ClassLoader loader, boolean shouldInitialize)
   :outertype: SystemModule

   Creates a new instance of SystemModule.

   :param descriptorLocation: the module descriptor.
   :param loader: the class loader for this module.
   :param shouldInitialize: true if the module should be initialized.
   :throws ModuleException: if errors encountered when loading the module descriptor.

Methods
-------
getLogger
^^^^^^^^^

.. java:method:: public Logger getLogger()
   :outertype: SystemModule

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.Module.getLogger()`

