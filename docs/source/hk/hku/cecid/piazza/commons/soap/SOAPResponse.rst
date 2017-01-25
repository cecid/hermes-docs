.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap Detail

.. java:import:: javax.xml.soap DetailEntry

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPBody

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPFault

.. java:import:: javax.xml.soap SOAPMessage

SOAPResponse
============

.. java:package:: hk.hku.cecid.piazza.commons.soap
   :noindex:

.. java:type:: public class SOAPResponse

   The SOAPResponse class represents a SOAP response. It is independent of which transport protocol it is using and contains the SOAP message of the target response.

   :author: Hugo Y. K. Lam

Constructors
------------
SOAPResponse
^^^^^^^^^^^^

.. java:constructor::  SOAPResponse()
   :outertype: SOAPResponse

   Creates a new instance of SOAPResponse.

SOAPResponse
^^^^^^^^^^^^

.. java:constructor::  SOAPResponse(Object target)
   :outertype: SOAPResponse

   Creates a new instance of SOAPResponse.

   :param target: the target that this response should be committed to.

Methods
-------
addFault
^^^^^^^^

.. java:method:: public SOAPFault addFault(String code, String actor, String desc) throws SOAPException
   :outertype: SOAPResponse

   Adds a SOAP fault to the SOAP message of this response.

   :param code: the fault code.
   :param actor: the fault actor.
   :param desc: the fault description.
   :throws SOAPException: a SOAP error occurred when adding the the fault.
   :return: the SOAP fault which has been added to the SOAP message. null if there is no SOAP message in this response or the fault has already been added.

addFault
^^^^^^^^

.. java:method:: public SOAPFault addFault(Throwable cause) throws SOAPException
   :outertype: SOAPResponse

   Adds a SOAP fault to the SOAP message of this response.

   :param cause: the exception cause.
   :throws SOAPException: a SOAP error occurred when adding the the fault.
   :return: the SOAP fault which has been added to the SOAP message. null if there is no SOAP message in this response or the fault has already been added.

getMessage
^^^^^^^^^^

.. java:method:: public SOAPMessage getMessage()
   :outertype: SOAPResponse

   Gets the SOAP message of this response.

   :return: the SOAP message of this response.

getTarget
^^^^^^^^^

.. java:method:: public Object getTarget()
   :outertype: SOAPResponse

   Gets the target that this response should be committed to.

   :return: the target that this response should be committed to.

setMessage
^^^^^^^^^^

.. java:method:: public void setMessage(SOAPMessage message)
   :outertype: SOAPResponse

   Sets the SOAP message of this response.

   :param message: the SOAP message of this response.

setTarget
^^^^^^^^^

.. java:method::  void setTarget(Object target)
   :outertype: SOAPResponse

   Sets the target that this response should be committed to.

   :param target: the target that this response should be committed to.

