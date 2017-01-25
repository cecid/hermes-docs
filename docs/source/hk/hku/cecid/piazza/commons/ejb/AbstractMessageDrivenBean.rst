.. java:import:: javax.ejb MessageDrivenContext

AbstractMessageDrivenBean
=========================

.. java:package:: hk.hku.cecid.piazza.commons.ejb
   :noindex:

.. java:type:: public abstract class AbstractMessageDrivenBean implements javax.ejb.MessageDrivenBean, javax.jms.MessageListener

   The AbstractMessageDrivenBean class is an abstract class which implements the methods required for a Message Driven Bean, excepts the onMessage() method.

   :author: Hugo Y. K. Lam

Fields
------
mdc
^^^

.. java:field:: protected MessageDrivenContext mdc
   :outertype: AbstractMessageDrivenBean

Methods
-------
ejbCreate
^^^^^^^^^

.. java:method:: public void ejbCreate()
   :outertype: AbstractMessageDrivenBean

   A container invokes this method before it begins the life of the message-driven object.

ejbRemove
^^^^^^^^^

.. java:method:: public void ejbRemove()
   :outertype: AbstractMessageDrivenBean

   A container invokes this method before it ends the life of the message-driven object.

setMessageDrivenContext
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setMessageDrivenContext(MessageDrivenContext mdc)
   :outertype: AbstractMessageDrivenBean

   Sets the associated message-driven context. The container calls this method after the instance creation.

   :param mdc: A MessageDrivenContext interface for the instance.

