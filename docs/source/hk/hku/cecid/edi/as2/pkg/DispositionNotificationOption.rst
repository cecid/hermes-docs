.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: java.util Vector

DispositionNotificationOption
=============================

.. java:package:: hk.hku.cecid.edi.as2.pkg
   :noindex:

.. java:type:: public class DispositionNotificationOption

   DispositionNotificationOption represents an AS2 disposition notification option.

   :author: Hugo Y. K. Lam

Fields
------
IMPORTANCE_OPTIONAL
^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String IMPORTANCE_OPTIONAL
   :outertype: DispositionNotificationOption

IMPORTANCE_REQURIED
^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String IMPORTANCE_REQURIED
   :outertype: DispositionNotificationOption

SIGNED_RECEIPT_MICALG_MD5
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SIGNED_RECEIPT_MICALG_MD5
   :outertype: DispositionNotificationOption

SIGNED_RECEIPT_MICALG_SHA1
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SIGNED_RECEIPT_MICALG_SHA1
   :outertype: DispositionNotificationOption

SIGNED_RECEIPT_PROTOCOL_PKCS7
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SIGNED_RECEIPT_PROTOCOL_PKCS7
   :outertype: DispositionNotificationOption

Constructors
------------
DispositionNotificationOption
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public DispositionNotificationOption()
   :outertype: DispositionNotificationOption

DispositionNotificationOption
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public DispositionNotificationOption(String option)
   :outertype: DispositionNotificationOption

DispositionNotificationOption
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public DispositionNotificationOption(String name, String importance, String[] values)
   :outertype: DispositionNotificationOption

Methods
-------
addValue
^^^^^^^^

.. java:method:: public void addValue(String value)
   :outertype: DispositionNotificationOption

containsValue
^^^^^^^^^^^^^

.. java:method:: public boolean containsValue(String value)
   :outertype: DispositionNotificationOption

countValues
^^^^^^^^^^^

.. java:method:: public int countValues()
   :outertype: DispositionNotificationOption

getImportance
^^^^^^^^^^^^^

.. java:method:: public String getImportance()
   :outertype: DispositionNotificationOption

getName
^^^^^^^

.. java:method:: public String getName()
   :outertype: DispositionNotificationOption

getValue
^^^^^^^^

.. java:method:: public String getValue()
   :outertype: DispositionNotificationOption

getValue
^^^^^^^^

.. java:method:: public String getValue(int pos)
   :outertype: DispositionNotificationOption

getValues
^^^^^^^^^

.. java:method:: public Iterator getValues()
   :outertype: DispositionNotificationOption

isRequired
^^^^^^^^^^

.. java:method:: public boolean isRequired()
   :outertype: DispositionNotificationOption

removeValue
^^^^^^^^^^^

.. java:method:: public void removeValue(int pos)
   :outertype: DispositionNotificationOption

removeValues
^^^^^^^^^^^^

.. java:method:: public void removeValues()
   :outertype: DispositionNotificationOption

setImportance
^^^^^^^^^^^^^

.. java:method:: public void setImportance(String importance)
   :outertype: DispositionNotificationOption

setName
^^^^^^^

.. java:method:: public void setName(String name)
   :outertype: DispositionNotificationOption

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: DispositionNotificationOption

