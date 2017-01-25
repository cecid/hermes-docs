.. java:import:: java.util List

.. java:import:: java.util Vector

MenuComponent
=============

.. java:package:: hk.hku.cecid.piazza.corvus.admin.menu
   :noindex:

.. java:type:: public class MenuComponent implements Comparable

   A MenuComponent represents a menu-type component having the following characteristics:

   ..

   * A sequence number which indicates the menu position.
   * A name or caption of the menu.
   * A description of the menu.
   * A link of the menu.
   * A parent menu.
   * A list of child menus.
   * Visibility.

   :author: Hugo Y. K. Lam

Methods
-------
addChild
^^^^^^^^

.. java:method:: public void addChild(MenuComponent child)
   :outertype: MenuComponent

   Adds a child menu.

   :param child: the child menu to be added.

compareTo
^^^^^^^^^

.. java:method:: public int compareTo(Object o)
   :outertype: MenuComponent

   Compares this menu component to another menu component with their sequence numbers. If the sequence numbers are the same, their IDs will be compared.

   **See also:** :java:ref:`java.lang.Comparable.compareTo(java.lang.Object)`

getChildren
^^^^^^^^^^^

.. java:method:: public List getChildren()
   :outertype: MenuComponent

   Gets the child menus.

   :return: the child menus.

getDescription
^^^^^^^^^^^^^^

.. java:method:: public String getDescription()
   :outertype: MenuComponent

   Gets the description of this menu component.

   :return: the description of this menu component.

getId
^^^^^

.. java:method:: public String getId()
   :outertype: MenuComponent

   Gets the ID of this menu component.

   :return: the ID of this menu component.

getLink
^^^^^^^

.. java:method:: public String getLink()
   :outertype: MenuComponent

   Gets the link of this menu component.

   :return: the link of this menu component.

getName
^^^^^^^

.. java:method:: public String getName()
   :outertype: MenuComponent

   Gets the name of this menu component.

   :return: the name of this menu component.

getParent
^^^^^^^^^

.. java:method:: public MenuComponent getParent()
   :outertype: MenuComponent

   Gets the parent menu component.

   :return: the parent menu component.

getSeqNo
^^^^^^^^

.. java:method:: public int getSeqNo()
   :outertype: MenuComponent

   Gets the sequence number of this menu component.

   :return: the sequence number of this menu component.

isVisible
^^^^^^^^^

.. java:method:: public boolean isVisible()
   :outertype: MenuComponent

   Checks if this menu component is visible.

   :return: true if this menu component is visible.

setChildren
^^^^^^^^^^^

.. java:method:: public void setChildren(List children)
   :outertype: MenuComponent

   Sets the child menus.

   :param children: the child menus.

setDescription
^^^^^^^^^^^^^^

.. java:method:: public void setDescription(String description)
   :outertype: MenuComponent

   Sets the description of this menu component.

   :param description: the description of this menu component.

setId
^^^^^

.. java:method:: public void setId(String id)
   :outertype: MenuComponent

   Sets the ID of this menu component.

   :param id: the ID of this menu component.

setLink
^^^^^^^

.. java:method:: public void setLink(String link)
   :outertype: MenuComponent

   Sets the link of this menu component.

   :param link: the link of this menu component.

setName
^^^^^^^

.. java:method:: public void setName(String name)
   :outertype: MenuComponent

   Sets the name of this menu component.

   :param name: the name of this menu component.

setParent
^^^^^^^^^

.. java:method:: public void setParent(MenuComponent parent)
   :outertype: MenuComponent

   Sets the parent menu component.

   :param parent: the parent menu component.

setSeqNo
^^^^^^^^

.. java:method:: public void setSeqNo(int seqNo)
   :outertype: MenuComponent

   Sets the sequence number of this menu component.

   :param seqNo: the sequence number of this menu component.

setVisible
^^^^^^^^^^

.. java:method:: public void setVisible(boolean visible)
   :outertype: MenuComponent

   Sets the visibility of this menu component.

   :param visible: true if this menu component is visible.

