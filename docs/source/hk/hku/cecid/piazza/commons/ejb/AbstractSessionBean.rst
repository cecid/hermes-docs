.. java:import:: javax.ejb SessionBean

.. java:import:: javax.ejb SessionContext

AbstractSessionBean
===================

.. java:package:: hk.hku.cecid.piazza.commons.ejb
   :noindex:

.. java:type:: public class AbstractSessionBean implements SessionBean

   The AbstractSessionBean class is an abstract class which implements the methods required for a Session Bean, except the ejbCreate(...) methods and the business methods.

   :author: Hugo Y. K. Lam

Fields
------
context
^^^^^^^

.. java:field:: protected SessionContext context
   :outertype: AbstractSessionBean

   The session context.

Constructors
------------
AbstractSessionBean
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AbstractSessionBean()
   :outertype: AbstractSessionBean

   Creates a new instance of AbstractSessionBean.

Methods
-------
ejbActivate
^^^^^^^^^^^

.. java:method:: public void ejbActivate()
   :outertype: AbstractSessionBean

   A container invokes this method when the instance is activated from its "passive" state.

   **See also:** :java:ref:`javax.ejb.SessionBean.ejbActivate()`

ejbCreate
^^^^^^^^^

.. java:method:: public void ejbCreate()
   :outertype: AbstractSessionBean

   A container invokes this method when the instance is created. This is a default and mandatory creator in a stateless session bean.

   **See also:** :java:ref:`javax.ejb.SessionBean.ejbActivate()`

ejbPassivate
^^^^^^^^^^^^

.. java:method:: public void ejbPassivate()
   :outertype: AbstractSessionBean

   A container invokes this method before the instance enters the "passive" state.

   **See also:** :java:ref:`javax.ejb.SessionBean.ejbPassivate()`

ejbRemove
^^^^^^^^^

.. java:method:: public void ejbRemove()
   :outertype: AbstractSessionBean

   A container invokes this method before it ends the life of the session object.

   **See also:** :java:ref:`javax.ejb.SessionBean.ejbRemove()`

setSessionContext
^^^^^^^^^^^^^^^^^

.. java:method:: public void setSessionContext(SessionContext ctx)
   :outertype: AbstractSessionBean

   Set the associated session context.

   **See also:** :java:ref:`javax.ejb.SessionBean.setSessionContext(javax.ejb.SessionContext)`

