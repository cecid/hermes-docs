.. java:import:: javax.ejb EntityBean

.. java:import:: javax.ejb EntityContext

AbstractEntityBean
==================

.. java:package:: hk.hku.cecid.piazza.commons.ejb
   :noindex:

.. java:type:: public class AbstractEntityBean implements EntityBean

   The AbstractEntityBean class is an abstract class which implements the methods required for an Entity Bean, except the ejbCreateXXX() methods which have been defined in the home interface.

   :author: Hugo Y. K. Lam

Fields
------
context
^^^^^^^

.. java:field:: protected EntityContext context
   :outertype: AbstractEntityBean

   The entity context.

Constructors
------------
AbstractEntityBean
^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AbstractEntityBean()
   :outertype: AbstractEntityBean

   Creates a new instance of AbstractEntityBean.

Methods
-------
ejbActivate
^^^^^^^^^^^

.. java:method:: public void ejbActivate()
   :outertype: AbstractEntityBean

   A container invokes this method when the instance is taken out of the pool of available instances to become associated with a specific EJB object.

   **See also:** :java:ref:`javax.ejb.EntityBean.ejbActivate()`

ejbLoad
^^^^^^^

.. java:method:: public void ejbLoad()
   :outertype: AbstractEntityBean

   A container invokes this method to instruct the instance to synchronize its state by loading it state from the underlying database.

   **See also:** :java:ref:`javax.ejb.EntityBean.ejbLoad()`

ejbPassivate
^^^^^^^^^^^^

.. java:method:: public void ejbPassivate()
   :outertype: AbstractEntityBean

   A container invokes this method on an instance before the instance becomes disassociated with a specific EJB object.

   **See also:** :java:ref:`javax.ejb.EntityBean.ejbPassivate()`

ejbRemove
^^^^^^^^^

.. java:method:: public void ejbRemove()
   :outertype: AbstractEntityBean

   A container invokes this method before it removes the EJB object that is currently associated with the instance.

   **See also:** :java:ref:`javax.ejb.EntityBean.ejbRemove()`

ejbStore
^^^^^^^^

.. java:method:: public void ejbStore()
   :outertype: AbstractEntityBean

   **See also:** :java:ref:`javax.ejb.EntityBean.ejbStore()`

setEntityContext
^^^^^^^^^^^^^^^^

.. java:method:: public void setEntityContext(EntityContext ctx)
   :outertype: AbstractEntityBean

   Sets the associated entity context.

   **See also:** :java:ref:`javax.ejb.EntityBean.setEntityContext(javax.ejb.EntityContext)`

unsetEntityContext
^^^^^^^^^^^^^^^^^^

.. java:method:: public void unsetEntityContext()
   :outertype: AbstractEntityBean

   Unset the associated entity context.

   **See also:** :java:ref:`javax.ejb.EntityBean.unsetEntityContext()`

