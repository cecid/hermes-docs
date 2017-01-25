.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

OutboxDVO
=========

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public interface OutboxDVO extends DVO

   :author: Donahue Sze

Methods
-------
getMessageId
^^^^^^^^^^^^

.. java:method:: public String getMessageId()
   :outertype: OutboxDVO

   :return: Returns the ackRequested.

getRetried
^^^^^^^^^^

.. java:method:: public int getRetried()
   :outertype: OutboxDVO

   :return: Returns the retried.

setMessageId
^^^^^^^^^^^^

.. java:method:: public void setMessageId(String messageId)
   :outertype: OutboxDVO

   :param messageId: The messageId to set.

setRetried
^^^^^^^^^^

.. java:method:: public void setRetried(int retried)
   :outertype: OutboxDVO

   :param retried: The retried to set.

