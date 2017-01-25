.. java:import:: hk.hku.cecid.edi.as2 AS2Exception

.. java:import:: hk.hku.cecid.edi.as2 AS2PlusProcessor

.. java:import:: hk.hku.cecid.edi.as2.dao AS2DAOHandler

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDVO

.. java:import:: hk.hku.cecid.edi.as2.dao PartnershipDVO

.. java:import:: hk.hku.cecid.edi.as2.dao RepositoryDAO

.. java:import:: hk.hku.cecid.edi.as2.dao RepositoryDVO

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: hk.hku.cecid.piazza.commons.module ActiveTask

.. java:import:: hk.hku.cecid.piazza.commons.net HttpConnector

.. java:import:: hk.hku.cecid.piazza.commons.security TrustedHostnameVerifier

.. java:import:: hk.hku.cecid.piazza.commons.util Headers

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io InputStream

.. java:import:: java.net HttpURLConnection

OutgoingMessageTask
===================

.. java:package:: hk.hku.cecid.edi.as2.module
   :noindex:

.. java:type:: public class OutgoingMessageTask implements ActiveTask

   OutgoingMessageTask

   :author: Hugo Y. K. Lam

Constructors
------------
OutgoingMessageTask
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public OutgoingMessageTask(MessageDVO message) throws AS2Exception
   :outertype: OutgoingMessageTask

   :throws AS2Exception:

Methods
-------
execute
^^^^^^^

.. java:method:: public void execute() throws Exception
   :outertype: OutgoingMessageTask

   execute

   :throws Exception:

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.execute()`

getMaxRetries
^^^^^^^^^^^^^

.. java:method:: public int getMaxRetries()
   :outertype: OutgoingMessageTask

   getMaxRetries

   :return: int

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.getMaxRetries()`

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public long getRetryInterval()
   :outertype: OutgoingMessageTask

   getRetryInterval

   :return: long

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.getRetryInterval()`

isRetryEnabled
^^^^^^^^^^^^^^

.. java:method:: public boolean isRetryEnabled()
   :outertype: OutgoingMessageTask

   isRetryEnabled

   :return: boolean

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.isRetryEnabled()`

isSucceedFast
^^^^^^^^^^^^^

.. java:method:: public boolean isSucceedFast()
   :outertype: OutgoingMessageTask

   isSucceedFast

   :return: boolean

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.isSucceedFast()`

onAwake
^^^^^^^

.. java:method:: public void onAwake()
   :outertype: OutgoingMessageTask

   onAwake

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.onAwake()`

onFailure
^^^^^^^^^

.. java:method:: public void onFailure(Throwable e)
   :outertype: OutgoingMessageTask

   onFailure

   :param e:

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.onFailure(java.lang.Throwable)`

setRetried
^^^^^^^^^^

.. java:method:: public void setRetried(int retried)
   :outertype: OutgoingMessageTask

   setRetried

   :param retried:

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.setRetried(int)`

