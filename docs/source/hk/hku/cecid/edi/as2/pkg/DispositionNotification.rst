.. java:import:: hk.hku.cecid.piazza.commons.security SMimeMessage

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: java.util Enumeration

.. java:import:: javax.mail MessagingException

.. java:import:: javax.mail.internet InternetHeaders

.. java:import:: javax.mail.internet MimeBodyPart

.. java:import:: javax.mail.internet MimeMultipart

.. java:import:: javax.mail.internet MimeUtility

DispositionNotification
=======================

.. java:package:: hk.hku.cecid.edi.as2.pkg
   :noindex:

.. java:type:: public class DispositionNotification

   DispositionNotification represents an AS2 disposition notification.

   :author: Hugo Y. K. Lam

Fields
------
DISPOSITION
^^^^^^^^^^^

.. java:field:: public static final String DISPOSITION
   :outertype: DispositionNotification

FINAL_RECIPIENT
^^^^^^^^^^^^^^^

.. java:field:: public static final String FINAL_RECIPIENT
   :outertype: DispositionNotification

ORIG_MESSAGE_ID
^^^^^^^^^^^^^^^

.. java:field:: public static final String ORIG_MESSAGE_ID
   :outertype: DispositionNotification

ORIG_RECIPIENT
^^^^^^^^^^^^^^

.. java:field:: public static final String ORIG_RECIPIENT
   :outertype: DispositionNotification

RECEIVED_CONTENT_MIC
^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String RECEIVED_CONTENT_MIC
   :outertype: DispositionNotification

REPORTING_UA
^^^^^^^^^^^^

.. java:field:: public static final String REPORTING_UA
   :outertype: DispositionNotification

Constructors
------------
DispositionNotification
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public DispositionNotification() throws AS2MessageException
   :outertype: DispositionNotification

DispositionNotification
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor::  DispositionNotification(AS2Message as2Message) throws AS2MessageException
   :outertype: DispositionNotification

Methods
-------
getBodyPart
^^^^^^^^^^^

.. java:method:: public MimeBodyPart getBodyPart() throws AS2MessageException
   :outertype: DispositionNotification

getDisposition
^^^^^^^^^^^^^^

.. java:method:: public Disposition getDisposition() throws AS2MessageException
   :outertype: DispositionNotification

getOriginalMessageID
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getOriginalMessageID()
   :outertype: DispositionNotification

getReceivedContentMIC
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getReceivedContentMIC()
   :outertype: DispositionNotification

getReportValue
^^^^^^^^^^^^^^

.. java:method:: public String getReportValue(String key)
   :outertype: DispositionNotification

getText
^^^^^^^

.. java:method:: public String getText() throws AS2MessageException
   :outertype: DispositionNotification

matchOriginalContentMIC
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean matchOriginalContentMIC(String originalMIC)
   :outertype: DispositionNotification

replyTo
^^^^^^^

.. java:method:: public void replyTo(AS2Message message, String reportingUA) throws AS2MessageException
   :outertype: DispositionNotification

setDisposition
^^^^^^^^^^^^^^

.. java:method:: public void setDisposition(Disposition disposition) throws AS2MessageException
   :outertype: DispositionNotification

setOriginalMessageID
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setOriginalMessageID(String messageID)
   :outertype: DispositionNotification

setReceivedContentMIC
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setReceivedContentMIC(String mic)
   :outertype: DispositionNotification

setReceivedContentMIC
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setReceivedContentMIC(String mic, String alg)
   :outertype: DispositionNotification

setReportValue
^^^^^^^^^^^^^^

.. java:method:: public void setReportValue(String key, Object value)
   :outertype: DispositionNotification

setText
^^^^^^^

.. java:method:: public void setText(String text) throws AS2MessageException
   :outertype: DispositionNotification

