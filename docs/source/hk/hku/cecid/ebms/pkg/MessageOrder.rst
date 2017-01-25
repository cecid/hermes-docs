.. java:import:: hk.hku.cecid.ebms.pkg.validation EbxmlValidationException

.. java:import:: hk.hku.cecid.ebms.pkg.validation SOAPValidationException

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

MessageOrder
============

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class MessageOrder extends HeaderElement

   An ebXML \ ``MessageOrder``\  in the SOAP Header of a \ ``HeaderContainer``\  [ebMSS 9.1].

   :author: tslam

Fields
------
ATTRIBUTE_STATUS
^^^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_STATUS
   :outertype: MessageOrder

   Name of the status attribute

ELEMENT_SEQUENCE_NUMBER
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_SEQUENCE_NUMBER
   :outertype: MessageOrder

   SequenceNumber element name

MESSAGE_ORDER
^^^^^^^^^^^^^

.. java:field:: static final String MESSAGE_ORDER
   :outertype: MessageOrder

   \ ``MessageOrder``\  element name

STATUS_CONTINUE
^^^^^^^^^^^^^^^

.. java:field:: public static final int STATUS_CONTINUE
   :outertype: MessageOrder

   Subsequent messages in the conversation and the sequence number is not reset.

STATUS_RESET
^^^^^^^^^^^^

.. java:field:: public static final int STATUS_RESET
   :outertype: MessageOrder

   First mesage in conversation / reset the sequence number counter.

VALUE_STATUS_CONTINUE
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String VALUE_STATUS_CONTINUE
   :outertype: MessageOrder

   Name of the "Continue" status

VALUE_STATUS_RESET
^^^^^^^^^^^^^^^^^^

.. java:field:: static final String VALUE_STATUS_RESET
   :outertype: MessageOrder

   Name of the "Reset" status

Constructors
------------
MessageOrder
^^^^^^^^^^^^

.. java:constructor::  MessageOrder(SOAPEnvelope soapEnvelope, int status, int sequenceNo) throws SOAPException
   :outertype: MessageOrder

   Constructs a \ ``MessageOrder``\  with the given mandatory fields.

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header container of which the \ ``MessageOrder``\  is attached to.
   :param status: Status of the sequence number.
   :param sequenceNo: The sequence number in the converstaion.
   :throws SOAPException:

MessageOrder
^^^^^^^^^^^^

.. java:constructor::  MessageOrder(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: MessageOrder

   Constructs an \ ``MessageOrder``\  object by parsing the given \ ``SOAPElement``\ .

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header container of which the \ ``MessageOrder``\  is attached to.
   :param soapElement: \ ``SOAPElement``\  containing SequenceNumber element.
   :throws SOAPException:

Methods
-------
getSequenceNumber
^^^^^^^^^^^^^^^^^

.. java:method:: public int getSequenceNumber()
   :outertype: MessageOrder

   Get the sequence number in the conversation. Note that although the word "conversation" is used in the specification, the sequence number is set and incremented by one party only. It means that both parties need to keep their own sequence numbers for all outgoing messages.

   :return: sequence number.

getStatus
^^^^^^^^^

.. java:method:: public int getStatus()
   :outertype: MessageOrder

   Get the status of the sequence number which can be "Reset" or "Continue".

   :return: Status of the sequence number.

