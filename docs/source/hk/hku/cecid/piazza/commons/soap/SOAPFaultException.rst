.. java:import:: java.util ArrayList

.. java:import:: java.util Collection

.. java:import:: java.util HashMap

.. java:import:: java.util Iterator

.. java:import:: java.util Map

.. java:import:: javax.xml.soap Name

SOAPFaultException
==================

.. java:package:: hk.hku.cecid.piazza.commons.soap
   :noindex:

.. java:type:: public class SOAPFaultException extends SOAPRequestException

   SOAPFaultException represents a SOAP fault in a SOAP request.

   :author: Hugo Y. K. Lam

Fields
------
SOAP_FAULT_CLIENT
^^^^^^^^^^^^^^^^^

.. java:field:: public static String SOAP_FAULT_CLIENT
   :outertype: SOAPFaultException

SOAP_FAULT_MUST_UNDERSTAND
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String SOAP_FAULT_MUST_UNDERSTAND
   :outertype: SOAPFaultException

SOAP_FAULT_SERVER
^^^^^^^^^^^^^^^^^

.. java:field:: public static String SOAP_FAULT_SERVER
   :outertype: SOAPFaultException

SOAP_FAULT_VERSION_MISMATCH
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String SOAP_FAULT_VERSION_MISMATCH
   :outertype: SOAPFaultException

Constructors
------------
SOAPFaultException
^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SOAPFaultException(String code, String message)
   :outertype: SOAPFaultException

   Creates a new instance of SOAPFaultException.

   :param code: the fault code.
   :param message: the fault string.

SOAPFaultException
^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SOAPFaultException(String code, String message, String actor)
   :outertype: SOAPFaultException

   Creates a new instance of SOAPFaultException.

   :param code: the fault code.
   :param message: the fault string.
   :param actor: the fault actor.

SOAPFaultException
^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SOAPFaultException(String code, String message, Throwable cause)
   :outertype: SOAPFaultException

   Creates a new instance of SOAPFaultException.

   :param code: the fault code.
   :param message: the fault string.
   :param cause: the cause of this exception.

SOAPFaultException
^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SOAPFaultException(String code, String message, String actor, Throwable cause)
   :outertype: SOAPFaultException

   Creates a new instance of SOAPFaultException.

   :param code: the fault code.
   :param message: the fault string.
   :param actor: the fault actor.
   :param cause: the cause of this exception.

Methods
-------
addDetailEntry
^^^^^^^^^^^^^^

.. java:method:: public void addDetailEntry(Name name, Object message)
   :outertype: SOAPFaultException

   Adds a SOAP fault detail entry.

   :param name: the entry name.
   :param message: the message of the detail entry.

getDetailEntryNames
^^^^^^^^^^^^^^^^^^^

.. java:method:: public Iterator getDetailEntryNames()
   :outertype: SOAPFaultException

   Gets the SOAP fault detail entry names.

   :return: the SOAP fault detail entry Name objects.

getDetailEntryValue
^^^^^^^^^^^^^^^^^^^

.. java:method:: public Object getDetailEntryValue(Name name)
   :outertype: SOAPFaultException

   Gets the SOAP fault detail entry value with the specified name.

   :return: the SOAP fault detail entry value.

getFaultActor
^^^^^^^^^^^^^

.. java:method:: public String getFaultActor()
   :outertype: SOAPFaultException

   Gets the fault actor.

   :return: the fault actor.

getFaultCode
^^^^^^^^^^^^

.. java:method:: public String getFaultCode()
   :outertype: SOAPFaultException

   Gets the fault code.

   :return: the fault code.

getFaultString
^^^^^^^^^^^^^^

.. java:method:: public String getFaultString()
   :outertype: SOAPFaultException

   Gets the fault string.

   :return: the fault string.

hasDetailEntries
^^^^^^^^^^^^^^^^

.. java:method:: public boolean hasDetailEntries()
   :outertype: SOAPFaultException

   Checks if there are any SOAP fault detail entries.

   :return: true if there are any SOAP fault detail entries.

init
^^^^

.. java:method:: protected void init(String code, String message, String actor)
   :outertype: SOAPFaultException

   Initializes this SOAP fault exception.

   :param code: the fault code.
   :param message: the fault string.
   :param actor: the fault actor.

