.. java:import:: java.lang.reflect Constructor

.. java:import:: java.lang.reflect InvocationTargetException

.. java:import:: java.lang.reflect Method

Instance
========

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public final class Instance

   Instance represents an object instance. It wraps the actual object instance and provides methods for invoking the object's methods.

   :author: Hugo Y. K. Lam

Constructors
------------
Instance
^^^^^^^^

.. java:constructor:: public Instance(Object source) throws InstanceException
   :outertype: Instance

   Creates a new instance of Instance.

   :param source: an object instance, its class, or its class name.
   :throws InstanceException: if errors occurred in the creation of the instance.

Instance
^^^^^^^^

.. java:constructor:: public Instance(Object source, ClassLoader loader) throws InstanceException
   :outertype: Instance

   Creates a new instance of Instance.

   :param source: an object instance, its class, or its class name.
   :param loader: the class loader for loading the instance's class.
   :throws InstanceException: if errors occurred in the creation of the instance.

Instance
^^^^^^^^

.. java:constructor:: public Instance(Object source, Class[] initargTypes, Object[] initargs) throws InstanceException
   :outertype: Instance

   Creates a new instance of Instance.

   :param source: an object instance, its class, or its class name.
   :param initargTypes: the constructor's parameter types.
   :param initargs: the constructor's parameters.
   :throws InstanceException: if errors occurred in the creation of the instance.

Instance
^^^^^^^^

.. java:constructor:: public Instance(Object source, ClassLoader loader, Class[] initargTypes, Object[] initargs) throws InstanceException
   :outertype: Instance

   Creates a new instance of Instance.

   :param source: an object instance, its class, or its class name.
   :param loader: the class loader for loading the instance's class.
   :param initargTypes: the constructor's parameter types.
   :param initargs: the constructor's parameters.
   :throws InstanceException: if errors occurred in the creation of the instance.

Methods
-------
getObject
^^^^^^^^^

.. java:method:: public Object getObject()
   :outertype: Instance

   Gets the object this instance represents.

   :return: the object this instance represents.

invoke
^^^^^^

.. java:method:: public Object invoke(String methodName) throws InstanceException, InvocationTargetException
   :outertype: Instance

   Invokes a method in the object that this instance represents.

   :param methodName: the method name.
   :throws InstanceException: if the method could not be invoked.
   :throws InvocationTargetException: if the invoked method has thrown an exception.
   :return: the object returned by the invoked method.

invoke
^^^^^^

.. java:method:: public Object invoke(String methodName, Object[] parameters) throws InstanceException, InvocationTargetException
   :outertype: Instance

   Invokes a method in the object that this instance represents.

   :param methodName: the method name.
   :param parameters: the parameters.
   :throws InstanceException: if the method could not be invoked.
   :throws InvocationTargetException: if the invoked method has thrown an exception.
   :return: the object returned by the invoked method.

invoke
^^^^^^

.. java:method:: public Object invoke(String methodName, Object[] pt, Object[] parameters) throws InstanceException, InvocationTargetException
   :outertype: Instance

   Invokes a method in the object that this instance represents.

   :param methodName: the method name.
   :param pt: the parameter types.
   :param parameters: the parameters.
   :throws InstanceException: if the method could not be invoked.
   :throws InvocationTargetException: if the invoked method has thrown an exception.
   :return: the object returned by the invoked method.

isMethodExist
^^^^^^^^^^^^^

.. java:method:: public boolean isMethodExist(String name, Object[] pt)
   :outertype: Instance

   Check if the specified method exists.

   :param name: the method name.
   :param pt: the parameter types.
   :return: true if the specified method exists.

