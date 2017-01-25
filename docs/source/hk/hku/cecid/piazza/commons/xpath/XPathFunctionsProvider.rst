.. java:import:: java.util Hashtable

.. java:import:: java.util Vector

.. java:import:: javax.xml.transform TransformerException

.. java:import:: com.sun.org.apache.xpath.internal ExtensionsProvider

.. java:import:: com.sun.org.apache.xpath.internal.functions FuncExtFunction

XPathFunctionsProvider
======================

.. java:package:: hk.hku.cecid.piazza.commons.xpath
   :noindex:

.. java:type::  class XPathFunctionsProvider implements ExtensionsProvider

   XPathFunctionsProvider implements the Apache XPath Extensions Provider. It is solely used by the XPathExecutor in building an Apache XPath Context.

   :author: Hugo Y. K. Lam

Methods
-------
elementAvailable
^^^^^^^^^^^^^^^^

.. java:method:: public boolean elementAvailable(String ns, String elemName)
   :outertype: XPathFunctionsProvider

   Checks if the given element is available.

   :param ns: the namespace of the element.
   :param elemName: the element name.
   :return: false in any way.

   **See also:** :java:ref:`org.apache.xpath.ExtensionsProvider.elementAvailable(java.lang.String,java.lang.String)`

extFunction
^^^^^^^^^^^

.. java:method:: public Object extFunction(String ns, String funcName, Vector argVec, Object methodKey) throws TransformerException
   :outertype: XPathFunctionsProvider

   Executes the extension function.

   :param ns: the namespace of the function.
   :param funcName: the function name.
   :param argVec: the function arguments.
   :param methodKey: the method key.
   :throws TransformerException: if the function executed with errors or the function is not available.
   :return: the execution result.

   **See also:** :java:ref:`org.apache.xpath.ExtensionsProvider.extFunction(java.lang.String,java.lang.String,java.util.Vector,java.lang.Object)`

extFunction
^^^^^^^^^^^

.. java:method:: public Object extFunction(FuncExtFunction funcExtFunction, Vector vec) throws TransformerException
   :outertype: XPathFunctionsProvider

functionAvailable
^^^^^^^^^^^^^^^^^

.. java:method:: public boolean functionAvailable(String ns, String funcName)
   :outertype: XPathFunctionsProvider

   Checks if the given function is available.

   :param ns: the namespace of the function.
   :param funcName: the function name.
   :return: true if the given function is available.

   **See also:** :java:ref:`org.apache.xpath.ExtensionsProvider.functionAvailable(java.lang.String,java.lang.String)`

regsiterFunction
^^^^^^^^^^^^^^^^

.. java:method:: public void regsiterFunction(String ns, String funcName, XPathFunction func)
   :outertype: XPathFunctionsProvider

   Registers a function to this provider.

   :param ns: the namespace of the function.
   :param funcName: the function name.
   :param func: the function implementation.

