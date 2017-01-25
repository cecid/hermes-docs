.. java:import:: hk.hku.cecid.edi.as2 AS2Exception

.. java:import:: hk.hku.cecid.edi.as2.dao AS2DAOHandler

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDAO

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDVO

.. java:import:: hk.hku.cecid.edi.as2.dao PartnershipDVO

.. java:import:: hk.hku.cecid.edi.as2.dao RepositoryDAO

.. java:import:: hk.hku.cecid.edi.as2.dao RepositoryDVO

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Header

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: hk.hku.cecid.edi.as2.pkg Disposition

.. java:import:: hk.hku.cecid.edi.as2.pkg DispositionNotification

.. java:import:: hk.hku.cecid.piazza.commons.module SystemComponent

.. java:import:: hk.hku.cecid.piazza.commons.security KeyStoreManager

.. java:import:: hk.hku.cecid.piazza.commons.security SMimeMessage

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: java.io InputStream

IncomingMessageProcessor
========================

.. java:package:: hk.hku.cecid.edi.as2.module
   :noindex:

.. java:type:: public class IncomingMessageProcessor extends SystemComponent

   IncomingMessageProcessor

   :author: Hugo Y. K. Lam

Methods
-------
processMessage
^^^^^^^^^^^^^^

.. java:method:: public AS2Message processMessage(AS2Message requestMessage) throws AS2Exception
   :outertype: IncomingMessageProcessor

processReceipt
^^^^^^^^^^^^^^

.. java:method:: public void processReceipt(AS2Message receipt) throws AS2Exception
   :outertype: IncomingMessageProcessor

processReceivedMessage
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected AS2Message processReceivedMessage(AS2Message requestMessage) throws AS2Exception
   :outertype: IncomingMessageProcessor

