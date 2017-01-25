NullableObject
==============

.. java:package:: hk.hku.cecid.piazza.commons.dao.ds
   :noindex:

.. java:type:: public class NullableObject

   NullableObject is a wrapper class for any object which has a corresponding SQL type. It indicates if the object wrapped is null and provide the type, java.sql.Types, information of the object.

Constructors
------------
NullableObject
^^^^^^^^^^^^^^

.. java:constructor:: public NullableObject(Object o, int type)
   :outertype: NullableObject

   Creates a new instance of NullableObject.

   :param o: The object to be wrapped by this NullableObject.
   :param type: The type of the object to be wrapped.

Methods
-------
getObject
^^^^^^^^^

.. java:method:: public Object getObject()
   :outertype: NullableObject

   Retrieves the object wrapped by this NullableObject.

   :return: the object wrapped.

getType
^^^^^^^

.. java:method:: public int getType()
   :outertype: NullableObject

   Retrieves the type information of the object wrapped.

   :return: the type information of the object wrapped. -1 if not specified in the creation of this instance.

isNull
^^^^^^

.. java:method:: public boolean isNull()
   :outertype: NullableObject

   Reports whether the wrapped object is null.

   :return: \ ``true``\  if the object wrapped is null and
           false if it is not.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: NullableObject

   Returns a string representation of the object wrapped.

   :return: a string representation of the object wrapped. 'null' if the object wrapped is null.

