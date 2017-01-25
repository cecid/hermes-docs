.. java:import:: hk.hku.cecid.ebms.pkg Description

.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.pkg ErrorList

.. java:import:: hk.hku.cecid.ebms.pkg SignatureHandler

.. java:import:: hk.hku.cecid.ebms.pkg.validation EbxmlMessageValidator

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageServerDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao OutboxDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao OutboxDVO

.. java:import:: hk.hku.cecid.ebms.spa.handler EbxmlMessageDAOConvertor

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageClassifier

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageServiceHandler

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageServiceHandlerException

.. java:import:: hk.hku.cecid.ebms.spa.handler SignalMessageGenerator

.. java:import:: hk.hku.cecid.ebms.spa.listener EbmsRequest

.. java:import:: hk.hku.cecid.ebms.spa.listener EbmsResponse

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.module ActiveTask

.. java:import:: hk.hku.cecid.piazza.commons.security SMimeMessage

.. java:import:: hk.hku.cecid.piazza.commons.security TrustedHostnameVerifier

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPHttpConnector

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPMailSender

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io IOException

.. java:import:: java.net HttpURLConnection

.. java:import:: java.net URL

.. java:import:: java.security.cert CertificateException

.. java:import:: java.security.cert CertificateFactory

.. java:import:: java.security.cert X509Certificate

.. java:import:: java.sql Timestamp

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: javax.mail Session

.. java:import:: javax.mail.internet MimeBodyPart

.. java:import:: javax.mail.internet MimeMessage

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPMessage

OutboxTask
==========

.. java:package:: hk.hku.cecid.ebms.spa.task
   :noindex:

.. java:type:: public class OutboxTask implements ActiveTask

   :author: Donahue Sze, Twinsen Tsang (modifiers)

Constructors
------------
OutboxTask
^^^^^^^^^^

.. java:constructor:: public OutboxTask(MessageDVO message)
   :outertype: OutboxTask

   Explicit Constructor.

   :param message:

Methods
-------
execute
^^^^^^^

.. java:method:: public void execute() throws Exception
   :outertype: OutboxTask

   The main execution of \ ``OutboxTask``\ . The overview procedure is listed in below:

   ..

   #. Extract the \ ``EbXMLMessage``\  from the \ ``messageDVO``\ .
   #. Sign the \ ``EbXMLMessage``\  by it's keystore if necessary.
   #. Send the \ ``EbXMLMessage``\  through HTTP/HTTPS/SMTP protocol.
   #. Update the number of retry attempted to deliver for this \ ``EbXMLMessage``\ .

getMaxRetries
^^^^^^^^^^^^^

.. java:method:: public int getMaxRetries()
   :outertype: OutboxTask

   Get the maximum execution times for this task. It returns the total number of times that the \ ``EbXML Message``\  can be attempted to deliver (including non-retry delivery). For \ ``EbXML Message``\  does not requests ACK, this method always return zero because it does not support retry / re-sending schema when ACK does not requested. [ebMSS section 6.4.3] It is calculated by :  \ *Max(maximum retry defined in partnership for this message - 1,0) + 1.*\

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.getMaxRetries()`, :java:ref:`hk.hku.cecid.ebms.spa.dao.PartnershipDVO.getRetries()`, :java:ref:`hk.hku.cecid.ebms.spa.dao.OutboxDVO.getRetried()`

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public long getRetryInterval()
   :outertype: OutboxTask

isRetryEnabled
^^^^^^^^^^^^^^

.. java:method:: public boolean isRetryEnabled()
   :outertype: OutboxTask

isSucceedFast
^^^^^^^^^^^^^

.. java:method:: public boolean isSucceedFast()
   :outertype: OutboxTask

onAwake
^^^^^^^

.. java:method:: public void onAwake()
   :outertype: OutboxTask

onFailure
^^^^^^^^^

.. java:method:: public void onFailure(Throwable t)
   :outertype: OutboxTask

   Invoke when \ :java:ref:`execute()`\  throw any kind of uncaught exception.

setRetried
^^^^^^^^^^

.. java:method:: public void setRetried(int retried)
   :outertype: OutboxTask

   :param retried: The number of times that this active task has been retried (local retired times).

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.ActiveTask.setRetried(int)`

