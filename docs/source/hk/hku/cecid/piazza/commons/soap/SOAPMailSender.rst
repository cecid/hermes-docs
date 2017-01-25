.. java:import:: hk.hku.cecid.piazza.commons.activation ByteArrayDataSource

.. java:import:: hk.hku.cecid.piazza.commons.activation InputStreamDataSource

.. java:import:: hk.hku.cecid.piazza.commons.net ConnectionException

.. java:import:: hk.hku.cecid.piazza.commons.net MailSender

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.util Iterator

.. java:import:: javax.activation DataHandler

.. java:import:: javax.mail BodyPart

.. java:import:: javax.mail MessagingException

.. java:import:: javax.mail Session

.. java:import:: javax.mail.internet MimeMessage

.. java:import:: javax.mail.internet MimeMultipart

.. java:import:: javax.xml.soap MimeHeader

.. java:import:: javax.xml.soap MimeHeaders

.. java:import:: javax.xml.soap SOAPMessage

SOAPMailSender
==============

.. java:package:: hk.hku.cecid.piazza.commons.soap
   :noindex:

.. java:type:: public class SOAPMailSender extends MailSender

   SOAPMailSender is a mail sender responsible for sending SOAP message.

   :author: Hugo Y. K. Lam

Constructors
------------
SOAPMailSender
^^^^^^^^^^^^^^

.. java:constructor:: public SOAPMailSender(String host)
   :outertype: SOAPMailSender

   Creates a new instance of SOAPMailSender.

   :param host: the mail host.

SOAPMailSender
^^^^^^^^^^^^^^

.. java:constructor:: public SOAPMailSender(String protocol, String host)
   :outertype: SOAPMailSender

   Creates a new instance of SOAPMailSender.

   :param protocol: the mail protocol.
   :param host: the mail host.

SOAPMailSender
^^^^^^^^^^^^^^

.. java:constructor:: public SOAPMailSender(String host, String username, String password)
   :outertype: SOAPMailSender

   Creates a new instance of SOAPMailSender.

   :param host: the mail host.
   :param username: the user name for authentication.
   :param password: the password for authentication.

SOAPMailSender
^^^^^^^^^^^^^^

.. java:constructor:: public SOAPMailSender(String protocol, String host, String username, String password)
   :outertype: SOAPMailSender

   Creates a new instance of SOAPMailSender.

   :param protocol: the mail protocol.
   :param host: the mail host.
   :param username: the user name for authentication.
   :param password: the password for authentication.

Methods
-------
createMessage
^^^^^^^^^^^^^

.. java:method:: public MimeMessage createMessage(String from, String to, String cc, String subject, SOAPMessage soapMessage) throws ConnectionException
   :outertype: SOAPMailSender

   Creates a MIME message from a SOAP message.

   :param from: the 'from' mail address.
   :param to: the 'to' mail address(es).
   :param cc: the 'cc' mail address(es).
   :param subject: the mail subject.
   :param soapMessage: the SOAP message.
   :throws ConnectionException: if error occurred in constructing the mail message.
   :return: a new MIME message.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.net.MailSender.createMessage(java.lang.String,java.lang.String,java.lang.String,java.lang.String,javax.mail.Session)`

createMessage
^^^^^^^^^^^^^

.. java:method:: public MimeMessage createMessage(String from, String to, String cc, String subject, SOAPMessage soapMessage, Session session) throws ConnectionException
   :outertype: SOAPMailSender

   Creates a MIME message from a SOAP message.

   :param from: the 'from' mail address.
   :param to: the 'to' mail address(es).
   :param cc: the 'cc' mail address(es).
   :param subject: the mail subject.
   :param soapMessage: the SOAP message.
   :param session: the mail session.
   :throws ConnectionException: if error occurred in constructing the mail message.
   :return: a new MIME message.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.net.MailSender.createMessage(java.lang.String,java.lang.String,java.lang.String,java.lang.String,javax.mail.Session)`

send
^^^^

.. java:method:: public void send(String from, String to, String cc, String subject, SOAPMessage soapMessage) throws ConnectionException
   :outertype: SOAPMailSender

   Sends a SOAP message.

   :param from: the 'from' mail address.
   :param to: the 'to' mail address(es).
   :param cc: the 'cc' mail address(es).
   :param subject: the mail subject.
   :param soapMessage: the SOAP message.
   :throws ConnectionException: if unable to construct the mail message or to send out the message.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.net.MailSender.send(java.lang.String,java.lang.String,java.lang.String,java.lang.String,java.lang.String)`

