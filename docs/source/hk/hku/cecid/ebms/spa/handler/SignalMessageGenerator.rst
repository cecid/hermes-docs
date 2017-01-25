.. java:import:: hk.hku.cecid.ebms.spa EbmsUtility

.. java:import:: hk.hku.cecid.ebms.pkg Acknowledgment

.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.pkg MessageHeader

.. java:import:: hk.hku.cecid.ebms.pkg Signature

.. java:import:: hk.hku.cecid.ebms.pkg SignatureReference

.. java:import:: hk.hku.cecid.piazza.commons.util DataFormatter

.. java:import:: hk.hku.cecid.piazza.commons.util Generator

.. java:import:: java.util Date

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap SOAPException

SignalMessageGenerator
======================

.. java:package:: hk.hku.cecid.ebms.spa.handler
   :noindex:

.. java:type:: public class SignalMessageGenerator

   \ ``SignalMessageGenerator``\  is an utility api for the user to generate some signal message

   :author: pykoon

Methods
-------
generateAcknowledgment
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static EbxmlMessage generateAcknowledgment(EbxmlMessage ackRequestedMessage, String refToMessageId) throws SOAPException
   :outertype: SignalMessageGenerator

   Generates acknowledgement message from the given acknowledgement request message and the refToMessageId. Note that the acknowledgment message is not signed.

   :param ackRequestedMessage: Acknowledgement request message.
   :param refToMessageId: MessageId of the message to which the acknowledgement response should be referred.
   :throws SOAPException:
   :return: Acknowledgement message.

generateAcknowledgment
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static EbxmlMessage generateAcknowledgment(EbxmlMessage ackRequestedMessage) throws SOAPException
   :outertype: SignalMessageGenerator

   Generates acknowledgement message from the given acknowledgement request message and the refToMessageId. Note that the acknowledgment message is not signed.

   :param ackRequestedMessage: Acknowledgement request message.
   :throws SOAPException:
   :return: Acknowledgement message.

generateErrorMessage
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static EbxmlMessage generateErrorMessage(EbxmlMessage ebxmlMessage, String errorCode, String severity, String description, String location) throws SOAPException
   :outertype: SignalMessageGenerator

   Generates an error message containing the specfied error code [ebMSS 4.2.3.4.1].

   :param ebxmlMessage: ebXML message to which error list should be attached.
   :param errorCode: Error code of the message.
   :param severity: Error severity, either ERROR or WARNING.
   :param description: Human-readable description of the error message.
   :param location: Source of the error.
   :throws SOAPException:
   :return: ebXML message containing error code.

generateErrorMessageBySender
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static EbxmlMessage generateErrorMessageBySender(EbxmlMessage ebxmlMessage, String errorCode, String severity, String description, String location) throws SOAPException
   :outertype: SignalMessageGenerator

generatePongMessage
^^^^^^^^^^^^^^^^^^^

.. java:method:: public static EbxmlMessage generatePongMessage(EbxmlMessage pingMessage) throws SOAPException
   :outertype: SignalMessageGenerator

   Generates pong message from the given ping message [ebMSS 8.2].

   :param pingMessage: Incoming ping message.
   :throws SOAPException:
   :return: Pong message in response of the incoming ping message.

generateStatusResponseMessage
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static EbxmlMessage generateStatusResponseMessage(EbxmlMessage statusRequestMessage, String status, Date timestamp) throws SOAPException
   :outertype: SignalMessageGenerator

   Generates response message from the given status request message and the status string [ebMSS 7.1.2].

   :param statusRequestMessage: Status request message.
   :param status: Current status of the message service handler.
   :throws SOAPException:
   :return: Status response message.

