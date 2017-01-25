.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao InboxDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao InboxDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDVO

.. java:import:: hk.hku.cecid.ebms.spa.handler EbxmlMessageDAOConvertor

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageClassifier

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.module ActiveTask

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

InboxTask
=========

.. java:package:: hk.hku.cecid.ebms.spa.task
   :noindex:

.. java:type:: public class InboxTask implements ActiveTask

   :author: Donahue Sze

Constructors
------------
InboxTask
^^^^^^^^^

.. java:constructor:: public InboxTask(MessageDVO message, long nextOrderNo)
   :outertype: InboxTask

Methods
-------
execute
^^^^^^^

.. java:method:: public void execute() throws Exception
   :outertype: InboxTask

getMaxRetries
^^^^^^^^^^^^^

.. java:method:: public int getMaxRetries()
   :outertype: InboxTask

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public long getRetryInterval()
   :outertype: InboxTask

isRetryEnabled
^^^^^^^^^^^^^^

.. java:method:: public boolean isRetryEnabled()
   :outertype: InboxTask

isSucceedFast
^^^^^^^^^^^^^

.. java:method:: public boolean isSucceedFast()
   :outertype: InboxTask

onAwake
^^^^^^^

.. java:method:: public void onAwake()
   :outertype: InboxTask

onFailure
^^^^^^^^^

.. java:method:: public void onFailure(Throwable arg0)
   :outertype: InboxTask

setRetried
^^^^^^^^^^

.. java:method:: public void setRetried(int arg0)
   :outertype: InboxTask

