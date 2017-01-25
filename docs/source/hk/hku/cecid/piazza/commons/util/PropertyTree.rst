.. java:import:: hk.hku.cecid.piazza.commons.module ComponentException

.. java:import:: hk.hku.cecid.piazza.commons.module PersistentComponent

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io FileOutputStream

.. java:import:: java.io InputStream

.. java:import:: java.net URL

.. java:import:: java.util Collections

.. java:import:: java.util Enumeration

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: java.util Properties

.. java:import:: java.util StringTokenizer

.. java:import:: java.util Vector

.. java:import:: javax.xml.parsers DocumentBuilder

.. java:import:: javax.xml.parsers DocumentBuilderFactory

.. java:import:: javax.xml.transform Source

.. java:import:: javax.xml.transform Transformer

.. java:import:: javax.xml.transform TransformerFactory

.. java:import:: javax.xml.transform.dom DOMSource

.. java:import:: javax.xml.transform.stream StreamResult

.. java:import:: org.dom4j Document

.. java:import:: org.dom4j DocumentHelper

.. java:import:: org.dom4j Element

.. java:import:: org.dom4j Node

.. java:import:: org.dom4j.io DocumentSource

.. java:import:: org.dom4j.io OutputFormat

.. java:import:: org.dom4j.io SAXReader

.. java:import:: org.dom4j.io XMLWriter

PropertyTree
============

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public class PropertyTree extends PersistentComponent implements PropertySheet

   PropertyTree is an implementation of a PropertySheet. It represents a property sheet with a tree structure and is actually backed by a Document object.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`org.dom4j.Document`

Constructors
------------
PropertyTree
^^^^^^^^^^^^

.. java:constructor:: public PropertyTree()
   :outertype: PropertyTree

   Creates a new instance of PropertyTree.

PropertyTree
^^^^^^^^^^^^

.. java:constructor:: public PropertyTree(URL url) throws ComponentException
   :outertype: PropertyTree

   Creates a new instance of PropertyTree.

   :param url: the url of the properties source.
   :throws ComponentException: if the properties could not be loaded from the specified url.

PropertyTree
^^^^^^^^^^^^

.. java:constructor:: public PropertyTree(org.w3c.dom.Node node) throws ComponentException
   :outertype: PropertyTree

   Creates a new instance of PropertyTree.

   :param node: the root node of the properties source.
   :throws ComponentException: if the properties could not be constructed from the specified node.

PropertyTree
^^^^^^^^^^^^

.. java:constructor:: public PropertyTree(InputStream ins) throws ComponentException
   :outertype: PropertyTree

   Creates a new instance of PropertyTree.

   :param ins: the input stream of the properties source.
   :throws ComponentException: if the properties could not be loaded from the specified input stream.

Methods
-------
addProperty
^^^^^^^^^^^

.. java:method:: protected boolean addProperty(String xpath, String value)
   :outertype: PropertyTree

   Adds a property to this property tree.

   :param xpath: the property xpath.
   :param value: the property value.
   :return: true if the operation is successful. false otherwise.

append
^^^^^^

.. java:method:: public boolean append(PropertySheet p)
   :outertype: PropertyTree

   Appends a property sheet to this property tree. The specified property sheet can only be appended if it is of the PropertyTree type.

   :param p: the property sheet to be appended.
   :return: true if the operation is successful. false otherwise.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.append(hk.hku.cecid.piazza.commons.util.PropertySheet)`

containsKey
^^^^^^^^^^^

.. java:method:: public boolean containsKey(String xpath)
   :outertype: PropertyTree

   Checks if the specified xpath exists in this property tree.

   :param xpath: the property xpath.
   :return: true if the specified xpath exists in this property tree.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.containsKey(java.lang.String)`

countProperties
^^^^^^^^^^^^^^^

.. java:method:: public int countProperties(String xpath)
   :outertype: PropertyTree

   Counts the number of properties with the specified xpath.

   :param xpath: the properties xpath.
   :return: the number of properties with the specified xpath.

createProperties
^^^^^^^^^^^^^^^^

.. java:method:: public Properties createProperties(String xpath)
   :outertype: PropertyTree

   Creates a Properties object which stores the properties retrieved by the specified xpath.

   :param xpath: the properties xpath.
   :return: a Properties object which stores the retrieved properties.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.createProperties(java.lang.String)`

getProperties
^^^^^^^^^^^^^

.. java:method:: public String[] getProperties(String xpath)
   :outertype: PropertyTree

   Gets a list of properties with the specified xpath.

   :param xpath: the properties xpath.
   :return: the properties with the specified xpath.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.getProperties(java.lang.String)`

