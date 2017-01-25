.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao OutboxDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao OutboxDVO

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageClassifier

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOFactory

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDAO

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceProcess

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceTransaction

EbmsMessageStatusReverser
=========================

.. java:package:: hk.hku.cecid.ebms.spa.util
   :noindex:

.. java:type:: public class EbmsMessageStatusReverser

   Reverse message status for message redownload and resend

   :author: franz

Methods
-------
updateToDownload
^^^^^^^^^^^^^^^^

.. java:method:: public void updateToDownload(String messageId) throws Exception
   :outertype: EbmsMessageStatusReverser

updateToSend
^^^^^^^^^^^^

.. java:method:: public MessageDVO updateToSend(String messageId) throws Exception
   :outertype: EbmsMessageStatusReverser

   Reverse \ **OUTBOX**\  message status back to \ **PENDING**\ . Hence, the message can be resent again.

   :param messageId: - Message Id of the message to be resent
   :throws Exception:
   :return: MessageDVO of the message to be resent

