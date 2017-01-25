.. java:import:: hk.hku.cecid.ebms.pkg.validation EbxmlValidationException

.. java:import:: java.util ArrayList

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

ErrorList
=========

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class ErrorList extends HeaderElement

   An ebXML \ ``ErrorList``\  in the SOAP Header of a \ ``HeaderContainer``\

   :author: cyng

Fields
------
ATTRIBUTE_CODE_CONTEXT
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_CODE_CONTEXT
   :outertype: ErrorList

   Name of the codeContext attribute [ebMSS 4.2.3.2.2].

ATTRIBUTE_ERROR_CODE
^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_ERROR_CODE
   :outertype: ErrorList

   Name of the errorCode attribute [ebMSS 4.2.3.2.3].

ATTRIBUTE_HIGHEST_SEVERITY
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_HIGHEST_SEVERITY
   :outertype: ErrorList

   Name of highestSeverity attribute [ebMSS 4.2.3.1].

ATTRIBUTE_LOCATION
^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_LOCATION
   :outertype: ErrorList

   Name of the location attribute [ebMSS 4.2.3.2.5].

ATTRIBUTE_SEVERITY
^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_SEVERITY
   :outertype: ErrorList

   Name of the severity attribute [ebMSS 4.2.3.2.4].

CODE_DELIVERY_FAILURE
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String CODE_DELIVERY_FAILURE
   :outertype: ErrorList

   Non-XML document error: message delivery failure [4.2.3.4.2].

CODE_INCONSISTENT
^^^^^^^^^^^^^^^^^

.. java:field:: public static final String CODE_INCONSISTENT
   :outertype: ErrorList

   Document error: element content or attribute value inconsistent with other elements or attributes [4.2.3.4.1].

CODE_MIME_PROBLEM
^^^^^^^^^^^^^^^^^

.. java:field:: public static final String CODE_MIME_PROBLEM
   :outertype: ErrorList

   Non-XML document error: URI resolve error.

CODE_NOT_SUPPORTED
^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String CODE_NOT_SUPPORTED
   :outertype: ErrorList

   Document error: element or attribute not supported [4.2.3.4.1].

CODE_OTHER_XML
^^^^^^^^^^^^^^

.. java:field:: public static final String CODE_OTHER_XML
   :outertype: ErrorList

   Document error: other error in an element content or attribute value [4.2.3.4.1].

CODE_SECURITY_FAILURE
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String CODE_SECURITY_FAILURE
   :outertype: ErrorList

   Non-XML document error: message security check failed [4.2.3.4.2].

CODE_TIME_TO_LIVE_EXPIRED
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String CODE_TIME_TO_LIVE_EXPIRED
   :outertype: ErrorList

   Non-XML document error: message time to live expired [4.2.3.4.2].

CODE_UNKNOWN
^^^^^^^^^^^^

.. java:field:: public static final String CODE_UNKNOWN
   :outertype: ErrorList

   Non-XML document error: Unknown error.

CODE_VALUE_NOT_RECOGNIZED
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String CODE_VALUE_NOT_RECOGNIZED
   :outertype: ErrorList

   Document error: element content or attribute value not recognized [4.2.3.4.1].

ELEMENT_ERROR
^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_ERROR
   :outertype: ErrorList

   Error element name in ErrorList [ebMSS 4.2.3.2].

ERROR_LIST
^^^^^^^^^^

.. java:field:: static final String ERROR_LIST
   :outertype: ErrorList

   \ ``ErrorList``\  element name

SEVERITY_ERROR
^^^^^^^^^^^^^^

.. java:field:: public static final String SEVERITY_ERROR
   :outertype: ErrorList

   Text for "Error" severity level.

SEVERITY_WARNING
^^^^^^^^^^^^^^^^

.. java:field:: public static final String SEVERITY_WARNING
   :outertype: ErrorList

   Text for "Warning" severity level.

Constructors
------------
ErrorList
^^^^^^^^^

.. java:constructor::  ErrorList(SOAPEnvelope soapEnvelope, String errorCode, String severity, String description) throws SOAPException
   :outertype: ErrorList

   Constructs an \ ``ErrorList``\  with the given mandatory fields.

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header of which the \ ``ErrorList``\  is added.
   :param errorCode: Error code value of the error.
   :param severity: Severity of the error.
   :param description: Description of the error.
   :throws SOAPException:

ErrorList
^^^^^^^^^

.. java:constructor::  ErrorList(SOAPEnvelope soapEnvelope, String errorCode, String severity, String description, String lang) throws SOAPException
   :outertype: ErrorList

   Constructs an \ ``ErrorList``\  with the given mandatory fields.

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header of which the \ ``ErrorList``\  is added.
   :param errorCode: Error code value of the error.
   :param severity: Severity of the error.
   :param description: Description of the error.
   :param lang: Language of the description specified in \ ` RFC 1766 <http://www.ietf.org/rfc/rfc1766.txt>`_\  and ISO639.
   :throws SOAPException:

ErrorList
^^^^^^^^^

.. java:constructor::  ErrorList(SOAPEnvelope soapEnvelope, String errorCode, String severity, String description, String lang, String location) throws SOAPException
   :outertype: ErrorList

   Constructs an \ ``ErrorList``\  with the given mandatory fields.

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header of which the \ ``ErrorList``\  is added.
   :param errorCode: Error code value of the error.
   :param severity: Severity of the error.
   :param description: Description of the error.
   :param lang: Language of the description specified in \ ` RFC 1766 <http://www.ietf.org/rfc/rfc1766.txt>`_\  and ISO639.
   :throws SOAPException:

ErrorList
^^^^^^^^^

.. java:constructor::  ErrorList(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: ErrorList

   Constructs an \ ``ErrorList``\  object by parsing the given \ ``SOAPElement``\  object.

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header of which the \ ``ErrorList``\  is added.
   :param soapElement: \ ``SOAPElement``\  object to be read into the \ ``ErrorList``\  object.
   :throws SOAPException:

Methods
-------
addError
^^^^^^^^

.. java:method:: public void addError(String errorCode, String severity, String description) throws SOAPException
   :outertype: ErrorList

   Add an  element to the error list.

   :param errorCode: Error code value.
   :param severity: Severity of the error.
   :param description: Description of the error.
   :throws SOAPException:

addError
^^^^^^^^

.. java:method:: public void addError(String errorCode, String severity, String description, String lang) throws SOAPException
   :outertype: ErrorList

   Add an  element to the error list.

   :param errorCode: Error code value.
   :param severity: Severity of the error.
   :param description: Description of the error.
   :param lang: Language of the description specified in \ ` RFC 1766 <http://www.ietf.org/rfc/rfc1766.txt>`_\  and ISO639.
   :throws SOAPException:

addError
^^^^^^^^

.. java:method:: public void addError(String errorCode, String severity, String description, String lang, String location) throws SOAPException
   :outertype: ErrorList

   Add an  element to the error list.

   :param errorCode: Error code value.
   :param severity: Severity of the error.
   :param description: Description of the error.
   :param lang: Language of the description specified in \ ` RFC 1766 <http://www.ietf.org/rfc/rfc1766.txt>`_\  and ISO639.
   :param location: Location of the message containing error.
   :throws SOAPException:

getErrors
^^^^^^^^^

.. java:method:: public Iterator getErrors()
   :outertype: ErrorList

   Gets all \ ``ErrorList.Error``\ s in this \ ``ErrorList``\

getHighestSeverity
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getHighestSeverity()
   :outertype: ErrorList

   Get the highest severity of all the \ ``ErrorList.Error``\  objects in the \ ``ErrorList``\ .

   :return: Highest severity of the errors.

