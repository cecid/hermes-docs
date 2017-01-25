.. java:import:: java.util Date

.. java:import:: java.util Properties

.. java:import:: javax.mail Address

.. java:import:: javax.mail AuthenticationFailedException

.. java:import:: javax.mail Message

.. java:import:: javax.mail MessagingException

.. java:import:: javax.mail NoSuchProviderException

.. java:import:: javax.mail SendFailedException

.. java:import:: javax.mail Session

.. java:import:: javax.mail Transport

.. java:import:: com.sun.mail.smtp SMTPMessage

SmtpMail
========

.. java:package:: hk.hku.cecid.piazza.commons.mail
   :noindex:

.. java:type:: public class SmtpMail

   A class that handles sending SMTP messages.

   :author: Administrator

Constructors
------------
SmtpMail
^^^^^^^^

.. java:constructor:: public SmtpMail(boolean useSSL) throws SmtpMailException
   :outertype: SmtpMail

   Create a new SmtpMail instance.

   :param useSSL:
   :throws SmtpMailException:

SmtpMail
^^^^^^^^

.. java:constructor:: public SmtpMail(SmtpMailProperties sprops, boolean useSSL) throws SmtpMailException
   :outertype: SmtpMail

   Create a new SmtpMail instance with the given SmtpMailProperties object.

   :param sprops:
   :param useSSL:
   :throws SmtpMailException:

Methods
-------
getSession
^^^^^^^^^^

.. java:method:: public Session getSession()
   :outertype: SmtpMail

isConnected
^^^^^^^^^^^

.. java:method:: public boolean isConnected()
   :outertype: SmtpMail

   Checks whether the transport associated with this instance is connected.

   :return: boolean

send
^^^^

.. java:method:: public void send(SMTPMessage msg, Address[] to) throws SmtpMailException
   :outertype: SmtpMail

   Send the SMTPMessage to the address(es) using the SMTP transport

   :param msg:
   :param to:
   :throws SmtpMailException:

send
^^^^

.. java:method:: public void send(String source, Address from, Address[] to, String subject) throws SmtpMailException
   :outertype: SmtpMail

   Convenience method for composing a simple text MIME Message with the source.

   :param source:
   :param from:
   :param to:
   :param subject:
   :throws SmtpMailException:

transportClose
^^^^^^^^^^^^^^

.. java:method:: public void transportClose() throws SmtpMailException
   :outertype: SmtpMail

   Attempts to close the transport connection. If the transport is not connected, will not do anything.

   :throws SmtpMailException:

transportConnect
^^^^^^^^^^^^^^^^

.. java:method:: public void transportConnect() throws SmtpMailException
   :outertype: SmtpMail

   Attempts to connect the smtp transport object using the default values from the session.

   :throws SmtpMailException:

transportConnect
^^^^^^^^^^^^^^^^

.. java:method:: public void transportConnect(String host, int port, String password, String username) throws SmtpMailException
   :outertype: SmtpMail

   Attempts to connect the smtp transport object. Use -1 for the default port, and null for the default values from the session.

   :throws SmtpMailException:
   :throws MessagingException:

