.. java:import:: hk.hku.cecid.piazza.commons.util Convertor

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io InputStream

.. java:import:: java.lang.reflect Method

.. java:import:: java.util Collections

.. java:import:: java.util Enumeration

.. java:import:: java.util HashSet

.. java:import:: java.util Hashtable

.. java:import:: java.util Set

AbstractDVO
===========

.. java:package:: hk.hku.cecid.piazza.commons.dao
   :noindex:

.. java:type:: public abstract class AbstractDVO implements DVO

   The AbstractDVO, which implements the DVO interface, is simply a convenient abstract class for managing the data of a DVO. It implemented the methods of the DVO interface, provides some convenient methods and is backed by a Hashtable.

   :author: Hugo Y. K. Lam

Constructors
------------
AbstractDVO
^^^^^^^^^^^

.. java:constructor:: protected AbstractDVO()
   :outertype: AbstractDVO

   Creates a new instance of AbstractDVO.

AbstractDVO
^^^^^^^^^^^

.. java:constructor:: protected AbstractDVO(Hashtable data)
   :outertype: AbstractDVO

   Creates a new instance of AbstractDVO.

   :param data: the source data of this DVO.

Methods
-------
equals
^^^^^^

.. java:method:: public boolean equals(Object obj)
   :outertype: AbstractDVO

   Indicates whether the given object is equal to this one. The objects are equal if and only if the given object is an AbstractDVO object and the values contained in that object match with this one's.

   :param obj: the object to be compared.
   :return: true if the given object is equal to this one.

   **See also:** :java:ref:`java.lang.Object.equals(java.lang.Object)`

get
^^^

.. java:method:: public Object get(Object key)
   :outertype: AbstractDVO

   Gets a value object back from this DVO by its key.

   :param key: the key referencing the value to be retrieved.
   :return: the value object retrieved by the specified key.

getBoolean
^^^^^^^^^^

.. java:method:: public boolean getBoolean(Object key)
   :outertype: AbstractDVO

   Retrieves the value by the specified key in this AbstractDVO as an boolean.

   :param key: the key referencing the value to be retrieved.
   :return: the value retrieved by the specified key.

getData
^^^^^^^

.. java:method:: public Hashtable getData()
   :outertype: AbstractDVO

   Gets the source data of this DVO.

   :return: the source data of this DVO.

getDate
^^^^^^^

.. java:method:: public java.util.Date getDate(Object key)
   :outertype: AbstractDVO

   Retrieves the value by the specified key in this AbstractDVO as a java.util.Date.

   :param key: the key referencing the value to be retrieved.
   :return: the value retrieved by the specified key.

getDirties
^^^^^^^^^^

.. java:method:: public String[] getDirties()
   :outertype: AbstractDVO

   Gets the keys which reference the dirty values.

   :return: the keys referencing the dirty values.

getDouble
^^^^^^^^^

.. java:method:: public double getDouble(Object key)
   :outertype: AbstractDVO

   Retrieves the value by the specified key in this AbstractDVO as a double.

   :param key: the key referencing the value to be retrieved.
   :return: the value retrieved by the specified key.

getInt
^^^^^^

.. java:method:: public int getInt(Object key)
   :outertype: AbstractDVO

   Retrieves the value by the specified key in this AbstractDVO as an int.

   :param key: the key referencing the value to be retrieved.
   :return: the value retrieved by the specified key or Integer.MIN_VALUE if the underlying value is null.

getLong
^^^^^^^

.. java:method:: public long getLong(Object key)
   :outertype: AbstractDVO

   Retrieves the value by the specified key in this AbstractDVO as a long.

   :param key: the key referencing the value to be retrieved.
   :return: the value retrieved by the specified key or Long.MIN_VALUE if the underlying value is null.

getObject
^^^^^^^^^

.. java:method:: public Object getObject(Object key, Class c)
   :outertype: AbstractDVO

   Gets an Object from this DVO by its referencing key. If the value object is not of the Class specified, it will try to create an instance of the Class with the Object as the parameter.

   :param key: The key referencing the String value.
   :param c: the Class of the returning Object.
   :return: the Object retrieved by its referencing key. If the value object is not of the Class specified, it will be an instance of the Class with the Object as the parameter. Null if the mentioned cannot be achieved.

getSQLDate
^^^^^^^^^^

.. java:method:: public java.sql.Date getSQLDate(Object key)
   :outertype: AbstractDVO

   Retrieves the value by the specified key in this AbstractDVO as a java.sql.Date.

   :param key: the key referencing the value to be retrieved.
   :return: the value retrieved by the specified key.

getString
^^^^^^^^^

.. java:method:: public String getString(Object key)
   :outertype: AbstractDVO

   Gets a String value from this DVO by its key reference.

   :param key: the key referencing the String value.
   :return: the String value retrieved by the specified key.

getTimestamp
^^^^^^^^^^^^

.. java:method:: public java.sql.Timestamp getTimestamp(Object key)
   :outertype: AbstractDVO

   Retrieves the value by the specified key in this AbstractDVO as a java.sql.Timestamp. It can transform java.sql.Date, java.util.Date and Oracle DATE and TIMESTAMP.

   :param key: the key referencing the value to be retrieved.
   :return: the value retrieved by the specified key.

put
^^^

.. java:method:: public Object put(Object key, Object value)
   :outertype: AbstractDVO

   Sets a single value to this DVO with a key as its reference.

   :param key: the key referencing the value to be set.
   :param value: the value object to be set to this DVO.
   :return: the previous value of the specified key in this hashtable, or null if it did not have one.

remove
^^^^^^

.. java:method:: public Object remove(Object key)
   :outertype: AbstractDVO

   Removes a value object from this DVO.

   :param key: the key referencing the value to be removed.
   :return: the value to which the key had been mapped in this DVO, or null if the key did not have a mapping.

setBoolean
^^^^^^^^^^

.. java:method:: public void setBoolean(Object key, boolean value)
   :outertype: AbstractDVO

   Sets a Boolean value to this DVO.

   :param key: the key referencing the Boolean value.
   :param value: the Boolean value to be set.

setData
^^^^^^^

.. java:method:: public void setData(Hashtable data)
   :outertype: AbstractDVO

   Sets the source data of this DVO.

   :param data: the source data of this DVO.

setDate
^^^^^^^

.. java:method:: public void setDate(Object key, Object obj)
   :outertype: AbstractDVO

   Sets a java.util.Date and java.sql.Date value to this DVO.

   :param key: the key referencing the Date value.
   :param obj: the Date value to be set.

setDouble
^^^^^^^^^

.. java:method:: public void setDouble(Object key, double value)
   :outertype: AbstractDVO

   Sets a Double value to this DVO.

   :param key: the key referencing the Double value.
   :param value: the Double value to be set.

setInt
^^^^^^

.. java:method:: public void setInt(Object key, int value)
   :outertype: AbstractDVO

   Sets an Integer value to this DVO.

   :param key: the key referencing the Integer value.
   :param value: the Integer value to be set.

setLong
^^^^^^^

.. java:method:: public void setLong(Object key, long value)
   :outertype: AbstractDVO

   Sets a Long value to this DVO.

   :param key: the key referencing the Long value.
   :param value: the Long value to be set.

setString
^^^^^^^^^

.. java:method:: public void setString(Object key, Object value)
   :outertype: AbstractDVO

   Sets a String value to this DVO.

   :param key: the key referencing the String value.
   :param value: the String value to be set.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: AbstractDVO

   Returns a string representation of this AbstractDVO object in the form of a set of entries.

   :return: a string representation of this AbstractDVO.

