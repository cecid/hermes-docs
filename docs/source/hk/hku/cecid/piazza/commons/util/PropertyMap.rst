.. java:import:: hk.hku.cecid.piazza.commons.module ComponentException

.. java:import:: hk.hku.cecid.piazza.commons.module PersistentComponent

.. java:import:: java.io FileOutputStream

.. java:import:: java.io InputStream

.. java:import:: java.net URL

.. java:import:: java.util ArrayList

.. java:import:: java.util Arrays

.. java:import:: java.util Enumeration

.. java:import:: java.util Properties

PropertyMap
===========

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public class PropertyMap extends PersistentComponent implements PropertySheet

   PropertyMap is an implementation of a PropertySheet. It represents a property sheet with a map structure and is actually backed by a Properties object.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`java.util.Properties`

Constructors
------------
PropertyMap
^^^^^^^^^^^

.. java:constructor:: public PropertyMap()
   :outertype: PropertyMap

   Creates a new instance of PropertyMap.

PropertyMap
^^^^^^^^^^^

.. java:constructor:: public PropertyMap(Properties p)
   :outertype: PropertyMap

   Creates a new instance of PropertyMap.

   :param p: the Properties object which backs this map.

PropertyMap
^^^^^^^^^^^

.. java:constructor:: public PropertyMap(URL url) throws ComponentException
   :outertype: PropertyMap

   Creates a new instance of PropertyMap.

   :param url: the url of the properties source.
   :throws ComponentException: if the properties could not be loaded from the specified url.

Methods
-------
append
^^^^^^

.. java:method:: public boolean append(PropertySheet p)
   :outertype: PropertyMap

   Appends a property sheet to this property map. The specified property sheet can only be appended if it is of the PropertyMap type.

   :param p: the property sheet to be appended.
   :return: true if the operation is successful. false otherwise.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.append(hk.hku.cecid.piazza.commons.util.PropertySheet)`

containsKey
^^^^^^^^^^^

.. java:method:: public boolean containsKey(String key)
   :outertype: PropertyMap

   Checks if the specified key exists in this property map.

   :param key: the property key.
   :return: true if the specified key exists in this property map.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.containsKey(java.lang.String)`

createProperties
^^^^^^^^^^^^^^^^

.. java:method:: public Properties createProperties(String keyPrefix)
   :outertype: PropertyMap

   Creates a Properties object which stores the properties retrieved by the specified key prefix.

   :param keyPrefix: the property key prefix.
   :return: a Properties object which stores the retrieved properties.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.createProperties(java.lang.String)`

getProperties
^^^^^^^^^^^^^

.. java:method:: public String[] getProperties(String keyPrefix)
   :outertype: PropertyMap

   Gets a list of properties with the specified key.

   :param keyPrefix: the property key prefix.
   :return: the properties with the specified key.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.getProperties(java.lang.String)`

getProperties
^^^^^^^^^^^^^

.. java:method:: public String[][] getProperties(String keyPrefix, String keySuffixes)
   :outertype: PropertyMap

   Gets a two-dimensional list of properties with the specified key prefix and key suffixes. The key prefix, along with the suffixes, will define the first dimension of the list while the key suffixes will define the second dimension. E.g.

   .. parsed-literal::

      # Properties content
      application.listener1.id=MyListener
      application.listener1.name=My Listener
      application.listener2.id=MyListener2
      application.listener2.name=My Listener 2

      Key Prefix: application.listener
      Key Suffixes: id,name

      Note that the resulted array will be sorted alphabetically according to the original
      keys but not the specified key suffixes order or the property values.

      Returned array:
      {{"MyListener","My Listener"},{"MyListener2","My Listener 2"}}

   :param keyPrefix: the property key prefix.
   :param keySuffixes: the property key suffixes delimited by either ',', ';' or '|'.
   :return: a two-dimensional list of properties with the specified keys.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.getProperties(java.lang.String,
   java.lang.String)`

getProperty
^^^^^^^^^^^

.. java:method:: public String getProperty(String key)
   :outertype: PropertyMap

   Gets a property with the specified key.

   :param key: the property key.
   :return: the property with the specified key.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.getProperty(java.lang.String)`

getProperty
^^^^^^^^^^^

.. java:method:: public String getProperty(String key, String def)
   :outertype: PropertyMap

   Gets a property with the specified key.

   :param key: the property key.
   :param def: the default value.
   :return: the property with the specified key.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.getProperty(java.lang.String,
   java.lang.String)`

getPropertyNames
^^^^^^^^^^^^^^^^

.. java:method:: protected String[] getPropertyNames(String keyPrefix)
   :outertype: PropertyMap

   Gets all property names with the specified key prefix.

   :param keyPrefix: the property key prefix.
   :return: the property names with the specified key prefix.

loading
^^^^^^^

.. java:method:: protected void loading(URL url) throws Exception
   :outertype: PropertyMap

   Loads the properties from the specified url location.

   :param url: the url of the properties source.
   :throws Exception: if the operation is unsuccessful.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.PersistentComponent.loading(java.net.URL)`

propertyNames
^^^^^^^^^^^^^

.. java:method:: public Enumeration propertyNames()
   :outertype: PropertyMap

   Gets all the existing property names.

   :return: all the existing property names.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.propertyNames()`

removeProperty
^^^^^^^^^^^^^^

.. java:method:: public boolean removeProperty(String key)
   :outertype: PropertyMap

   Removes a property with the specified key.

   :param key: the property key.
   :return: true if the operation is successful. false otherwise.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.removeProperty(java.lang.String)`

setProperty
^^^^^^^^^^^

.. java:method:: public boolean setProperty(String key, String value)
   :outertype: PropertyMap

   Sets a property value with the specified key.

   :param key: the property key.
   :param value: the property value.
   :return: true if the operation is successful. false otherwise.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertySheet.setProperty(java.lang.String,
   java.lang.String)`

storing
^^^^^^^

.. java:method:: protected void storing(URL url) throws Exception
   :outertype: PropertyMap

   Stores the properties to the specified url location.

   :param url: the url of the properties source.
   :throws Exception: if the operation is unsuccessful.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.PersistentComponent.storing(java.net.URL)`

