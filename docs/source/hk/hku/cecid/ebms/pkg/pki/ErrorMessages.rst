.. java:import:: java.util Iterator

.. java:import:: java.util TreeMap

ErrorMessages
=============

.. java:package:: hk.hku.cecid.ebms.pkg.pki
   :noindex:

.. java:type:: public class ErrorMessages

   A class holding error codes and the corresponding error messages.

   :author: kcyee

Fields
------
ERR_PKI_CANNOT_DECRYPT
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final int ERR_PKI_CANNOT_DECRYPT
   :outertype: ErrorMessages

ERR_PKI_CANNOT_ENCRYPT
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final int ERR_PKI_CANNOT_ENCRYPT
   :outertype: ErrorMessages

ERR_PKI_CANNOT_SIGN
^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final int ERR_PKI_CANNOT_SIGN
   :outertype: ErrorMessages

ERR_PKI_INVALID_KEYSTORE
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final int ERR_PKI_INVALID_KEYSTORE
   :outertype: ErrorMessages

ERR_PKI_UNKNOWN_ERROR
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final int ERR_PKI_UNKNOWN_ERROR
   :outertype: ErrorMessages

ERR_PKI_VERIFY_SIGNATURE_FAILED
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final int ERR_PKI_VERIFY_SIGNATURE_FAILED
   :outertype: ErrorMessages

errorMsg
^^^^^^^^

.. java:field:: protected static TreeMap errorMsg
   :outertype: ErrorMessages

isConfigured
^^^^^^^^^^^^

.. java:field:: protected static boolean isConfigured
   :outertype: ErrorMessages

Methods
-------
configure
^^^^^^^^^

.. java:method:: protected static synchronized void configure()
   :outertype: ErrorMessages

getMessage
^^^^^^^^^^

.. java:method:: public static String getMessage(int code)
   :outertype: ErrorMessages

getMessage
^^^^^^^^^^

.. java:method:: public static String getMessage(int code, String extraMsg)
   :outertype: ErrorMessages

getMessage
^^^^^^^^^^

.. java:method:: public static String getMessage(int code, Throwable e)
   :outertype: ErrorMessages

getMessage
^^^^^^^^^^

.. java:method:: public static String getMessage(int code, Throwable e, String extraMsg)
   :outertype: ErrorMessages

load
^^^^

.. java:method:: protected static void load(int code, String msg)
   :outertype: ErrorMessages

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: ErrorMessages

