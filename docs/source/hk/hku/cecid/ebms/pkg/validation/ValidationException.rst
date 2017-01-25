.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPMessage

ValidationException
===================

.. java:package:: hk.hku.cecid.ebms.pkg.validation
   :noindex:

.. java:type:: public abstract class ValidationException extends SOAPException

   Base class for message validation exceptions. All classes extending this class must be able to generate a SOAP message to indicate the error, but it is not necessary a SOAP Fault message (e.g. an ebXML message containing ErrorList element).

   :author: Frankie Lam

Fields
------
ERROR_EBXML
^^^^^^^^^^^

.. java:field:: public static final int ERROR_EBXML
   :outertype: ValidationException

   The error represented by this exception is caused by an incorrectly packaged ebXML message.

ERROR_SOAP
^^^^^^^^^^

.. java:field:: public static final int ERROR_SOAP
   :outertype: ValidationException

   The error represented by this exception is a SOAP Fault

ERROR_UNKNOWN
^^^^^^^^^^^^^

.. java:field:: public static final int ERROR_UNKNOWN
   :outertype: ValidationException

   The error represented by this exception is unknown.

errorCode
^^^^^^^^^

.. java:field:: protected final String errorCode
   :outertype: ValidationException

   Error code.

errorString
^^^^^^^^^^^

.. java:field:: protected final String errorString
   :outertype: ValidationException

   A string describing the error occurred.

errorType
^^^^^^^^^

.. java:field:: protected final int errorType
   :outertype: ValidationException

   The type of error represented by this exception object.

Constructors
------------
ValidationException
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public ValidationException(int errorType, String errorCode, String errorString)
   :outertype: ValidationException

   Constructs a \ ``ValidationException``\  object.

   :param errorType: The type of error represented by this exception object.
   :param errorCode: An error code in string to be processed by the applications.
   :param errorString: A human-readable description string.

Methods
-------
getSOAPMessage
^^^^^^^^^^^^^^

.. java:method:: public abstract SOAPMessage getSOAPMessage()
   :outertype: ValidationException

   Get the SOAP message containing the error information.

   :return: \ ``SOAPMessage``\  object containing the error information.

