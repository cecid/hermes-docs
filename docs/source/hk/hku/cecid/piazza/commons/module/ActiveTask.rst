ActiveTask
==========

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public interface ActiveTask

   ActiveTask represents a task which can be executed under a separated thread.

   :author: Hugo Y. K. Lam

Methods
-------
execute
^^^^^^^

.. java:method:: public void execute() throws Exception
   :outertype: ActiveTask

   Executes this task.

   :throws Exception: if unable to carry out the task.

getMaxRetries
^^^^^^^^^^^^^

.. java:method:: public int getMaxRetries()
   :outertype: ActiveTask

   Gets the maximum number of retries.

   :return: the maximum number of retries.

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public long getRetryInterval()
   :outertype: ActiveTask

   Gets the retry interval in milliseconds.

   :return: the retry interval.

isRetryEnabled
^^^^^^^^^^^^^^

.. java:method:: public boolean isRetryEnabled()
   :outertype: ActiveTask

   Indicates if retry should be enabled.

   :return: true if retry should be enabled.

isSucceedFast
^^^^^^^^^^^^^

.. java:method:: public boolean isSucceedFast()
   :outertype: ActiveTask

   Indicates if the task should succeed fast. false if this task should be retried depending solely on the indication of isRetryEnabled().

   :return: true if the task should succeed fast.

   **See also:** :java:ref:`.isRetryEnabled()`

onAwake
^^^^^^^

.. java:method:: public void onAwake()
   :outertype: ActiveTask

   Invoked when the retry interval has passed and before execution.

onFailure
^^^^^^^^^

.. java:method:: public void onFailure(Throwable e)
   :outertype: ActiveTask

   Invoked when there is any exception thrown from the execution.

   :param e: the exception cause.

setRetried
^^^^^^^^^^

.. java:method:: public void setRetried(int retried)
   :outertype: ActiveTask

   Sets the number of times this task has been retried.

   :param retried: the number of times this task has been retried.

