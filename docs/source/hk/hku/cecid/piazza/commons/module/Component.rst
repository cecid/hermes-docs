.. java:import:: java.util Properties

Component
=========

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public abstract class Component

   Component represents a module component. Subclasses should override the init() method for their own initializations.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`Module`

Methods
-------
getId
^^^^^

.. java:method:: public String getId()
   :outertype: Component

   Gets the component ID.

   :return: the component ID.

getModule
^^^^^^^^^

.. java:method:: public Module getModule()
   :outertype: Component

   Gets the parent module of this component.

   :return: the parent module of this component.

getName
^^^^^^^

.. java:method:: public String getName()
   :outertype: Component

   Gets the name of this component.

   :return: the name of this component.

getParameters
^^^^^^^^^^^^^

.. java:method:: public Properties getParameters()
   :outertype: Component

   Gets the parameters of this component.

   :return: the parameters of this component.

init
^^^^

.. java:method:: protected void init() throws Exception
   :outertype: Component

   Invoked for initialization.

   :throws Exception: if there is any error in the initialization.

setId
^^^^^

.. java:method:: public void setId(String id)
   :outertype: Component

   Sets the component ID.

   :param id: the component ID.

setModule
^^^^^^^^^

.. java:method:: protected void setModule(Module module)
   :outertype: Component

   Sets the parent module of this component.

   :param module: the parent module of this component.

setName
^^^^^^^

.. java:method:: protected void setName(String name)
   :outertype: Component

   Sets the name of this component.

   :param name: the name of this component.

setParameters
^^^^^^^^^^^^^

.. java:method:: protected void setParameters(Properties parameters)
   :outertype: Component

   Sets the parameters of this component.

   :param parameters: the parameters of this component.

