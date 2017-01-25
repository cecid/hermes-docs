RemoteCommandHome
=================

.. java:package:: hk.hku.cecid.piazza.commons.ejb.util
   :noindex:

.. java:type:: public interface RemoteCommandHome extends javax.ejb.EJBHome

   RemoteCommandHome is the home interface of RemoteCommand.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`RemoteCommand`

Methods
-------
create
^^^^^^

.. java:method:: public RemoteCommand create() throws javax.ejb.CreateException, java.rmi.RemoteException
   :outertype: RemoteCommandHome

   Creates a remote instance of RemoteCommand.

   :throws javax.ejb.CreateException: if the remote instance could not be created.
   :throws java.rmi.RemoteException: if there is a remote exception occurred.
   :return: a RemoteCommand remote instance.

