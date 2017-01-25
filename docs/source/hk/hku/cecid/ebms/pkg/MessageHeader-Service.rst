.. java:import:: hk.hku.cecid.ebms.pkg.validation SOAPValidationException

.. java:import:: java.util ArrayList

.. java:import:: java.util Calendar

.. java:import:: java.util Date

.. java:import:: java.util Iterator

.. java:import:: java.util TimeZone

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

MessageHeader.Service
=====================

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public static final class Service
   :outertype: MessageHeader

   A class representing service element in the \ ``MessageHeader``\

Constructors
------------
Service
^^^^^^^

.. java:constructor::  Service(String service, String type)
   :outertype: MessageHeader.Service

   Initializes service object from given service name and type

Methods
-------
getService
^^^^^^^^^^

.. java:method:: public String getService()
   :outertype: MessageHeader.Service

   Gets service name.

   :return: Service name.

getType
^^^^^^^

.. java:method:: public String getType()
   :outertype: MessageHeader.Service

   Gets service type.

   :return: Service type.

setType
^^^^^^^

.. java:method::  void setType(String type)
   :outertype: MessageHeader.Service

   Sets service type.

   :param type: Service type string.

