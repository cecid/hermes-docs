.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: java.util Iterator

.. java:import:: java.util Properties

ActiveTaskModule
================

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public class ActiveTaskModule extends ActiveModule

   ActiveTaskModule is an active module which manages an active task list. As an active module, it runs as a separated thread and loops through the task list for executing the tasks. It also contains an active monitor responsible for monitoring and controlling the thread count.

   :author: Hugo Y. K. Lam

Constructors
------------
ActiveTaskModule
^^^^^^^^^^^^^^^^

.. java:constructor:: public ActiveTaskModule(String descriptorLocation)
   :outertype: ActiveTaskModule

   Creates a new instance of ActiveTaskModule.

   :param descriptorLocation: the module descriptor.
   :throws ModuleException: when errors encountered when loading the module descriptor.

ActiveTaskModule
^^^^^^^^^^^^^^^^

.. java:constructor:: public ActiveTaskModule(String descriptorLocation, boolean shouldInitialize)
   :outertype: ActiveTaskModule

   Creates a new instance of ActiveTaskModule.

   :param descriptorLocation: the module descriptor.
   :param shouldInitialize: true if the module should be initialized.
   :throws ModuleException: when errors encountered when loading the module descriptor.

ActiveTaskModule
^^^^^^^^^^^^^^^^

.. java:constructor:: public ActiveTaskModule(String descriptorLocation, ClassLoader loader)
   :outertype: ActiveTaskModule

   Creates a new instance of ActiveTaskModule.

   :param descriptorLocation: the module descriptor.
   :param loader: the class loader for this module.
   :throws ModuleException: when errors encountered when loading the module descriptor.

ActiveTaskModule
^^^^^^^^^^^^^^^^

.. java:constructor:: public ActiveTaskModule(String descriptorLocation, ClassLoader loader, boolean shouldInitialize)
   :outertype: ActiveTaskModule

   Creates a new instance of ActiveTaskModule.

   :param descriptorLocation: the module descriptor.
   :param loader: the class loader for this module.
   :param shouldInitialize: true if the module should be initialized.
   :throws ModuleException: when errors encountered when loading the module descriptor.

Methods
-------
execute
^^^^^^^

.. java:method:: public boolean execute()
   :outertype: ActiveTaskModule

   Invoked by the start() method to start executing the managed task list and its tasks.

   :return: true if the active monitor of this module is not suspended.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveModule.execute()`

getMonitor
^^^^^^^^^^

.. java:method:: public ActiveMonitor getMonitor()
   :outertype: ActiveTaskModule

   Gets the monitor of this module.

   :return: the monitor of this module.

init
^^^^

.. java:method:: public void init()
   :outertype: ActiveTaskModule

   Initializes this module by loading the active task list component named "task-list". The component may have the following parameters:

   ..

   * max-thread-count: the maximum number of threads which can be acquired to execute the tasks in the task list. A number smaller than 1 indicates the tasks should be run under the same thread as this module.
   * wait-for-list: true if the tasks in the task list should be completely executed before being refreshed.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.Module.init()`

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: ActiveTaskModule

   Resumes the active monitor so that new threads can be acquired for executing tasks.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveModule.start()`, :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveModule.onStart()`

onStop
^^^^^^

.. java:method:: public void onStop()
   :outertype: ActiveTaskModule

   Suspends the active monitor so that no more threads can be acquired for executing tasks.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveModule.stop()`, :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveModule.onStop()`

