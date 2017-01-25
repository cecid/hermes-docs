.. java:import:: hk.hku.cecid.edi.as2 AS2Exception

.. java:import:: hk.hku.cecid.edi.as2 AS2PlusProcessor

.. java:import:: hk.hku.cecid.edi.as2.dao PartnershipDAO

.. java:import:: hk.hku.cecid.edi.as2.dao PartnershipDVO

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: hk.hku.cecid.piazza.commons.module ActiveTask

.. java:import:: javax.activation FileDataSource

OutgoingPayloadTask
===================

.. java:package:: hk.hku.cecid.edi.as2.module
   :noindex:

.. java:type:: public class OutgoingPayloadTask implements ActiveTask

   OutgoingPayloadTask

   :author: Hugo Y. K. Lam

Constructors
------------
OutgoingPayloadTask
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public OutgoingPayloadTask(PayloadCache payload) throws AS2Exception
   :outertype: OutgoingPayloadTask

   :throws AS2Exception:

Methods
-------
execute
^^^^^^^

.. java:method:: public void execute() throws Exception
   :outertype: OutgoingPayloadTask

   execute

   :throws Exception:

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.execute()`

getMaxRetries
^^^^^^^^^^^^^

.. java:method:: public int getMaxRetries()
   :outertype: OutgoingPayloadTask

   getMaxRetries

   :return: int

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.getMaxRetries()`

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public long getRetryInterval()
   :outertype: OutgoingPayloadTask

   getRetryInterval

   :return: long

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.getRetryInterval()`

isRetryEnabled
^^^^^^^^^^^^^^

.. java:method:: public boolean isRetryEnabled()
   :outertype: OutgoingPayloadTask

   isRetryEnabled

   :return: boolean

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.isRetryEnabled()`

isSucceedFast
^^^^^^^^^^^^^

.. java:method:: public boolean isSucceedFast()
   :outertype: OutgoingPayloadTask

   isSucceedFast

   :return: boolean

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.isSucceedFast()`

onAwake
^^^^^^^

.. java:method:: public void onAwake()
   :outertype: OutgoingPayloadTask

   onAwake

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.onAwake()`

onFailure
^^^^^^^^^

.. java:method:: public void onFailure(Throwable e)
   :outertype: OutgoingPayloadTask

   onFailure

   :param e:

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.onFailure(java.lang.Throwable)`

setRetried
^^^^^^^^^^

.. java:method:: public void setRetried(int retried)
   :outertype: OutgoingPayloadTask

   setRetried

   :param retried:

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.setRetried(int)`

