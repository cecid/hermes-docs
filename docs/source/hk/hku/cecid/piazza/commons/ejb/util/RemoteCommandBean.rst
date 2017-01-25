.. java:import:: hk.hku.cecid.piazza.commons.ejb AbstractSessionBean

.. java:import:: hk.hku.cecid.piazza.commons.util InstanceException

.. java:import:: java.lang.reflect InvocationTargetException

RemoteCommandBean
=================

.. java:package:: hk.hku.cecid.piazza.commons.ejb.util
   :noindex:

.. java:type:: public class RemoteCommandBean extends AbstractSessionBean

   RemoteCommandBean is the session bean class of RemoteCommand. It can execute a registered command with the given parameters.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`RemoteCommand`, :java:ref:`RemoteCommandHandler`

Methods
-------
execute
^^^^^^^

.. java:method:: public Object execute(String cmdName, Object[] parameters) throws InstanceException, InvocationTargetException
   :outertype: RemoteCommandBean

   Executes a registered command with the given parameters.

   :param cmdName: the command name.
   :param parameters: parameters for the target method invocation.
   :throws InstanceException: if the instance of the target class cannot be created or the method could not be invoked.
   :throws InvocationTargetException: if the invoked method has thrown an exception.
   :throws NullPointerException: if the command is not registered.
   :return: the object returned by the invoked method.

