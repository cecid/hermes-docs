.. java:import:: java.util Vector

ActiveMonitor
=============

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public class ActiveMonitor

   ActiveMonitor is a thread monitor of active threads.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`ActiveThread`

Constructors
------------
ActiveMonitor
^^^^^^^^^^^^^

.. java:constructor:: public ActiveMonitor()
   :outertype: ActiveMonitor

   Creares a new instance of ActiveMonitor.

Methods
-------
acquireThread
^^^^^^^^^^^^^

.. java:method:: public synchronized ActiveThread acquireThread()
   :outertype: ActiveMonitor

   Acquires a new active thread. This method will block if the maximum number of threads has been reached.

   :return: a new active thread or null if the monitor is suspended.

getMaxThreadCount
^^^^^^^^^^^^^^^^^

.. java:method:: public int getMaxThreadCount()
   :outertype: ActiveMonitor

   Gets the maximum number of threads this monitor allows to acquire.

   :return: the maximum number.

getPeekThreadCount
^^^^^^^^^^^^^^^^^^

.. java:method:: public int getPeekThreadCount()
   :outertype: ActiveMonitor

   Gets the peek number of threads being acquired.

   :return: the peek number of threads being acquired.

getThreadCount
^^^^^^^^^^^^^^

.. java:method:: public int getThreadCount()
   :outertype: ActiveMonitor

   Gets the current number of threads being acquired.

   :return: the current number of threads being acquired.

releaseThread
^^^^^^^^^^^^^

.. java:method:: public synchronized void releaseThread(ActiveThread thread)
   :outertype: ActiveMonitor

   Releases a previously acquired thread.

   :param thread: the previously acquired thread.

resume
^^^^^^

.. java:method:: public synchronized void resume()
   :outertype: ActiveMonitor

   Resumes this monitor.

setMaxThreadCount
^^^^^^^^^^^^^^^^^

.. java:method:: public void setMaxThreadCount(int maxThreadCount)
   :outertype: ActiveMonitor

   Sets the maximum number of threads this monitor allows to acquire.

   :param maxThreadCount: the maximum number.

suspend
^^^^^^^

.. java:method:: public synchronized void suspend()
   :outertype: ActiveMonitor

   Suspends this monitor.

   **See also:** :java:ref:`.waitForEmpty()`

waitForEmpty
^^^^^^^^^^^^

.. java:method:: public synchronized void waitForEmpty()
   :outertype: ActiveMonitor

   Waits until all the acquired threads have been released.

