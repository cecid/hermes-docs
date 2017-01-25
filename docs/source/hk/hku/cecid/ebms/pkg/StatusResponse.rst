.. java:import:: hk.hku.cecid.ebms.pkg.validation SOAPValidationException

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

StatusResponse
==============

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class StatusResponse extends BodyElement

   An ebXML \ ``StatusResponse``\  in the SOAP Body of a \ ``HeaderContainer``\  [ebMSS 7.1.2].

   :author: cyng

Fields
------
ATTRIBUTE_MESSAGE_STATUS
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_MESSAGE_STATUS
   :outertype: StatusResponse

   Name of the messageStatus attribute.

ELEMENT_REF_TO_MESSAGE_ID
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_REF_TO_MESSAGE_ID
   :outertype: StatusResponse

   Name of the RefToMessageID element.

ELEMENT_TIMESTAMP
^^^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_TIMESTAMP
   :outertype: StatusResponse

   Name of the Timestamp element.

STATUS_RESPONSE
^^^^^^^^^^^^^^^

.. java:field:: static final String STATUS_RESPONSE
   :outertype: StatusResponse

   \ ``StatusRequest``\  element name

Constructors
------------
StatusResponse
^^^^^^^^^^^^^^

.. java:constructor::  StatusResponse(SOAPEnvelope soapEnvelope, String refToMessageId, String messageStatus) throws SOAPException
   :outertype: StatusResponse

   Constructs a \ ``StatusResponse``\  with the given mandatory fields

   :param soapEnvelope: \ ``SOAPEnvelope``\  to which the status response element will be added.
   :param refToMessageId: Identifier of the message whose status is being reported. [ebMSS 7.3.1].
   :param messageStatus: Message status response string [ebMSS 7.3.3].
   :throws SOAPException:

StatusResponse
^^^^^^^^^^^^^^

.. java:constructor::  StatusResponse(SOAPEnvelope soapEnvelope, String refToMessageId, String messageStatus, String timestamp) throws SOAPException
   :outertype: StatusResponse

   Constructs a \ ``StatusResponse``\  with the given mandatory fields

   :param soapEnvelope: \ ``SOAPEnvelope``\  to which the status response element will be added.
   :param refToMessageId: Identifier of the message whose status is being reported. [ebMSS 7.3.1].
   :param messageStatus: Message status response string [ebMSS 7.3.3].
   :param timestamp: Timestamp of the message the status is being reported.
   :throws SOAPException:

StatusResponse
^^^^^^^^^^^^^^

.. java:constructor::  StatusResponse(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: StatusResponse

   Constructs a \ ``StatusResponse``\  object by parsing the given \ ``SOAPElement``\ .

   :param soapEnvelope: \ ``SOAPEnvelope``\  to which the status response element will be added.
   :param soapElement: \ ``SOAPElement``\  from which a \ ``StatusResponse``\  object is constructed.
   :throws SOAPException:

Methods
-------
getMessageStatus
^^^^^^^^^^^^^^^^

.. java:method:: public String getMessageStatus()
   :outertype: StatusResponse

   Gets the status of the message whose status is reported.

   :return: Message status.

getRefToMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public String getRefToMessageId()
   :outertype: StatusResponse

   Gets Identifier of the message whose status is reported.

   :return: Identifier of the message being referred.

getTimestamp
^^^^^^^^^^^^

.. java:method:: public String getTimestamp()
   :outertype: StatusResponse

   Get the timestamp of the message when it was received by the party who reported its status.

   :return: Message timestamp when it was received.

