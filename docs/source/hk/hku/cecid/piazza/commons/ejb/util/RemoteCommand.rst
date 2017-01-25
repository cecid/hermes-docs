.. java:import:: hk.hku.cecid.piazza.commons.util InstanceException

.. java:import:: java.lang.reflect InvocationTargetException

RemoteCommand
=============

.. java:package:: hk.hku.cecid.piazza.commons.ejb.util
   :noindex:

.. java:type:: public interface RemoteCommand extends javax.ejb.EJBObject

   RemoteCommand is the remote interface of RemoteCommandBean. It can execute a remote command with the given parameters.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`RemoteCommandBean`, :java:ref:`RemoteCommandHandler`

Methods
-------
execute
^^^^^^^

.. java:method:: public Object execute(String cmdName, Object[] parameters) throws java.rmi.RemoteException, InstanceException, InvocationTargetException
   :outertype: RemoteCommand

   Executes a registered command with the given parameters.

   :param cmdName: the command name.
   :param parameters: parameters for the target method invocation.
   :throws java.rmi.RemoteException: if there is a remote exception occurred.
   :throws InstanceException: if the instance of the target class cannot be created or the method could not be invoked.
   :throws InvocationTargetException: if the invoked method has thrown an exception.
   :throws NullPointerException: if the command is not registered.
   :return: the object returned by the invoked method.

