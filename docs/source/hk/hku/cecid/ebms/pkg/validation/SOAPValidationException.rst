.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: javax.xml.soap Detail

.. java:import:: javax.xml.soap DetailEntry

.. java:import:: javax.xml.soap MessageFactory

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPBody

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPFault

.. java:import:: javax.xml.soap SOAPMessage

.. java:import:: javax.xml.soap SOAPPart

SOAPValidationException
=======================

.. java:package:: hk.hku.cecid.ebms.pkg.validation
   :noindex:

.. java:type:: public class SOAPValidationException extends ValidationException

   Exception class that can generate SOAP fault messages from the information it has been given.

   :author: Frankie Lam

Fields
------
ELEMENT_ERROR
^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_ERROR
   :outertype: SOAPValidationException

   Error element to be embedded in the detail entries

NAMESPACE_PREFIX_CECID
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_PREFIX_CECID
   :outertype: SOAPValidationException

   CECID namespace prefix

NAMESPACE_PREFIX_SOAP_ENVELOPE
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_PREFIX_SOAP_ENVELOPE
   :outertype: SOAPValidationException

   SOAP Envelope namespace prefix.

NAMESPACE_URI_CECID
^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_URI_CECID
   :outertype: SOAPValidationException

   CECID Elements namespace

NAMESPACE_URI_SOAP_ENVELOPE
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String NAMESPACE_URI_SOAP_ENVELOPE
   :outertype: SOAPValidationException

   SOAP Envelope namespace.

SOAP_FAULT_CLIENT
^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SOAP_FAULT_CLIENT
   :outertype: SOAPValidationException

   SOAP Fault code indicating a client fault that the message should not be resent without change.

SOAP_FAULT_MUST_UNDERSTAND
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SOAP_FAULT_MUST_UNDERSTAND
   :outertype: SOAPValidationException

   SOAP Fault code indicating that the client cannot interpret an immediate child of the header element having mustUnderstand equals to "1".

SOAP_FAULT_SERVER
^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SOAP_FAULT_SERVER
   :outertype: SOAPValidationException

   SOAP Fault code indicating a server fault that the message may succeed by resending at a later time.

SOAP_FAULT_VERSION_MISMATCH
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SOAP_FAULT_VERSION_MISMATCH
   :outertype: SOAPValidationException

   SOAP Fault code indicating version mismatch.

detail
^^^^^^

.. java:field:: protected final String detail
   :outertype: SOAPValidationException

   SOAP Fault detail.

faultActor
^^^^^^^^^^

.. java:field:: protected final String faultActor
   :outertype: SOAPValidationException

   SOAP Fault Actor.

Constructors
------------
SOAPValidationException
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SOAPValidationException(String faultCode, String faultString)
   :outertype: SOAPValidationException

   Constructs a \ ``SOAPValidationException``\  object given its fault code and fault string.

   :param faultCode: Fault codes as specified in the SOAP 1.1 specification
   :param faultString: Human readable explanation of the fault.

SOAPValidationException
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SOAPValidationException(String faultCode, String faultString, String detail)
   :outertype: SOAPValidationException

   Constructs a \ ``SOAPValidationException``\  object given its fault code and fault string.

   :param faultCode: Fault codes as specified in the SOAP 1.1 specification
   :param faultString: Human readable explanation of the fault.
   :param detail: Specific error information related to the SOAP Body element. It must be present if the SOAP Body cannot be processed successfully, and must NOT be present if the error is caused by header entries.

SOAPValidationException
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SOAPValidationException(String faultCode, String faultString, String faultActor, String detail)
   :outertype: SOAPValidationException

   Constructs a \ ``SOAPValidationException``\  object given its fault code and fault string.

   :param faultCode: Fault codes as specified in the SOAP 1.1 specification
   :param faultString: Human readable explanation of the fault.
   :param faultActor: Information on who caused the fault to happen.
   :param detail: Specific error information related to the SOAP Body element. It must be present if the SOAP Body cannot be processed successfully, and must NOT be present if the error is caused by header entries.

Methods
-------
getSOAPMessage
^^^^^^^^^^^^^^

.. java:method:: public SOAPMessage getSOAPMessage()
   :outertype: SOAPValidationException

   Get SOAP Fault message from the information given.

   :return: \ ``SOAPMessage``\  object containing Fault element.

