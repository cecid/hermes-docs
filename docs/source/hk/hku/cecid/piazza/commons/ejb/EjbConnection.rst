.. java:import:: java.net InetAddress

.. java:import:: java.util Hashtable

.. java:import:: javax.naming InitialContext

EjbConnection
=============

.. java:package:: hk.hku.cecid.piazza.commons.ejb
   :noindex:

.. java:type:: public class EjbConnection

   An EjbConnection represents a connection to the initial context by which the specified EJBHome can be looked up. The URL connection string for an EJBConnection should comply the following format: PROVIDER_URL@INITIAL_CONTEXT_FACTORY {@SECURITY_PROTOCOL}

   :author: Hugo Y. K. Lam

Constructors
------------
EjbConnection
^^^^^^^^^^^^^

.. java:constructor:: public EjbConnection(String url, String username, String password)
   :outertype: EjbConnection

   Creates a new instance of EjbConnection.

Methods
-------
close
^^^^^

.. java:method:: public synchronized void close() throws EjbConnectionException
   :outertype: EjbConnection

   Closes this connection and releases any resources associated.

   :throws EjbConnectionException: if errors occurred during closing the connection or, the connection has not yet been connected or has been closed already.

connect
^^^^^^^

.. java:method:: public synchronized void connect() throws EjbConnectionException
   :outertype: EjbConnection

   Connects to the destination URL using the username and password stored in this connection.

   :throws EjbConnectionException: if errors occurred during the establishment of connection.

connect
^^^^^^^

.. java:method:: public synchronized void connect(String username, String password) throws EjbConnectionException
   :outertype: EjbConnection

   Connects to the destination URL using the specified username and password.

   :param username: the username used to connect. null if authentication is not required.
   :param password: the password used to connect. null if authentication is not required.
   :throws EjbConnectionException: if errors occurred during the establishment of connection or, the connection has been connected or closed already.

finalize
^^^^^^^^

.. java:method:: protected void finalize() throws Throwable
   :outertype: EjbConnection

   Closes this connection in finalization.

   **See also:** :java:ref:`java.lang.Object.finalize()`

getUrl
^^^^^^

.. java:method:: public String getUrl()
   :outertype: EjbConnection

   Gets the URL of this connection.

   :return: the URL of this connection.

getUsername
^^^^^^^^^^^

.. java:method:: public String getUsername()
   :outertype: EjbConnection

   Gets the username used for this connection.

   :return: the username used in this connection.

lookupHome
^^^^^^^^^^

.. java:method:: public Object lookupHome(String jndiName, Class narrowTo) throws EjbConnectionException
   :outertype: EjbConnection

   Retrieves the EJBHome by looking it up using the specified JNDI name. The EJBHome will be narrowed to the specified class if it is a remote interface.

   :param jndiName: the JNDI name for the EJBHome to be looked up.
   :param narrowTo: the class to which the EJBHome should be narrowed.
   :throws EjbConnectionException: if there is a naming or narrowing error.
   :throws NullPointerException: if \ ``narrowTo is null.``\
   :return: the EJBHome bound to the specified JNDI name.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: EjbConnection

   Returns a string representation of this object, which is the URL.

   **See also:** :java:ref:`java.lang.Object.toString()`

