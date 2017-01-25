.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.ejb EjbConnection

.. java:import:: hk.hku.cecid.piazza.commons.ejb EjbConnectionFactory

.. java:import:: hk.hku.cecid.piazza.commons.util ArrayUtilities

.. java:import:: hk.hku.cecid.piazza.commons.util Instance

.. java:import:: hk.hku.cecid.piazza.commons.util InstanceException

.. java:import:: java.lang.reflect InvocationTargetException

.. java:import:: java.net InetAddress

.. java:import:: java.net UnknownHostException

.. java:import:: java.rmi RemoteException

.. java:import:: java.util Enumeration

.. java:import:: java.util Hashtable

.. java:import:: java.util Properties

RemoteCommandHandler
====================

.. java:package:: hk.hku.cecid.piazza.commons.ejb.util
   :noindex:

.. java:type:: public final class RemoteCommandHandler

   RemoteCommandHandler is a handler class for invoking the RemoteCommand bean. It invokes the bean by using the command name and parameters specified by the caller. The given command must be registered beforehand on both side with a set of command properties in Java properties format:

   +------------+----------------------------------------------------------------------+
   | Key        | Value                                                                |
   +============+======================================================================+
   | url        | The connection URL (see EjbConnection)                               |
   +------------+----------------------------------------------------------------------+
   | username   | The username for the connection                                      |
   +------------+----------------------------------------------------------------------+
   | password   | The password for the connection                                      |
   +------------+----------------------------------------------------------------------+
   | class      | The class name/object to be excuted                                  |
   +------------+----------------------------------------------------------------------+
   | method     | The method of the class to be excuted                                |
   +------------+----------------------------------------------------------------------+
   | parameters | The parameter types, separated by comma, of the method to be excuted |
   +------------+----------------------------------------------------------------------+

   If it fails to invoke the bean, it will invoke the target class locally.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`RemoteCommandBean`, :java:ref:`EjbConnection`

Methods
-------
execute
^^^^^^^

.. java:method:: public static Object execute(String cmdName, Object[] parameters) throws RemoteException, InstanceException, InvocationTargetException
   :outertype: RemoteCommandHandler

   Executes a registered command with the given parameters.

   :param cmdName: the command name.
   :param parameters: parameters for the target method invocation.
   :throws RemoteException: if there is a remote exception occurred.
   :throws InstanceException: if the instance of the target class cannot be created or the method could not be invoked.
   :throws InvocationTargetException: if the invoked method has thrown an exception.
   :throws NullPointerException: if the command is not registered.
   :return: the object returned by the invoked method.

executeLocal
^^^^^^^^^^^^

.. java:method:: static Object executeLocal(String cmdName, Object[] parameters) throws InstanceException, InvocationTargetException
   :outertype: RemoteCommandHandler

   Executes a registered command locally with the given parameters.

   :param cmdName: the command name.
   :param parameters: parameters for the target method invocation.
   :throws InstanceException: if the instance of the target class cannot be created or the method could not be invoked.
   :throws InvocationTargetException: if the invoked method has thrown an exception.
   :throws NullPointerException: if the command is not registered.
   :return: the object returned by the invoked method.

getCommand
^^^^^^^^^^

.. java:method:: public static Properties getCommand(String name)
   :outertype: RemoteCommandHandler

   Gets the command properties by its name.

   :param name: the command name.
   :throws NullPointerException: if the command is not registered.
   :return: the command properties.

getCommandNames
^^^^^^^^^^^^^^^

.. java:method:: public static Enumeration getCommandNames()
   :outertype: RemoteCommandHandler

   Gets the names of the regsitered commands.

   :return: the names of the regsitered commands.

register
^^^^^^^^

.. java:method:: public static void register(String cmdName, Properties command)
   :outertype: RemoteCommandHandler

   Register a command to this handler.

   :param cmdName: the command name.
   :param command: the command properties.

unregister
^^^^^^^^^^

.. java:method:: public static void unregister(String cmdName)
   :outertype: RemoteCommandHandler

   Unregister a command from this handler.

   :param cmdName: the command name.

