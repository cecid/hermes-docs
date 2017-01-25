.. java:import:: java.util Properties

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

ActiveModule
============

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public abstract class ActiveModule extends Module implements Runnable

   ActiveModule is a runnable module which runs as a separated thread after started. Subclasses are expected to implement the run() method in the Runnable interface.

   :author: Hugo Y. K. Lam

Constructors
------------
ActiveModule
^^^^^^^^^^^^

.. java:constructor:: public ActiveModule(String descriptorLocation)
   :outertype: ActiveModule

   Creates a new instance of ActiveModule.

   :param descriptorLocation: the module descriptor.
   :throws ModuleException: if errors encountered when loading the module descriptor.

ActiveModule
^^^^^^^^^^^^

.. java:constructor:: public ActiveModule(String descriptorLocation, boolean shouldInitialize)
   :outertype: ActiveModule

   Creates a new instance of ActiveModule.

   :param descriptorLocation: the module descriptor.
   :param shouldInitialize: true if the module should be initialized.
   :throws ModuleException: if errors encountered when loading the module descriptor.

ActiveModule
^^^^^^^^^^^^

.. java:constructor:: public ActiveModule(String descriptorLocation, ClassLoader loader)
   :outertype: ActiveModule

   Creates a new instance of ActiveModule.

   :param descriptorLocation: the module descriptor.
   :param loader: the class loader for this module.
   :throws ModuleException: if errors encountered when loading the module descriptor.

ActiveModule
^^^^^^^^^^^^

.. java:constructor:: public ActiveModule(String descriptorLocation, ClassLoader loader, boolean shouldInitialize)
   :outertype: ActiveModule

   Creates a new instance of ActiveModule.

   :param descriptorLocation: the module descriptor.
   :param loader: the class loader for this module.
   :param shouldInitialize: true if the module should be initialized.
   :throws ModuleException: if errors encountered when loading the module descriptor.

Methods
-------
execute
^^^^^^^

.. java:method:: public abstract boolean execute()
   :outertype: ActiveModule

   Invoked by the run() method to execute this module's job.

   :return: true if this method should be invoked again after a defined interval.

getThread
^^^^^^^^^

.. java:method:: public Thread getThread()
   :outertype: ActiveModule

   Gets the thread of this module.

   :return: the thread of this module.

init
^^^^

.. java:method:: public void init()
   :outertype: ActiveModule

   Initializes this module by the following module parameters:

   ..

   * group-execution: all - started and stopped by its group; start - only started by its group; stop - only stopped by its group; none - not started or stopped by its group.
   * execution-interval: the interval (milliseconds) that this module should wait until the next execution. A negative number indicates a one-time execution.
   * stop-timeout: the maximum time (milliseconds) to wait for stopping this module.

isGroupStart
^^^^^^^^^^^^

.. java:method:: public boolean isGroupStart()
   :outertype: ActiveModule

   Checks if this module should be started by its group, if any.

   :return: true if this module should be started by its group.

isGroupStop
^^^^^^^^^^^

.. java:method:: public boolean isGroupStop()
   :outertype: ActiveModule

   Checks if this module should be stopped by its group, if any.

   :return: true if this module should be stopped by its group.

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: ActiveModule

   Invoked when this module starts.

   **See also:** :java:ref:`.start()`

onStop
^^^^^^

.. java:method:: public void onStop()
   :outertype: ActiveModule

   Invoked when this module stops.

   **See also:** :java:ref:`.stop()`

run
^^^

.. java:method:: public void run()
   :outertype: ActiveModule

   Invoked by the start() method and will continuously call the execute() method to carry out the execution. This method should not be invoked directly.

   **See also:** :java:ref:`.start()`, :java:ref:`.execute()`, :java:ref:`java.lang.Runnable.run()`

setExecutionInterval
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setExecutionInterval(long newInterval)
   :outertype: ActiveModule

   Set the execution interval in the module.

start
^^^^^

.. java:method:: public synchronized void start()
   :outertype: ActiveModule

   Starts this module. This method will invoke onStart() before starting its own thread.

   **See also:** :java:ref:`java.lang.Thread.start()`, :java:ref:`.onStart()`

stop
^^^^

.. java:method:: public synchronized void stop()
   :outertype: ActiveModule

   Stops this module. This method will invoke onStop() before waiting for its thread to die.

   **See also:** :java:ref:`.waitForStop()`, :java:ref:`.onStop()`

waitForStop
^^^^^^^^^^^

.. java:method:: public synchronized void waitForStop()
   :outertype: ActiveModule

   Waits for this module's thread to die.

