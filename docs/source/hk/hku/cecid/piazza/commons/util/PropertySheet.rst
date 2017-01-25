.. java:import:: java.util Enumeration

.. java:import:: java.util Properties

PropertySheet
=============

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public interface PropertySheet

   PropertySheet is a common interface of a properties container.

   :author: Hugo Y. K. Lam

Methods
-------
append
^^^^^^

.. java:method:: public boolean append(PropertySheet p)
   :outertype: PropertySheet

   Appends a property sheet to this property sheet.

   :param p: the property sheet to be appended.
   :return: true if the operation is successful. false otherwise.

containsKey
^^^^^^^^^^^

.. java:method:: public boolean containsKey(String key)
   :outertype: PropertySheet

   Checks if the specified key exists in this property sheet.

   :param key: the property key.
   :return: true if the specified key exists in this property sheet.

createProperties
^^^^^^^^^^^^^^^^

.. java:method:: public Properties createProperties(String key)
   :outertype: PropertySheet

   Creates a Properties object which stores the properties retrieved by the specified key.

   :param key: the property key.
   :return: a Properties object which stores the retrieved properties.

getProperties
^^^^^^^^^^^^^

.. java:method:: public String[] getProperties(String key)
   :outertype: PropertySheet

   Gets a list of properties with the specified key.

   :param key: the property key.
   :return: the properties with the specified key.

getProperties
^^^^^^^^^^^^^

.. java:method:: public String[][] getProperties(String key, String key2)
   :outertype: PropertySheet

   Gets a two-dimensional list of properties with the specified keys. The first key will define the first dimension of the list and the second key will define the second dimension.

   :param key: the first property key.
   :param key2: the second property key.
   :return: a two-dimensional list of properties with the specified keys.

getProperty
^^^^^^^^^^^

.. java:method:: public String getProperty(String key)
   :outertype: PropertySheet

   Gets a property with the specified key.

   :param key: the property key.
   :return: the property with the specified key.

getProperty
^^^^^^^^^^^

.. java:method:: public String getProperty(String key, String def)
   :outertype: PropertySheet

   Gets a property with the specified key.

   :param key: the property key.
   :param def: the default value.
   :return: the property with the specified key.

load
^^^^

.. java:method:: public void load() throws Exception
   :outertype: PropertySheet

   Loads the properties from a persistent storage.

   :throws Exception: if the operation is unsuccessful.

propertyNames
^^^^^^^^^^^^^

.. java:method:: public Enumeration propertyNames()
   :outertype: PropertySheet

   Gets all the existing property names.

   :return: all the existing property names.

removeProperty
^^^^^^^^^^^^^^

.. java:method:: public boolean removeProperty(String key)
   :outertype: PropertySheet

   Removes a property with the specified key.

   :param key: the property key.
   :return: true if the operation is successful. false otherwise.

setProperty
^^^^^^^^^^^

.. java:method:: public boolean setProperty(String key, String value)
   :outertype: PropertySheet

   Sets a property value with the specified key.

   :param key: the property key.
   :param value: the property value.
   :return: true if the operation is successful. false otherwise.

store
^^^^^

.. java:method:: public void store() throws Exception
   :outertype: PropertySheet

   Stores the properties to a persistent storage.

   :throws Exception: if the operation is unsuccessful.

