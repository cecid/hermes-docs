.. java:import:: hk.hku.cecid.edi.as2 AS2Exception

.. java:import:: hk.hku.cecid.edi.as2 AS2PlusProcessor

.. java:import:: hk.hku.cecid.edi.as2.dao AS2DAOHandler

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDVO

.. java:import:: hk.hku.cecid.edi.as2.dao RepositoryDAO

.. java:import:: hk.hku.cecid.edi.as2.dao RepositoryDVO

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: hk.hku.cecid.piazza.commons.module ActiveTask

.. java:import:: java.io ByteArrayInputStream

IncomingMessageTask
===================

.. java:package:: hk.hku.cecid.edi.as2.module
   :noindex:

.. java:type:: public class IncomingMessageTask implements ActiveTask

   OutgoingMessageTask

   :author: Hugo Y. K. Lam

Constructors
------------
IncomingMessageTask
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public IncomingMessageTask(MessageDVO messageData) throws AS2Exception
   :outertype: IncomingMessageTask

   :throws AS2Exception:

Methods
-------
execute
^^^^^^^

.. java:method:: public void execute() throws Exception
   :outertype: IncomingMessageTask

   execute

   :throws Exception:

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.execute()`

getMaxRetries
^^^^^^^^^^^^^

.. java:method:: public int getMaxRetries()
   :outertype: IncomingMessageTask

   getMaxRetries

   :return: int

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.getMaxRetries()`

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public long getRetryInterval()
   :outertype: IncomingMessageTask

   getRetryInterval

   :return: long

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.getRetryInterval()`

isRetryEnabled
^^^^^^^^^^^^^^

.. java:method:: public boolean isRetryEnabled()
   :outertype: IncomingMessageTask

   isRetryEnabled

   :return: boolean

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.isRetryEnabled()`

isSucceedFast
^^^^^^^^^^^^^

.. java:method:: public boolean isSucceedFast()
   :outertype: IncomingMessageTask

   isSucceedFast

   :return: boolean

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.isSucceedFast()`

onAwake
^^^^^^^

.. java:method:: public void onAwake()
   :outertype: IncomingMessageTask

   onAwake

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.onAwake()`

onFailure
^^^^^^^^^

.. java:method:: public void onFailure(Throwable e)
   :outertype: IncomingMessageTask

   onFailure

   :param e:

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.onFailure(java.lang.Throwable)`

setRetried
^^^^^^^^^^

.. java:method:: public void setRetried(int retried)
   :outertype: IncomingMessageTask

   setRetried

   :param retried:

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.setRetried(int)`

