ActiveThread
============

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public class ActiveThread implements Runnable

   ActiveThread is a thread which executes its associated task and manages the retry of the task. An active thread may or may not be managed by an active monitor.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`ActiveTask`, :java:ref:`ActiveMonitor`

Constructors
------------
ActiveThread
^^^^^^^^^^^^

.. java:constructor:: public ActiveThread()
   :outertype: ActiveThread

   Creates a new instance of ActiveThread.

ActiveThread
^^^^^^^^^^^^

.. java:constructor:: public ActiveThread(ActiveMonitor monitor)
   :outertype: ActiveThread

   Creates a new instance of ActiveThread.

   :param monitor: the active monitor from which this active thread is acquired.

Methods
-------
getTask
^^^^^^^

.. java:method:: public ActiveTask getTask()
   :outertype: ActiveThread

   Gets the active task of this thread.

   :return: the active task of this thread.

run
^^^

.. java:method:: public void run()
   :outertype: ActiveThread

   Executes its associated task and manages the retry of the task.

   **See also:** :java:ref:`java.lang.Runnable.run()`

setTask
^^^^^^^

.. java:method:: public void setTask(ActiveTask task)
   :outertype: ActiveThread

   Sets the active task of this thread.

   :param task: the active task to be executed.

start
^^^^^

.. java:method:: public void start()
   :outertype: ActiveThread

   Starts a new thread to execute the associated task.

   **See also:** :java:ref:`.run()`

