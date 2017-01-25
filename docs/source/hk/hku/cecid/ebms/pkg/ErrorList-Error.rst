.. java:import:: hk.hku.cecid.ebms.pkg.validation EbxmlValidationException

.. java:import:: java.util ArrayList

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

ErrorList.Error
===============

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public static final class Error
   :outertype: ErrorList

   An \ ``Error``\  inside an \ ``ErrorList``\

Constructors
------------
Error
^^^^^

.. java:constructor::  Error(String errorCode, String severity, Description description)
   :outertype: ErrorList.Error

   Initializes Error object using given error code, severity and description.

   :param errorCode: Error code value. Please refer to [ebMSS 4.2.3.4.1] for a list of valid error codes.
   :param severity: Severity of the error reported.
   :param description: Human-readable description of error.

Error
^^^^^

.. java:constructor::  Error(String errorCode, String severity, Description description, String location)
   :outertype: ErrorList.Error

   Initializes Error object using given error code, severity and description.

   :param errorCode: Error code value. Please refer to [ebMSS 4.2.3.4.1] for a list of valid error codes.
   :param severity: Severity of the error reported.
   :param description: Human-readable description of error.
   :param location: Location of the message containing the error.

Methods
-------
getDescription
^^^^^^^^^^^^^^

.. java:method:: public Description getDescription()
   :outertype: ErrorList.Error

   Get the description contained in the object.

   :return: Description of the error.

getErrorCode
^^^^^^^^^^^^

.. java:method:: public String getErrorCode()
   :outertype: ErrorList.Error

   Get the error code contained in the object.

   :return: Error code.

getLocation
^^^^^^^^^^^

.. java:method:: public String getLocation()
   :outertype: ErrorList.Error

   Get the location of the message containing the error.

   :return: Location string.

getSeverity
^^^^^^^^^^^

.. java:method:: public String getSeverity()
   :outertype: ErrorList.Error

   Get the severity level contained in the object.

   :return: Severity level.

