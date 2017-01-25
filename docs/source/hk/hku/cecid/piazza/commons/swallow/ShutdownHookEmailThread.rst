.. java:import:: java.io IOException

.. java:import:: java.io StringWriter

.. java:import:: hk.hku.cecid.piazza.commons.net ConnectionException

.. java:import:: hk.hku.cecid.piazza.commons.net MailSender

.. java:import:: hk.hku.cecid.piazza.commons.swallow DiagnosticUtilities

ShutdownHookEmailThread
=======================

.. java:package:: hk.hku.cecid.piazza.commons.swallow
   :noindex:

.. java:type:: public class ShutdownHookEmailThread extends Thread

   The \ ``ShutdownHookEmailThread``\  is the actual worker thread executing during the JVM shutdown.

Fields
------
DEFAULT_SHUTDOWN_MAIL_SUBJECT
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String DEFAULT_SHUTDOWN_MAIL_SUBJECT
   :outertype: ShutdownHookEmailThread

ccs
^^^

.. java:field:: protected String ccs
   :outertype: ShutdownHookEmailThread

from
^^^^

.. java:field:: protected String from
   :outertype: ShutdownHookEmailThread

host
^^^^

.. java:field:: protected String host
   :outertype: ShutdownHookEmailThread

password
^^^^^^^^

.. java:field:: protected String password
   :outertype: ShutdownHookEmailThread

protocol
^^^^^^^^

.. java:field:: protected String protocol
   :outertype: ShutdownHookEmailThread

subject
^^^^^^^

.. java:field:: protected String subject
   :outertype: ShutdownHookEmailThread

tos
^^^

.. java:field:: protected String tos
   :outertype: ShutdownHookEmailThread

username
^^^^^^^^

.. java:field:: protected String username
   :outertype: ShutdownHookEmailThread

verbose
^^^^^^^

.. java:field:: protected boolean verbose
   :outertype: ShutdownHookEmailThread

Constructors
------------
ShutdownHookEmailThread
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public ShutdownHookEmailThread(String protocol, String host, String username, String password, String from, String tos, String ccs, String subject, boolean verbose)
   :outertype: ShutdownHookEmailThread

   Create an instance of \ ``ShutdownHookEmailThread``\  for delivering shutdown notification mail.

   :param protocol: The protocol for delivering email. default: smtp.
   :param host: The host-name of email server.
   :param username: The user-name for authenticating the email server, if necessary.
   :param password: The password for authenticating the email server, if necessary.
   :param from: The source email address of the shutdown notification email.
   :param tos: The to email address of recipient notification email.
   :param ccs: The cc email address of recipient notification email.
   :param subject: The subject of the email address.
   :param verbose: Enable debug mode ?

Methods
-------
getCcs
^^^^^^

.. java:method:: public String getCcs()
   :outertype: ShutdownHookEmailThread

   Get the carbon copy address of the shutdown alert email.

   :return: Get the carbon copy address of the shutdown alert email.

getFrom
^^^^^^^

.. java:method:: public String getFrom()
   :outertype: ShutdownHookEmailThread

   Get the source address of the shutdown alert email.

   :return: Get the source address of the shutdown alert email.

getHost
^^^^^^^

.. java:method:: public String getHost()
   :outertype: ShutdownHookEmailThread

   Get the email host of the shutdown alert email.

   :return: Get the email host of the shutdown alert email.

getIsVerbose
^^^^^^^^^^^^

.. java:method:: public boolean getIsVerbose()
   :outertype: ShutdownHookEmailThread

   Get whether the shutdown hook output verbosely.

   :return: Get whether the shutdown hook output verbosely.

getPassword
^^^^^^^^^^^

.. java:method:: public String getPassword()
   :outertype: ShutdownHookEmailThread

   Get the password (if any) for authenticating the email host for delivering the alert email.

   :return: Get the password (if any) for authenticating the email host.

getProtocol
^^^^^^^^^^^

.. java:method:: public String getProtocol()
   :outertype: ShutdownHookEmailThread

   Get the email protocol of the shutdown alert email.

   :return: Get the email protocol of the shutdown alert email.

getSubject
^^^^^^^^^^

.. java:method:: public String getSubject()
   :outertype: ShutdownHookEmailThread

   Get the subject title of the shutdown alert email.

   :return: Get the subject title of the shutdown alert email.

getTos
^^^^^^

.. java:method:: public String getTos()
   :outertype: ShutdownHookEmailThread

   Get the recipient address of the shutdown alert email.

   :return: Get the recipient address of the shutdown alert email.

getUsername
^^^^^^^^^^^

.. java:method:: public String getUsername()
   :outertype: ShutdownHookEmailThread

   Get the user-name (if any) for authenticating the email host for delivering the alert email.

   :return: Get the user-name (if any) for authenticating the email host.

onCreateMailNotificationBody
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected String onCreateMailNotificationBody()
   :outertype: ShutdownHookEmailThread

   Return the body of notification email. The default return the snapshot of all thread dump information. Sub-class may override this to customize the subject of notification email.

   :return: Return the body of notification email.

onCreateMailNotificationSubject
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected String onCreateMailNotificationSubject()
   :outertype: ShutdownHookEmailThread

   Return the subject of notification email. Sub-class may override this to customize the subject of notification email.

   :return: Return the subject of notification email, default is \ :java:ref:`DEFAULT_SHUTDOWN_MAIL_SUBJECT`\

run
^^^

.. java:method:: public void run()
   :outertype: ShutdownHookEmailThread

   The shutdown thread execution.

