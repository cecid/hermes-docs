.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao InboxDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao InboxDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao OutboxDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao OutboxDVO

.. java:import:: hk.hku.cecid.edi.as2 AS2Processor

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDAO

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDVO

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDataSourceDAO

.. java:import:: hk.hku.cecid.edi.as2.dao RepositoryDAO

.. java:import:: hk.hku.cecid.edi.as2.dao RepositoryDVO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao Transaction

.. java:import:: hk.hku.cecid.piazza.commons.mail SmtpMail

.. java:import:: hk.hku.cecid.piazza.commons.mail SmtpMailException

.. java:import:: hk.hku.cecid.piazza.commons.mail SmtpMailProperties

.. java:import:: hk.hku.cecid.piazza.commons.module ActiveTask

.. java:import:: hk.hku.cecid.piazza.commons.servlet.http HttpDispatcherContext

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.corvus.core.main.admin AdminMainProcessor

.. java:import:: hk.hku.cecid.piazza.corvus.core.main.admin.hc.util AdminProperties

.. java:import:: hk.hku.cecid.piazza.corvus.core.main.admin.hc.util AdminPropertiesException

.. java:import:: java.io UnsupportedEncodingException

.. java:import:: java.text ParseException

.. java:import:: java.text SimpleDateFormat

.. java:import:: java.util Calendar

.. java:import:: java.util Date

.. java:import:: java.util GregorianCalendar

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: javax.mail Address

.. java:import:: javax.mail MessagingException

.. java:import:: javax.mail Session

.. java:import:: javax.mail.internet AddressException

.. java:import:: javax.mail.internet InternetAddress

.. java:import:: com.sun.mail.smtp SMTPMessage

SchedulerTask
=============

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.admin.hc.module
   :noindex:

.. java:type:: public class SchedulerTask implements ActiveTask

Fields
------
DATE_FORMAT
^^^^^^^^^^^

.. java:field:: public static final String DATE_FORMAT
   :outertype: SchedulerTask

   Formats

TIME_FORMAT
^^^^^^^^^^^

.. java:field:: public static final String TIME_FORMAT
   :outertype: SchedulerTask

Methods
-------
cleanAS2
^^^^^^^^

.. java:method:: protected Transaction cleanAS2(int months) throws Exception
   :outertype: SchedulerTask

   Attempt to clean out the AS2 database

   :param months:
   :throws Exception:
   :throws DAOException:

cleanEBMS
^^^^^^^^^

.. java:method:: protected Transaction cleanEBMS(int months) throws Exception
   :outertype: SchedulerTask

   Attempt to clean the EBMS messages.

   :param months:
   :throws Exception:
   :throws DAOException:

execute
^^^^^^^

.. java:method:: public void execute() throws Exception
   :outertype: SchedulerTask

getMaxRetries
^^^^^^^^^^^^^

.. java:method:: public int getMaxRetries()
   :outertype: SchedulerTask

getNextRunDateFromNow
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static Date getNextRunDateFromNow(int day_of_week, int hour, int min, int sec)
   :outertype: SchedulerTask

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public long getRetryInterval()
   :outertype: SchedulerTask

isRetryEnabled
^^^^^^^^^^^^^^

.. java:method:: public boolean isRetryEnabled()
   :outertype: SchedulerTask

isSucceedFast
^^^^^^^^^^^^^

.. java:method:: public boolean isSucceedFast()
   :outertype: SchedulerTask

onAwake
^^^^^^^

.. java:method:: public void onAwake()
   :outertype: SchedulerTask

onFailure
^^^^^^^^^

.. java:method:: public void onFailure(Throwable e)
   :outertype: SchedulerTask

setNextRunDateFromNow
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean setNextRunDateFromNow(AdminProperties properties)
   :outertype: SchedulerTask

setRetried
^^^^^^^^^^

.. java:method:: public void setRetried(int retried)
   :outertype: SchedulerTask

