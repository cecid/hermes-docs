.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageServiceHandler

.. java:import:: hk.hku.cecid.ebms.spa.listener EbmsRequest

.. java:import:: hk.hku.cecid.ebms.spa.listener EbmsResponse

.. java:import:: hk.hku.cecid.piazza.commons.module ActiveTask

.. java:import:: hk.hku.cecid.piazza.commons.security KeyStoreManager

.. java:import:: hk.hku.cecid.piazza.commons.security SMimeMessage

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: javax.mail Message

.. java:import:: javax.mail.internet MimeBodyPart

.. java:import:: javax.mail.internet MimeMessage

MailTask
========

.. java:package:: hk.hku.cecid.ebms.spa.task
   :noindex:

.. java:type:: public class MailTask implements ActiveTask

   :author: Donahue Sze

Constructors
------------
MailTask
^^^^^^^^

.. java:constructor:: public MailTask(Message message)
   :outertype: MailTask

Methods
-------
execute
^^^^^^^

.. java:method:: public void execute() throws Exception
   :outertype: MailTask

getMaxRetries
^^^^^^^^^^^^^

.. java:method:: public int getMaxRetries()
   :outertype: MailTask

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public long getRetryInterval()
   :outertype: MailTask

isRetryEnabled
^^^^^^^^^^^^^^

.. java:method:: public boolean isRetryEnabled()
   :outertype: MailTask

isSucceedFast
^^^^^^^^^^^^^

.. java:method:: public boolean isSucceedFast()
   :outertype: MailTask

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: MailTask

onAwake
^^^^^^^

.. java:method:: public void onAwake()
   :outertype: MailTask

onFailure
^^^^^^^^^

.. java:method:: public void onFailure(Throwable arg0)
   :outertype: MailTask

setRetried
^^^^^^^^^^

.. java:method:: public void setRetried(int arg0)
   :outertype: MailTask

