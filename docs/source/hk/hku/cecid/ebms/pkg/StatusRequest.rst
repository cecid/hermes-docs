.. java:import:: hk.hku.cecid.ebms.pkg.validation SOAPValidationException

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

StatusRequest
=============

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class StatusRequest extends BodyElement

   An ebXML \ ``StatusRequest``\  in the SOAP Body of a \ ``HeaderContainer``\  [ebMSS 7.1.1].

   :author: cyng

Fields
------
ELEMENT_REF_TO_MESSAGE_ID
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_REF_TO_MESSAGE_ID
   :outertype: StatusRequest

   Name of the RefToMessageID element.

STATUS_REQUEST
^^^^^^^^^^^^^^

.. java:field:: static final String STATUS_REQUEST
   :outertype: StatusRequest

   Name of the \ ``StatusRequest``\  element.

Constructors
------------
StatusRequest
^^^^^^^^^^^^^

.. java:constructor::  StatusRequest(SOAPEnvelope soapEnvelope, String refToMessageId) throws SOAPException
   :outertype: StatusRequest

   Constructs a \ ``StatusRequested``\  with the given mandatory fields.

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header of which status request element will be added to.
   :param refToMessageId: Identifier of the message that this status message intends to query.
   :throws SOAPException:

StatusRequest
^^^^^^^^^^^^^

.. java:constructor::  StatusRequest(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: StatusRequest

   Constructs a \ ``StatusRequest``\  object by parsing the given \ ``SOAPElement``\ .

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header of which status request element will be added to.
   :param soapElement: \ ``SOAPElement``\  from which a \ ``StatusRequest``\  object is constructed.
   :throws SOAPException:

Methods
-------
getRefToMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public String getRefToMessageId()
   :outertype: StatusRequest

   Get the identifier of the message the status request refers to.

   :return: Identifier of the message being referred to by status request.

