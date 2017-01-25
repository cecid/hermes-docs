.. java:import:: java.util Hashtable

.. java:import:: java.util Iterator

.. java:import:: java.util Map

DispositionNotificationOptions
==============================

.. java:package:: hk.hku.cecid.edi.as2.pkg
   :noindex:

.. java:type:: public class DispositionNotificationOptions

   DispositionNotificationOption represents the AS2 disposition notification options.

   :author: Hugo Y. K. Lam

Fields
------
SIGNED_RECEIPT_MICALG
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SIGNED_RECEIPT_MICALG
   :outertype: DispositionNotificationOptions

SIGNED_RECEIPT_PROTOCOL
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SIGNED_RECEIPT_PROTOCOL
   :outertype: DispositionNotificationOptions

Constructors
------------
DispositionNotificationOptions
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public DispositionNotificationOptions()
   :outertype: DispositionNotificationOptions

DispositionNotificationOptions
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public DispositionNotificationOptions(String options)
   :outertype: DispositionNotificationOptions

Methods
-------
addOption
^^^^^^^^^

.. java:method:: public void addOption(DispositionNotificationOption option)
   :outertype: DispositionNotificationOptions

addOption
^^^^^^^^^

.. java:method:: public DispositionNotificationOption addOption(String name)
   :outertype: DispositionNotificationOptions

getOption
^^^^^^^^^

.. java:method:: public DispositionNotificationOption getOption(String name)
   :outertype: DispositionNotificationOptions

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: DispositionNotificationOptions

