.. java:import:: java.util ArrayList

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: java.util.regex Matcher

.. java:import:: java.util.regex Pattern

Template
========

.. java:package:: hk.hku.cecid.piazza.commons.pagelet
   :noindex:

.. java:type:: public class Template

   A Template is a parser which tokenizes a given template into a list of template elements. There are two types of template elements:

   ..

   #. Text
   #. Template Tag

   Hence, a template is composed of a mixture of text and template tags. A template tag is recognized by the following pattern in the content: \ ``<!--[\\s]*template-((.*?))[\\s]*-->``\

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`TemplateElement`

Constructors
------------
Template
^^^^^^^^

.. java:constructor:: public Template(String s)
   :outertype: Template

   Creates a new instance of Template.

   :param s: the template.

Methods
-------
hasMoreElements
^^^^^^^^^^^^^^^

.. java:method:: public boolean hasMoreElements()
   :outertype: Template

   Checks if there are anymore elements in this template. This method will always return false if this template is not yet parsed. More, each invocation of nextElement() may also affect the result of this method.

   :return: true if there are more elements in this template.

   **See also:** :java:ref:`.nextElement()`

nextElement
^^^^^^^^^^^

.. java:method:: public TemplateElement nextElement()
   :outertype: Template

   Gets the next template element. This method will always return null if this template is not yet parsed.

   :return: the next template element.

parse
^^^^^

.. java:method:: public void parse()
   :outertype: Template

   Parses the template content and initializes this template.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: Template

   Returns a string representation of this template. This method simply returns the original template content.

   :return: a string representation of this template.

   **See also:** :java:ref:`java.lang.Object.toString()`

