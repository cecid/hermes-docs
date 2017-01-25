.. java:import:: hk.hku.cecid.edi.as2 AS2Exception

.. java:import:: hk.hku.cecid.edi.as2 AS2PlusProcessor

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDAO

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDVO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOFactory

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDAO

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceProcess

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceTransaction

.. java:import:: java.util List

AS2MessageStatusReverser
========================

.. java:package:: hk.hku.cecid.edi.as2.util
   :noindex:

.. java:type:: public class AS2MessageStatusReverser

   Reverse message status for message redownload and resend

   :author: franz

Methods
-------
updateToDownload
^^^^^^^^^^^^^^^^

.. java:method:: public void updateToDownload(String messageId) throws AS2Exception, DAOException
   :outertype: AS2MessageStatusReverser

   Reverse \ **INBOX**\  message status back to \ **PROCESSED**\ . Hence, the message can be downloaded again.

   :param messageId: - MessageId to query inbox message
   :throws AS2Exception:

updateToSend
^^^^^^^^^^^^

.. java:method:: public MessageDVO updateToSend(String messageId) throws AS2Exception
   :outertype: AS2MessageStatusReverser

   Reverse \ **OUTBOX**\  message status back to \ **PENDING**\ . Hence, the message can be resent again.

   :param messageId: - Message Id of the message to be resent
   :throws AS2Exception:
   :return: MessageDVO of the message to be resent

