.. java:import:: javax.xml.parsers DocumentBuilder

.. java:import:: javax.xml.parsers DocumentBuilderFactory

.. java:import:: javax.xml.transform TransformerException

.. java:import:: com.sun.org.apache.xml.internal.utils PrefixResolverDefault

.. java:import:: com.sun.org.apache.xpath.internal XPath

.. java:import:: com.sun.org.apache.xpath.internal XPathContext

.. java:import:: com.sun.org.apache.xpath.internal XPathVisitor

.. java:import:: com.sun.org.apache.xpath.internal.objects XObject

.. java:import:: org.w3c.dom Node

XPathExecutor
=============

.. java:package:: hk.hku.cecid.piazza.commons.xpath
   :noindex:

.. java:type:: public class XPathExecutor

   XPathExecutor is an executor which evaluates a given xpath and yields the result.

   \ *Example:*\

   .. parsed-literal::

      XPathExecutor exec = new XPathExecutor(getDocument("doc.xml"));

      exec.registerFunction("http://example.com", "sum", new MySum());

      System.out.println(exec.eval( "3 + number('3') + eg:sum(3, 4, '5.1') + /values/one  - 2"));

      // The result will be '17.1'

   :author: Hugo Y. K. Lam

Constructors
------------
XPathExecutor
^^^^^^^^^^^^^

.. java:constructor:: public XPathExecutor()
   :outertype: XPathExecutor

   Creates a new instance of XPathExecutor.

XPathExecutor
^^^^^^^^^^^^^

.. java:constructor:: public XPathExecutor(Node document)
   :outertype: XPathExecutor

   Creates a new instance of XPathExecutor.

   :param document: the document containing the context being queried and the namespaces being referenced.

XPathExecutor
^^^^^^^^^^^^^

.. java:constructor:: public XPathExecutor(Node context, Node namespaces)
   :outertype: XPathExecutor

   Creates a new instance of XPathExecutor.

   :param context: the document containing the context being queried.
   :param namespaces: the document containing the namespaces being referenced.

Methods
-------
eval
^^^^

.. java:method:: public Object eval(String expression) throws TransformerException
   :outertype: XPathExecutor

   Evaluates an XPath expression.

   :param expression: the XPath expression.
   :throws TransformerException: if unable to transform the expression.
   :return: the evaluated result.

eval
^^^^

.. java:method:: public Object eval(String expression, Node context) throws TransformerException
   :outertype: XPathExecutor

   Evaluates an XPath expression.

   :param expression: the XPath expression.
   :param context: the document containing the context being queried.
   :throws TransformerException: if unable to transform the expression.
   :return: the evaluated result.

registerFunction
^^^^^^^^^^^^^^^^

.. java:method:: public void registerFunction(String ns, String funcName, XPathFunction func)
   :outertype: XPathExecutor

   Registers a function to be used in an XPath.

   :param ns: the namespace of the function.
   :param funcName: the function name.
   :param func: the function implementation.

visit
^^^^^

.. java:method:: public void visit(String expression, XPathVisitor visitor) throws TransformerException
   :outertype: XPathExecutor

   Evaluates an XPath expression.

   :param expression: the XPath expression.
   :param visitor: the XPath visitor.
   :throws TransformerException: if unable to transform the expression.

