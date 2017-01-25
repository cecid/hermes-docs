.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.pkg ErrorList

.. java:import:: hk.hku.cecid.ebms.pkg MessageHeader

.. java:import:: hk.hku.cecid.ebms.pkg Utility

.. java:import:: java.util Date

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPMessage

EbxmlValidationException
========================

.. java:package:: hk.hku.cecid.ebms.pkg.validation
   :noindex:

.. java:type:: public class EbxmlValidationException extends ValidationException

   Exception class that can generate ebXML error messages from the information it has been given.

   :author: Frankie Lam

Fields
------
ACTION
^^^^^^

.. java:field:: public static final String ACTION
   :outertype: EbxmlValidationException

   Error action reserved for standalone errors described in ebXML Message Service Specification [ebMSS 4.2.4.3].

EBXML_ERROR_DELIVERY_FAILURE
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBXML_ERROR_DELIVERY_FAILURE
   :outertype: EbxmlValidationException

   ebXML message cannot be delivered.

EBXML_ERROR_INCONSISTENT
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBXML_ERROR_INCONSISTENT
   :outertype: EbxmlValidationException

   ebXML error indicating that the ebXML message is inconsistent.

EBXML_ERROR_MIME_PROBLEM
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBXML_ERROR_MIME_PROBLEM
   :outertype: EbxmlValidationException

   xlink:href error cannot be resolved.

EBXML_ERROR_NOT_SUPPORTED
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBXML_ERROR_NOT_SUPPORTED
   :outertype: EbxmlValidationException

   ebXML error indicating that the function is not supported.

EBXML_ERROR_OTHER_XML
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBXML_ERROR_OTHER_XML
   :outertype: EbxmlValidationException

   ebXML error indicating that the ebXML message do not conform to the rules or constraints specified in the specification, and cannot be represented using other error codes.

EBXML_ERROR_SECURITY_FAILURE
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBXML_ERROR_SECURITY_FAILURE
   :outertype: EbxmlValidationException

   Validation of signatures or authenticity / authority has failed.

EBXML_ERROR_TIME_TO_LIVE_EXPIRED
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBXML_ERROR_TIME_TO_LIVE_EXPIRED
   :outertype: EbxmlValidationException

   ebXML message is expired.

EBXML_ERROR_UNKNOWN
^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBXML_ERROR_UNKNOWN
   :outertype: EbxmlValidationException

   An error has occurred but cannot be represented by other error codes.

EBXML_ERROR_VALUE_NOT_RECOGNIZED
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBXML_ERROR_VALUE_NOT_RECOGNIZED
   :outertype: EbxmlValidationException

   ebXML error indicating that the value of an element / attribute cannot be recognized.

SERVICE
^^^^^^^

.. java:field:: public static final String SERVICE
   :outertype: EbxmlValidationException

   Service name reserved for services described in ebXML Message Service Specification [ebMSS 3.1.4].

SEVERITY_ERROR
^^^^^^^^^^^^^^

.. java:field:: public static final String SEVERITY_ERROR
   :outertype: EbxmlValidationException

   Error severity level

SEVERITY_WARNING
^^^^^^^^^^^^^^^^

.. java:field:: public static final String SEVERITY_WARNING
   :outertype: EbxmlValidationException

   Warning severity level

location
^^^^^^^^

.. java:field:: protected final String location
   :outertype: EbxmlValidationException

   location of the message containing the error.

refToMessage
^^^^^^^^^^^^

.. java:field:: protected EbxmlMessage refToMessage
   :outertype: EbxmlValidationException

   The ebXML message being referred to.

severity
^^^^^^^^

.. java:field:: protected final String severity
   :outertype: EbxmlValidationException

   Severity of the error.

Constructors
------------
EbxmlValidationException
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EbxmlValidationException(String errorCode, String severity, String errorString)
   :outertype: EbxmlValidationException

   Constructs a \ ``EbxmlValidationException``\  object given its error code, severity level, error string and the ebXML message being referred.

   :param errorCode: One of the error codes defined in ebMS 4.2.3.4.1.
   :param severity: Severity level of the error, which should be either SEVERITY_WARNING or SEVERITY_ERROR
   :param errorString: String describing the error.

EbxmlValidationException
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EbxmlValidationException(String errorCode, String severity, String errorString, String location)
   :outertype: EbxmlValidationException

   Constructs a \ ``EbxmlValidationException``\  object given its error code, severity level, error string and the ebXML message being referred.

   :param errorCode: One of the error codes defined in ebMS 4.2.3.4.1.
   :param severity: Severity level of the error, which should be either SEVERITY_WARNING or SEVERITY_ERROR
   :param errorString: String describing the error.
   :param location: Location of the message containing the error.

Methods
-------
getEbxmlMessage
^^^^^^^^^^^^^^^

.. java:method:: public EbxmlMessage getEbxmlMessage()
   :outertype: EbxmlValidationException

   Get \ ``EbxmlMessage``\  error message from the information given int this object.

   :return: \ ``EbxmlMessage``\  containing the error information.

getLocation
^^^^^^^^^^^

.. java:method:: public String getLocation()
   :outertype: EbxmlValidationException

   Get the location attribute of the ebXML error element.

   :return: Value of location attribute; null if it is unspecified.

getSOAPMessage
^^^^^^^^^^^^^^

.. java:method:: public SOAPMessage getSOAPMessage()
   :outertype: EbxmlValidationException

   Get the error message in SOAP format.

   :return: \ ``javax.xml.soap.SOAPMessage``\  object.

setRefToMessage
^^^^^^^^^^^^^^^

.. java:method:: public void setRefToMessage(EbxmlMessage refToMessage)
   :outertype: EbxmlValidationException

   Set the \ ``EbxmlMessage``\  being referred to by the error message.

   :param refToMessage: \ ``EbxmlMessage``\  object to be referred to.

