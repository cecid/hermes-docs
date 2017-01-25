.. java:import:: hk.hku.cecid.edi.as2 AS2Exception

.. java:import:: hk.hku.cecid.edi.as2.dao AS2DAOHandler

.. java:import:: hk.hku.cecid.edi.as2.dao PartnershipDVO

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Header

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: hk.hku.cecid.edi.as2.pkg Disposition

.. java:import:: hk.hku.cecid.edi.as2.pkg DispositionNotification

.. java:import:: hk.hku.cecid.edi.as2.pkg DispositionNotificationOption

.. java:import:: hk.hku.cecid.edi.as2.pkg DispositionNotificationOptions

.. java:import:: hk.hku.cecid.piazza.commons.security KeyStoreManager

.. java:import:: hk.hku.cecid.piazza.commons.security SMimeMessage

.. java:import:: hk.hku.cecid.piazza.commons.util Logger

.. java:import:: java.util Iterator

.. java:import:: javax.mail.internet MimeBodyPart

IncomingMessage
===============

.. java:package:: hk.hku.cecid.edi.as2.module
   :noindex:

.. java:type::  class IncomingMessage

   IncomingMessage

   :author: Hugo Y. K. Lam

Constructors
------------
IncomingMessage
^^^^^^^^^^^^^^^

.. java:constructor:: public IncomingMessage(AS2Message requestMessage, KeyStoreManager keyman, AS2DAOHandler daoHandler, Logger logger)
   :outertype: IncomingMessage

Methods
-------
generateReceipt
^^^^^^^^^^^^^^^

.. java:method:: public AS2Message generateReceipt() throws AS2Exception
   :outertype: IncomingMessage

getDecrytedMessage
^^^^^^^^^^^^^^^^^^

.. java:method:: public AS2Message getDecrytedMessage() throws AS2Exception
   :outertype: IncomingMessage

getDisposition
^^^^^^^^^^^^^^

.. java:method:: public Disposition getDisposition()
   :outertype: IncomingMessage

processSMime
^^^^^^^^^^^^

.. java:method:: public Disposition processSMime() throws AS2Exception
   :outertype: IncomingMessage

