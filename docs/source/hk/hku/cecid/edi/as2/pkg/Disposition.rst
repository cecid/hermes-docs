.. java:import:: java.util StringTokenizer

Disposition
===========

.. java:package:: hk.hku.cecid.edi.as2.pkg
   :noindex:

.. java:type:: public class Disposition

   Disposition represents an AS2 disposition.

   :author: Hugo Y. K. Lam

Fields
------
ACTION_MODE_AUTOMATIC
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ACTION_MODE_AUTOMATIC
   :outertype: Disposition

ACTION_MODE_MANUAL
^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ACTION_MODE_MANUAL
   :outertype: Disposition

DESC_AUTHENTICATION_FAILED
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String DESC_AUTHENTICATION_FAILED
   :outertype: Disposition

DESC_DECOMPRESSION_FAILED
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String DESC_DECOMPRESSION_FAILED
   :outertype: Disposition

DESC_DECRYPTION_FAILED
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String DESC_DECRYPTION_FAILED
   :outertype: Disposition

DESC_INSUFFICIENT_MESSAGE_SECURITY
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String DESC_INSUFFICIENT_MESSAGE_SECURITY
   :outertype: Disposition

DESC_INTEGRITY_CHECK_FAILED
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String DESC_INTEGRITY_CHECK_FAILED
   :outertype: Disposition

DESC_UNEXPECTED_PROCESSING_ERROR
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String DESC_UNEXPECTED_PROCESSING_ERROR
   :outertype: Disposition

DESC_UNSUPPORTED_FORMAT
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String DESC_UNSUPPORTED_FORMAT
   :outertype: Disposition

DESC_UNSUPPORTED_MIC_ALGORITHM
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String DESC_UNSUPPORTED_MIC_ALGORITHM
   :outertype: Disposition

MODIFIER_ERROR
^^^^^^^^^^^^^^

.. java:field:: public static final String MODIFIER_ERROR
   :outertype: Disposition

MODIFIER_FAILURE
^^^^^^^^^^^^^^^^

.. java:field:: public static final String MODIFIER_FAILURE
   :outertype: Disposition

MODIFIER_WARNING
^^^^^^^^^^^^^^^^

.. java:field:: public static final String MODIFIER_WARNING
   :outertype: Disposition

SENDING_MODE_AUTOMATIC
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SENDING_MODE_AUTOMATIC
   :outertype: Disposition

SENDING_MODE_MANUAL
^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SENDING_MODE_MANUAL
   :outertype: Disposition

TYPE_FAILED
^^^^^^^^^^^

.. java:field:: public static final String TYPE_FAILED
   :outertype: Disposition

TYPE_PROCESSED
^^^^^^^^^^^^^^

.. java:field:: public static final String TYPE_PROCESSED
   :outertype: Disposition

Constructors
------------
Disposition
^^^^^^^^^^^

.. java:constructor:: public Disposition()
   :outertype: Disposition

Disposition
^^^^^^^^^^^

.. java:constructor:: public Disposition(String actionMode, String sendingMode, String type)
   :outertype: Disposition

Disposition
^^^^^^^^^^^

.. java:constructor:: public Disposition(String actionMode, String sendingMode, String type, String modifier, String statusDescription)
   :outertype: Disposition

Disposition
^^^^^^^^^^^

.. java:constructor:: public Disposition(String disposition) throws AS2MessageException
   :outertype: Disposition

Methods
-------
getActionMode
^^^^^^^^^^^^^

.. java:method:: public String getActionMode()
   :outertype: Disposition

getDescription
^^^^^^^^^^^^^^

.. java:method:: public String getDescription()
   :outertype: Disposition

getDispositionMode
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getDispositionMode()
   :outertype: Disposition

getModifier
^^^^^^^^^^^

.. java:method:: public String getModifier()
   :outertype: Disposition

getSendingMode
^^^^^^^^^^^^^^

.. java:method:: public String getSendingMode()
   :outertype: Disposition

getType
^^^^^^^

.. java:method:: public String getType()
   :outertype: Disposition

isError
^^^^^^^

.. java:method:: public boolean isError()
   :outertype: Disposition

isWarning
^^^^^^^^^

.. java:method:: public boolean isWarning()
   :outertype: Disposition

setActionMode
^^^^^^^^^^^^^

.. java:method:: public void setActionMode(String action)
   :outertype: Disposition

setDescription
^^^^^^^^^^^^^^

.. java:method:: public void setDescription(String statusDescription)
   :outertype: Disposition

setModifier
^^^^^^^^^^^

.. java:method:: public void setModifier(String statusModifier)
   :outertype: Disposition

setSendingMode
^^^^^^^^^^^^^^

.. java:method:: public void setSendingMode(String mdnAction)
   :outertype: Disposition

setType
^^^^^^^

.. java:method:: public void setType(String status)
   :outertype: Disposition

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: Disposition

validate
^^^^^^^^

.. java:method:: public void validate() throws DispositionException
   :outertype: Disposition

