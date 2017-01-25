.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: java.net URL

EjbConnectionFactory
====================

.. java:package:: hk.hku.cecid.piazza.commons.ejb
   :noindex:

.. java:type:: public final class EjbConnectionFactory

   EjbConnectionFactory is a concrete factory class for creating EjbConnection by using a pre-defined set of properties.

   :author: Hugo Y. K. Lam

Methods
-------
configure
^^^^^^^^^

.. java:method:: public static void configure(URL url) throws EjbConnectionException
   :outertype: EjbConnectionFactory

   Configures the EjbConnectionFactory from the configuration located by the specifed URL. Expected to be called before any other methods are called.

   :param url: The URL of the configuration file.
   :throws EjbConnectionException: if any errors in configuring the EjbConnectionFactory.

createConnection
^^^^^^^^^^^^^^^^

.. java:method:: public static EjbConnection createConnection() throws EjbConnectionException
   :outertype: EjbConnectionFactory

   Creates a new EjbConnection. The url, username and password will be retrieved from the default properties.

   :return: a new EjbConnection.

createConnection
^^^^^^^^^^^^^^^^

.. java:method:: public static EjbConnection createConnection(String url)
   :outertype: EjbConnectionFactory

   Creates a new EjbConnection. The username and password will be retrieved from the default properties.

   :param url: the URL for this connection.
   :return: a new EjbConnection.

createConnection
^^^^^^^^^^^^^^^^

.. java:method:: public static EjbConnection createConnection(String url, String username, String password)
   :outertype: EjbConnectionFactory

   Creates a new EjbConnection.

   :param url: the URL for this connection.
   :param username: the username for authentication.
   :param password: the password for authentication.
   :return: a new EjbConnection.

