.. java:import:: java.util Map

.. java:import:: java.util HashMap

KVPairData
==========

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class KVPairData implements Data

   The \ ``KVPairData``\  is a simple data structures for storing key-valued style data. It is implemented based on \ :java:ref:`java.util.Map`\ . You can define the max capacity through the constructor so that the internal data does not need to rehash when there is not enough room. Creation Date: 21/3/2007

   :author: Twinsen Tsang

Fields
------
props
^^^^^

.. java:field:: protected Map props
   :outertype: KVPairData

   The KVPair interval data.

Constructors
------------
KVPairData
^^^^^^^^^^

.. java:constructor:: public KVPairData(int maxCapacity)
   :outertype: KVPairData

   Explicit Constructor.

   :param maxCapacity: The maximum Key value pair that the data can hold.

Methods
-------
getProperties
^^^^^^^^^^^^^

.. java:method:: public Map getProperties()
   :outertype: KVPairData

   :return: the properties set for this MessageStatusRequestData.

setProperties
^^^^^^^^^^^^^

.. java:method:: public void setProperties(Map hm)
   :outertype: KVPairData

   Set the message status request properties and overwrite the existing one. This operation success only when the size of \ ``hm``\  is smaller than it's maxCapacity defined in the constructor.

   :param hm: The new properties set.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: KVPairData

   toString method. Simple Key-Iteration

