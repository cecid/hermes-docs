.. java:import:: javax.mail Folder

.. java:import:: javax.mail Session

.. java:import:: javax.mail Store

MailReceiver
============

.. java:package:: hk.hku.cecid.piazza.commons.net
   :noindex:

.. java:type:: public class MailReceiver extends MailConnector

   MailReceiver is a mail connector for making connections to incoming mail servers.

   :author: Hugo Y. K. Lam

Constructors
------------
MailReceiver
^^^^^^^^^^^^

.. java:constructor:: public MailReceiver(String host, String username, String password)
   :outertype: MailReceiver

   Creates a new instance of MailReceiver. The default protocol is POP3.

   :param host: the mail host.
   :param username: the user name for authentication.
   :param password: the password for authentication.

MailReceiver
^^^^^^^^^^^^

.. java:constructor:: public MailReceiver(String protocol, String host, String username, String password)
   :outertype: MailReceiver

   Creates a new instance of MailReceiver.

   :param protocol: the mail protocol.
   :param host: the mail host.
   :param username: the user name for authentication.
   :param password: the password for authentication.

Methods
-------
connect
^^^^^^^

.. java:method:: public synchronized void connect() throws ConnectionException
   :outertype: MailReceiver

   Connects to the incoming mail server.

   :throws ConnectionException: if unable to connect to the incoming mail server or a connection to the server has already been established.

disconnect
^^^^^^^^^^

.. java:method:: public synchronized void disconnect() throws ConnectionException
   :outertype: MailReceiver

   Disconnects from the incoming mail server.

   :throws ConnectionException: if unable to disconnect from the incoming mail server or the connection to the server has not been established.

openFolder
^^^^^^^^^^

.. java:method:: public synchronized Folder openFolder(String folderName) throws ConnectionException
   :outertype: MailReceiver

   Opens a specified folder for read-write access.

   :param folderName: the name of the folder to be opened.
   :throws ConnectionException: if unable to open the specified folder or the connection to the incoming mail server has not yet been established.
   :return: the opened folder.

openFolder
^^^^^^^^^^

.. java:method:: public synchronized Folder openFolder(String folderName, boolean readOnly) throws ConnectionException
   :outertype: MailReceiver

   Opens a specified folder.

   :param folderName: the name of the folder to be opened.
   :param readOnly: true if the folder should be readonly.
   :throws ConnectionException: if unable to open the specified folder or the connection to the incoming mail server has not yet been established.
   :return: the opened folder.

openInbox
^^^^^^^^^

.. java:method:: public synchronized Folder openInbox() throws ConnectionException
   :outertype: MailReceiver

   Opens the inbox for read-write access.

   :throws ConnectionException: if unable to open the inbox or the connection to the incoming mail server has not yet been established.
   :return: the opened inbox.

