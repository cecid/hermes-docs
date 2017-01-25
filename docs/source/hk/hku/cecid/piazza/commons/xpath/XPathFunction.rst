.. java:import:: java.util Vector

XPathFunction
=============

.. java:package:: hk.hku.cecid.piazza.commons.xpath
   :noindex:

.. java:type:: public interface XPathFunction

   XPathFunction is an interface of any customized XPath functions.

   :author: Hugo Y. K. Lam

Methods
-------
execute
^^^^^^^

.. java:method:: public Object execute(Vector args)
   :outertype: XPathFunction

   Invoked when evaluating its corresponding function in the XPath.

   :param args: the arguments specifed in the XPath.
   :return: the result after execution.

