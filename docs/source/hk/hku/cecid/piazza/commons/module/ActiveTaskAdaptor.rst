ActiveTaskAdaptor
=================

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public class ActiveTaskAdaptor implements ActiveTask

   A Active Task Adaptor is a dummy class for the interface active task. Creation Date: 24/10/2006.

   :author: Twinsen Tsang

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask`

Methods
-------
execute
^^^^^^^

.. java:method:: public void execute() throws Exception
   :outertype: ActiveTaskAdaptor

getMaxRetries
^^^^^^^^^^^^^

.. java:method:: public int getMaxRetries()
   :outertype: ActiveTaskAdaptor

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public long getRetryInterval()
   :outertype: ActiveTaskAdaptor

isRetryEnabled
^^^^^^^^^^^^^^

.. java:method:: public boolean isRetryEnabled()
   :outertype: ActiveTaskAdaptor

isSucceedFast
^^^^^^^^^^^^^

.. java:method:: public boolean isSucceedFast()
   :outertype: ActiveTaskAdaptor

onAwake
^^^^^^^

.. java:method:: public void onAwake()
   :outertype: ActiveTaskAdaptor

onFailure
^^^^^^^^^

.. java:method:: public void onFailure(Throwable e)
   :outertype: ActiveTaskAdaptor

setRetried
^^^^^^^^^^

.. java:method:: public void setRetried(int retried)
   :outertype: ActiveTaskAdaptor

