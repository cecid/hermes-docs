.. java:import:: java.util Properties

.. java:import:: javax.mail Authenticator

.. java:import:: javax.mail PasswordAuthentication

.. java:import:: javax.mail Session

MailConnector
=============

.. java:package:: hk.hku.cecid.piazza.commons.net
   :noindex:

.. java:type:: public abstract class MailConnector

   MailConnector is an abstract connector for making connection to mail hosts. The configuration of mail connector is mainly through the standard java properties injection. You can always use either \ :java:ref:`addProperties(Properties)`\  or \ :java:ref:`getProperties()`\  to set or get the current configuration of this mail connector. For the detail of the properties key, read \ `here <http://java.sun.com/products/javamail/javadocs/index.html>`_\  1.0.1 - Add help method for enabling black box debug mode through \ :java:ref:`setDebug(boolean)`\

   :author: Hugo Y. K. Lam,, Twinsen Tsang (modifers)

Constructors
------------
MailConnector
^^^^^^^^^^^^^

.. java:constructor:: public MailConnector(String protocol, String host)
   :outertype: MailConnector

   Creates a new instance of MailConnector.

   :param protocol: the mail protocol.
   :param host: the mail host.

MailConnector
^^^^^^^^^^^^^

.. java:constructor:: public MailConnector(String protocol, String host, String username, String password)
   :outertype: MailConnector

   Creates a new instance of MailConnector.

   :param protocol: the mail protocol.
   :param host: the mail host.
   :param username: the user name for authentication.
   :param password: the password for authentication.

Methods
-------
addProperties
^^^^^^^^^^^^^

.. java:method:: public void addProperties(Properties properties)
   :outertype: MailConnector

   Adds the given mail properties to the underlying mail properties used by this connector.

   :param properties: the properties to be added.

addProperty
^^^^^^^^^^^

.. java:method:: public void addProperty(String propKey, String propValue)
   :outertype: MailConnector

   Adds a property to the underlying mail properties used by this connector.

   :param propKey: the property key.
   :param propValue: the property value.

createSession
^^^^^^^^^^^^^

.. java:method:: public Session createSession()
   :outertype: MailConnector

   Creates a mail session from the underlying mail properties.

   :return: the mail session.

getHost
^^^^^^^

.. java:method:: public String getHost()
   :outertype: MailConnector

   Gets the host to which this mail connector connects.

   :return: the mail host.

getIsDebug
^^^^^^^^^^

.. java:method:: public boolean getIsDebug()
   :outertype: MailConnector

   Get whether the mail connector is under debug mode.

getProperties
^^^^^^^^^^^^^

.. java:method:: public Properties getProperties()
   :outertype: MailConnector

   Gets the underlying mail properties used by this connector.

   :return: the mail properties.

getProtocol
^^^^^^^^^^^

.. java:method:: public String getProtocol()
   :outertype: MailConnector

   Gets the protocol that this mail connector uses.

   :return: the mail protocol.

setDebug
^^^^^^^^

.. java:method:: public void setDebug(boolean on)
   :outertype: MailConnector

   Set whether the mail connector is under debug mode.

   :param on: The flag whether debug mode is switched on for this mail connector.

