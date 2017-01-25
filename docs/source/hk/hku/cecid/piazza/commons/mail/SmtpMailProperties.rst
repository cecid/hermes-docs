.. java:import:: java.util Properties

SmtpMailProperties
==================

.. java:package:: hk.hku.cecid.piazza.commons.mail
   :noindex:

.. java:type:: public class SmtpMailProperties

   A class wrapping the SMTP Properties.

   :author: Joel Matsumoto

Constructors
------------
SmtpMailProperties
^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SmtpMailProperties()
   :outertype: SmtpMailProperties

Methods
-------
getFrom
^^^^^^^

.. java:method:: public String getFrom()
   :outertype: SmtpMailProperties

   Get the from property.

   :return: String

getHost
^^^^^^^

.. java:method:: public String getHost()
   :outertype: SmtpMailProperties

   Return the host.

   :return: host

getPassword
^^^^^^^^^^^

.. java:method:: public String getPassword()
   :outertype: SmtpMailProperties

   Get the password

   :return: String

getPort
^^^^^^^

.. java:method:: public int getPort() throws NumberFormatException
   :outertype: SmtpMailProperties

   Get the port number.

   :return: int

getProperties
^^^^^^^^^^^^^

.. java:method:: public Properties getProperties()
   :outertype: SmtpMailProperties

   Get the properties data structure.

   :return: Properties

getProperty
^^^^^^^^^^^

.. java:method:: public String getProperty(String key)
   :outertype: SmtpMailProperties

   Get the value of the key.

   :param key:
   :return: String

getUsername
^^^^^^^^^^^

.. java:method:: public String getUsername()
   :outertype: SmtpMailProperties

   Get the default username

   :return: username

setFrom
^^^^^^^

.. java:method:: public void setFrom(String from)
   :outertype: SmtpMailProperties

   Set the from property. If no from is set, uses msg.getFrom() or InternetAddress.getLocalAddress().

   :param from:

setHost
^^^^^^^

.. java:method:: public void setHost(String host)
   :outertype: SmtpMailProperties

   Set the default host to connect to.

   :param host:

setPassword
^^^^^^^^^^^

.. java:method:: public void setPassword(String pw)
   :outertype: SmtpMailProperties

   Set the password for servers needing authentication

   :param pw:

setPort
^^^^^^^

.. java:method:: public void setPort(int port)
   :outertype: SmtpMailProperties

   Set the port number. Defaults to 25.

   :param port:

setProperty
^^^^^^^^^^^

.. java:method:: public void setProperty(String key, String value)
   :outertype: SmtpMailProperties

   Add the key/value pair to trhe property structure.

   :param key:
   :param value:

setUsername
^^^^^^^^^^^

.. java:method:: public void setUsername(String user)
   :outertype: SmtpMailProperties

   Set the default username to be used

   :param user:

