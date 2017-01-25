.. java:import:: javax.mail Message

.. java:import:: javax.mail Session

.. java:import:: javax.mail Transport

.. java:import:: javax.mail.internet InternetAddress

.. java:import:: javax.mail.internet MimeMessage

MailSender
==========

.. java:package:: hk.hku.cecid.piazza.commons.net
   :noindex:

.. java:type:: public class MailSender extends MailConnector

   MailSender is a mail connector for making connections to outgoing mail servers.

   :author: Hugo Y. K. Lam

Constructors
------------
MailSender
^^^^^^^^^^

.. java:constructor:: public MailSender(String host)
   :outertype: MailSender

   Creates a new instance of MailSender. The default protocol is SMTP.

   :param host: the mail host.

MailSender
^^^^^^^^^^

.. java:constructor:: public MailSender(String host, String username, String password)
   :outertype: MailSender

   Creates a new instance of MailSender. The default protocol is SMTP.

   :param host: the mail host.
   :param username: the user name for authentication.
   :param password: the password for authentication.

MailSender
^^^^^^^^^^

.. java:constructor:: public MailSender(String protocol, String host)
   :outertype: MailSender

   Creates a new instance of MailSender.

   :param protocol: the mail protocol.
   :param host: the mail host.

MailSender
^^^^^^^^^^

.. java:constructor:: public MailSender(String protocol, String host, String username, String password)
   :outertype: MailSender

   Creates a new instance of MailSender.

   :param protocol: the mail protocol.
   :param host: the mail host.
   :param username: the user name for authentication.
   :param password: the password for authentication.

Methods
-------
createMessage
^^^^^^^^^^^^^

.. java:method:: public MimeMessage createMessage()
   :outertype: MailSender

   Creates a MIME message from the underlying mail properties.

   :return: a new MIME message.

createMessage
^^^^^^^^^^^^^

.. java:method:: public MimeMessage createMessage(Session session)
   :outertype: MailSender

   Creates a MIME message from the given mail session.

   :param session: the mail session.
   :return: a new MIME message.

createMessage
^^^^^^^^^^^^^

.. java:method:: public MimeMessage createMessage(String from, String to, String cc, String subject) throws ConnectionException
   :outertype: MailSender

   Creates a simple MIME message with some basic headers.

   :param from: the 'from' mail address.
   :param to: the 'to' mail address(es).
   :param cc: the 'cc' mail address(es).
   :param subject: the mail subject.
   :throws ConnectionException: if error occurred in constructing the mail message.
   :return: a new MIME message.

createMessage
^^^^^^^^^^^^^

.. java:method:: public MimeMessage createMessage(String from, String to, String cc, String subject, Session session) throws ConnectionException
   :outertype: MailSender

   Creates a simple MIME message with some basic headers.

   :param from: the 'from' mail address.
   :param to: the 'to' mail address(es).
   :param cc: the 'cc' mail address(es).
   :param subject: the mail subject.
   :param session: the mail session.
   :throws ConnectionException: if error occurred in constructing the mail message.
   :return: a new MIME message.

send
^^^^

.. java:method:: public void send(String from, String to, String cc, String subject, String body) throws ConnectionException
   :outertype: MailSender

   Sends a simple mail message.

   :param from: the 'from' mail address.
   :param to: the 'to' mail address(es).
   :param cc: the 'cc' mail address(es).
   :param subject: the mail subject.
   :param body: the message content.
   :throws ConnectionException: if unable to construct the mail message or to send out the message.

send
^^^^

.. java:method:: public void send(Message msg) throws ConnectionException
   :outertype: MailSender

   Sends a mail message.

   :param msg: the mail message to be sent.
   :throws ConnectionException: if unable to send the mail message

