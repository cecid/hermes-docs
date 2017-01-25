TemplateElement
===============

.. java:package:: hk.hku.cecid.piazza.commons.pagelet
   :noindex:

.. java:type:: public class TemplateElement

   A TemplateElement represents a composing element of a template. There are two types of template elements:

   ..

   #. Text
   #. Template Tag

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`Template`

Constructors
------------
TemplateElement
^^^^^^^^^^^^^^^

.. java:constructor:: public TemplateElement(String name)
   :outertype: TemplateElement

   Creates a new instance of TemplateElement which represents a template tag element.

   :param name: the element name.

TemplateElement
^^^^^^^^^^^^^^^

.. java:constructor:: public TemplateElement(String s, boolean isText)
   :outertype: TemplateElement

   Creates a new instance of TemplateElement.

   :param s: the element name or text if it is a text element.
   :param isText: true if this element is a text element.

Methods
-------
getName
^^^^^^^

.. java:method:: public String getName()
   :outertype: TemplateElement

   Gets the element name.

   :return: the element name or null if it is a text element.

getText
^^^^^^^

.. java:method:: public String getText()
   :outertype: TemplateElement

   Gets the text of this element.

   :return: the text of this element or null if it is a template tag element.

isText
^^^^^^

.. java:method:: public boolean isText()
   :outertype: TemplateElement

   Checks if this element is a text element.

   :return: true if this element is a text element.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: TemplateElement

   Returns a string representation of this element.

   :return: the text of this element if it is a text element or the element name otherwise.

   **See also:** :java:ref:`java.lang.Object.toString()`