getProperties
^^^^^^^^^^^^^

.. java:method:: public String[][] getProperties(String xpath, String xpath2)
   :outertype: PropertyTree

   Gets a two-dimensional list of properties with the specified xpaths. The first xpath will define the first dimension of the list while the second xpath will define the second dimension. E.g.

   .. parsed-literal::

      <!- Properties content -->
      <application>
        <listener>
          <id>MyListener</id>
          <name>My Listener</name>
        </listener>
        <listener>
          <id>MyListener2</id>
          <name>My Listener 2</name>
        </listener>
      </application>

      First xpath: /application/listener
      Second xpath: ./id|./name

      Returned array:
      {{"MyListener","My Listener"},{"MyListener2","My Listener 2"}}

   :param xpath: the first xpath.
   :param xpath2: the second xpath.
   :return: a two-dimensional list of properties with the specified xpaths.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.getProperties(java.lang.String,
   java.lang.String)`

getProperty
^^^^^^^^^^^

.. java:method:: public String getProperty(String xpath)
   :outertype: PropertyTree

   Gets a property with the specified xpath. If the xpath refers to more than one properpty, the first one will be returned.

   :param xpath: the property xpath.
   :return: the property with the specified xpath.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.getProperty(java.lang.String)`

getProperty
^^^^^^^^^^^

.. java:method:: public String getProperty(String xpath, String def)
   :outertype: PropertyTree

   Gets a property with the specified xpath. If the xpath refers to more than one properpty, the first one will be returned.

   :param xpath: the property xpath.
   :param def: the default value.
   :return: the property with the specified xpath.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.getProperty(java.lang.String,
   java.lang.String)`

getPropertyNode
^^^^^^^^^^^^^^^

.. java:method:: protected Node getPropertyNode(String xpath)
   :outertype: PropertyTree

   Gets a property node with the specified xpath. If the xpath refers to more than one properpty node, the first one will be returned.

   :param xpath: the property xpath.
   :return: the property node with the specified xpath.

getPropertyNodes
^^^^^^^^^^^^^^^^

.. java:method:: protected List getPropertyNodes(String xpath)
   :outertype: PropertyTree

   Gets a list of property nodes with the specified xpath.

   :param xpath: the properties xpath.
   :return: the property nodes with the specified xpath.

getSource
^^^^^^^^^

.. java:method:: public Source getSource()
   :outertype: PropertyTree

   Gets the docment source.

   :return: the document source.

loading
^^^^^^^

.. java:method:: protected void loading(URL url) throws Exception
   :outertype: PropertyTree

   Loads the properties from the specified url location.

   :param url: the url of the properties source.
   :throws Exception: if the operation is unsuccessful.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.PersistentComponent.loading(java.net.URL)`

propertyNames
^^^^^^^^^^^^^

.. java:method:: public Enumeration propertyNames()
   :outertype: PropertyTree

   Gets all the existing property xpaths.

   :return: all the existing property xpaths.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.propertyNames()`

removeProperty
^^^^^^^^^^^^^^

.. java:method:: public boolean removeProperty(String xpath)
   :outertype: PropertyTree

   Removes a property with the specified xpath. If the xpath refers to more than one properpty, the first one will be removed.

   :param xpath: the property xpath.
   :return: true if the operation is successful. false otherwise.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.removeProperty(java.lang.String)`

setProperty
^^^^^^^^^^^

.. java:method:: public boolean setProperty(String xpath, String value)
   :outertype: PropertyTree

   Sets a property value with the specified key.

   :param xpath: the property xpath.
   :param value: the property value.
   :return: true if the operation is successful. false otherwise.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.setProperty(java.lang.String,
   java.lang.String)`

storing
^^^^^^^

.. java:method:: protected void storing(URL url) throws Exception
   :outertype: PropertyTree

   Stores the properties to the specified url location.

   :param url: the url of the properties source.
   :throws Exception: if the operation is unsuccessful.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.PersistentComponent.storing(java.net.URL)`

subtree
^^^^^^^

.. java:method:: public PropertyTree subtree(String xpath)
   :outertype: PropertyTree

   Creates a sub-tree from this property tree.

   :param xpath: the xpath for locating the subtree.
   :return: a new property tree.

toDocument
^^^^^^^^^^

.. java:method:: public org.w3c.dom.Document toDocument()
   :outertype: PropertyTree

   Returns a W3C document representation of this property tree.

   :return: a new W3C document.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: PropertyTree

   Returns a string representation of this property tree, which is the XML text.

   :return: a string representation of this property tree.

   **See also:** :java:ref:`java.lang.Object.toString()`

