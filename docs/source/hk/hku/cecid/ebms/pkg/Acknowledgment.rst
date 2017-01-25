.. java:import:: hk.hku.cecid.ebms.pkg.validation SOAPValidationException

.. java:import:: java.util ArrayList

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap Text

Acknowledgment
==============

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class Acknowledgment extends HeaderElement

   An ebXML \ ``Acknowledgment``\  in the SOAP Header of a \ ``HeaderContainer``\  [ebMSS 6.3.2].

   :author: cyng

Fields
------
ACKNOWLEDGMENT
^^^^^^^^^^^^^^

.. java:field:: static final String ACKNOWLEDGMENT
   :outertype: Acknowledgment

   \ ``Acknowledgment``\  element name

Constructors
------------
Acknowledgment
^^^^^^^^^^^^^^

.. java:constructor::  Acknowledgment(SOAPEnvelope soapEnvelope, String timestamp, EbxmlMessage refToMessage, String fromPartyId, String fromPartyIdType) throws SOAPException
   :outertype: Acknowledgment

   Constructs an \ ``Acknowledgment``\  with the given mandatory fields.

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header container of which the \ ``Acknowledgement``\  is attached to.
   :param timestamp: The time the message service handler received the message to be acknowledged.
   :param refToMessage: The message this acknowledgement response is referring to.
   :param fromPartyId: The identifier of the party generating the acknowledgement response message.
   :param fromPartyIdType: PartyId type
   :throws SOAPException:

Acknowledgment
^^^^^^^^^^^^^^

.. java:constructor::  Acknowledgment(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: Acknowledgment

   Constructs an \ ``Acknowledgement``\  object by parsing the given \ ``SOAPElement``\ .

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header container of which the \ ``Acknowledgement``\  is attached to.
   :param soapElement: \ ``SOAPElement``\  containing acknowledgement response.
   :throws SOAPException:

Methods
-------
addFromPartyId
^^^^^^^^^^^^^^

.. java:method:: public void addFromPartyId(String id) throws SOAPException
   :outertype: Acknowledgment

   Add sender's PartyID into this \ ``Acknowledgement``\

   :param id: Sender's PartyID string.
   :throws SOAPException:

addFromPartyId
^^^^^^^^^^^^^^

.. java:method:: public void addFromPartyId(String id, String type) throws SOAPException
   :outertype: Acknowledgment

   Add sender's PartyID and its type into this \ ``Acknowledgement``\

   :param id: Sender's PartyID string.
   :param type: PartyID type.
   :throws SOAPException:

addSignatureReference
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void addSignatureReference(SignatureReference reference) throws SOAPException
   :outertype: Acknowledgment

getFromPartyIds
^^^^^^^^^^^^^^^

.. java:method:: public Iterator getFromPartyIds()
   :outertype: Acknowledgment

   Get the identifiers of the party generating the acknowledgement response

   :return: Iterator of \ ``MessageHeader.PartyId``\

getRefToMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public String getRefToMessageId()
   :outertype: Acknowledgment

   Get the identifier of the message being acknowledged.

   :return: Identifier of the message being acknowledged.

getSignatureReferences
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public Iterator getSignatureReferences()
   :outertype: Acknowledgment

getTimestamp
^^^^^^^^^^^^

.. java:method:: public String getTimestamp()
   :outertype: Acknowledgment

   Get the time that the message being acknowledged is received.

   :return: Timestamp expressed in UTC format.

