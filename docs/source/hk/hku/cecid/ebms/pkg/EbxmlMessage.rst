.. java:import:: hk.hku.cecid.ebms.pkg.validation EbxmlValidationException

.. java:import:: hk.hku.cecid.ebms.pkg.validation SOAPValidationException

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io File

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: java.io PushbackInputStream

.. java:import:: java.util ArrayList

.. java:import:: java.util HashMap

.. java:import:: java.util Iterator

.. java:import:: java.util Map

.. java:import:: javax.activation DataHandler

.. java:import:: javax.activation DataSource

.. java:import:: javax.activation FileDataSource

.. java:import:: javax.mail MessagingException

.. java:import:: javax.mail.internet MimeUtility

.. java:import:: javax.xml.soap AttachmentPart

.. java:import:: javax.xml.soap MessageFactory

.. java:import:: javax.xml.soap MimeHeader

.. java:import:: javax.xml.soap MimeHeaders

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPMessage

EbxmlMessage
============

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class EbxmlMessage

   A representation of an ebXML message. An ebXML message conforms to the \ ` SOAP 1.1 with Attachments Specification  <http://www.w3.org/TR/2000/NOTE-SOAP-attachments-20001211>`_\ . This \ ``EbxmlMessage``\  encapsulates a \ ``javax.xml.soap.SOAPMessage``\ .

   :author: cyng

Fields
------
CHARACTER_SET_ENCODING
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String CHARACTER_SET_ENCODING
   :outertype: EbxmlMessage

   Default value XML character set

SOAP_ACTION
^^^^^^^^^^^

.. java:field:: public static final String SOAP_ACTION
   :outertype: EbxmlMessage

   SOAPAction in the SOAP message MIME header

SOAP_ACTION_VALUE
^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SOAP_ACTION_VALUE
   :outertype: EbxmlMessage

   SOAPAction value in the SOAP message MIME header

SOAP_PART_CONTENT_ID
^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String SOAP_PART_CONTENT_ID
   :outertype: EbxmlMessage

   Default content id of soap part

WRITE_XML_DECLARATION
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final boolean WRITE_XML_DECLARATION
   :outertype: EbxmlMessage

   Default value of writing XML declaration in front of message

mimeBoundary
^^^^^^^^^^^^

.. java:field:: public static final String mimeBoundary
   :outertype: EbxmlMessage

   MIME boundary generated

needPatch
^^^^^^^^^

.. java:field:: public static boolean needPatch
   :outertype: EbxmlMessage

   Description of the Field

Constructors
------------
EbxmlMessage
^^^^^^^^^^^^

.. java:constructor:: public EbxmlMessage() throws SOAPException
   :outertype: EbxmlMessage

   Constructs an \ ``EbxmlMessage``\  using the default JAXM \ ``MessageFactory``\  implementation

   :throws SOAPException: Description of the Exception

EbxmlMessage
^^^^^^^^^^^^

.. java:constructor:: public EbxmlMessage(MessageFactory messageFactory) throws SOAPException
   :outertype: EbxmlMessage

   Constructs an \ ``EbxmlMessage``\  using the provided \ ``javax.xml.soap.MessageFactory``\

   :param messageFactory: \ ``MessageFactory``\  for creating message.
   :throws SOAPException: Description of the Exception

EbxmlMessage
^^^^^^^^^^^^

.. java:constructor:: public EbxmlMessage(File file) throws SOAPException, IOException
   :outertype: EbxmlMessage

   construct an \ ``EbxmlMessage``\  from File using the logic in MessageServer. The file must not contain any content header like Content-Type

   :param file: the file contain the messsage.
   :throws SOAPException: Description of the Exception
   :throws IOException: Description of the Exception

EbxmlMessage
^^^^^^^^^^^^

.. java:constructor:: public EbxmlMessage(InputStream inputStream) throws SOAPException, IOException
   :outertype: EbxmlMessage

   constructs an \ ``EbxmlMessage``\  from InputStream using the logic in MessageServer. The input stream must not contain any content headers like Content-type.

   :param inputStream: Description of the Parameter
   :throws SOAPException: Description of the Exception
   :throws IOException: Description of the Exception

EbxmlMessage
^^^^^^^^^^^^

.. java:constructor:: public EbxmlMessage(SOAPMessage soapMessage) throws SOAPException
   :outertype: EbxmlMessage

   Constructs an \ ``EbxmlMessage``\  using the given \ ``SOAPMessage``\

   :param soapMessage:
   :throws SOAPException: Description of the Exception

EbxmlMessage
^^^^^^^^^^^^

.. java:constructor:: public EbxmlMessage(MimeHeaders headers, InputStream in) throws IOException, SOAPException
   :outertype: EbxmlMessage

   Constructs a \ ``EbxmlMessage``\  using the given \ ``InputStream``\  and default JAXM \ ``MessageFactory``\  implementation

   :param headers: MIME headers to be included in the message.
   :param in: Message content in form of \ ``InputStream``\ .
   :throws IOException: Description of the Exception
   :throws SOAPException: Description of the Exception

Methods
-------
addAckRequested
^^^^^^^^^^^^^^^

.. java:method:: public void addAckRequested(boolean signed) throws SOAPException
   :outertype: EbxmlMessage

   Add acknowledgement request element to the message.

   :param signed: The feature to be added to the AckRequested attribute
   :throws SOAPException:

addAcknowledgment
^^^^^^^^^^^^^^^^^

.. java:method:: public void addAcknowledgment(String timestamp, EbxmlMessage refToMessage) throws SOAPException
   :outertype: EbxmlMessage

   Add acknowledgement element to the message using given timestamp, refToMessageId.

   :param timestamp: Timestamp string expressed in UTC format.
   :param refToMessage: The feature to be added to the Acknowledgment attribute
   :throws SOAPException: Description of the Exception

addAcknowledgment
^^^^^^^^^^^^^^^^^

.. java:method:: public void addAcknowledgment(String timestamp, EbxmlMessage refToMessage, String fromPartyId) throws SOAPException
   :outertype: EbxmlMessage

   Add acknowledgement element to the message using given timestamp, refToMessageId and fromPartyId.

   :param timestamp: Timestamp string expressed in UTC format.
   :param fromPartyId: Sender party ID.
   :param refToMessage: The feature to be added to the Acknowledgment attribute
   :throws SOAPException: Description of the Exception

addAcknowledgment
^^^^^^^^^^^^^^^^^

.. java:method:: public void addAcknowledgment(String timestamp, EbxmlMessage refToMessage, String fromPartyId, String fromPartyIdType) throws SOAPException
   :outertype: EbxmlMessage

   Add acknowledgement element to the message using given timestamp, refToMessageId, fromPartyId and fromPartyIdType.

   :param timestamp: Timestamp string expressed in UTC format.
   :param fromPartyId: Sender party ID.
   :param fromPartyIdType: Sender party ID type.
   :param refToMessage: The feature to be added to the Acknowledgment attribute
   :throws SOAPException: Description of the Exception

addErrorList
^^^^^^^^^^^^

.. java:method:: public void addErrorList(String errorCode, String severity, String description) throws SOAPException
   :outertype: EbxmlMessage

   Add an error list to the message using given error code, severity and description.

   :param errorCode: [ebMSS 4.2.3.4]
   :param severity: Valid values are "Error" and "Warning".
   :param description: Description of the error.
   :throws SOAPException: Description of the Exception

addErrorList
^^^^^^^^^^^^

.. java:method:: public void addErrorList(String errorCode, String severity, String description, String location) throws SOAPException
   :outertype: EbxmlMessage

   Add an error list to the message using given error code, severity and description.

   :param errorCode: [ebMSS 4.2.3.4]
   :param severity: Valid values are "Error" and "Warning".
   :param description: Description of the error.
   :param location: Location of the message containing the error.
   :throws SOAPException:

addMessageHeader
^^^^^^^^^^^^^^^^

.. java:method:: public MessageHeader addMessageHeader(String fromPartyId, String toPartyId, String cpaId, String conversationId, String service, String action, String messageId, String timestamp) throws SOAPException
   :outertype: EbxmlMessage

   Adds a \ ``MessageHeader``\  to this \ ``EbxmlMessage``\  with the given mandatory fields

   :param fromPartyId: Party ID of the sender [ebMSS 3.1.1.1]
   :param toPartyId: Party ID of the receiver [ebMSS 3.1.1.1]
   :param cpaId: CPA Id [ebMSS 3.1.2]
   :param conversationId: ID of the conversation in which this message is involved [ebMSS 3.1.3]
   :param service: Service name [ebMSS 3.1.4]
   :param action: Action name [ebMSS 3.1.5]
   :param messageId: Unique identifier of the message [ebMSS 3.1.6.1]
   :param timestamp: Date/time of the message header creation expressed as UTC [ebMSS 3.1.6.2]
   :throws SOAPException: Description of the Exception
   :return: the newly added \ ``MessageHeader``\

addMessageHeader
^^^^^^^^^^^^^^^^

.. java:method:: public MessageHeader addMessageHeader(String fromPartyId, String fromPartyIdType, String toPartyId, String toPartyIdType, String cpaId, String conversationId, String service, String action, String messageId, String timestamp) throws SOAPException
   :outertype: EbxmlMessage

   Adds a \ ``MessageHeader``\  to this \ ``EbxmlMessage``\  with the given mandatory fields

   :param fromPartyId: Party ID of the sender [ebMSS 3.1.1.1]
   :param fromPartyIdType: PartyID type of the sender [ebMSS 3.1.1.1]
   :param toPartyId: Party ID of the receiver [ebMSS 3.1.1.1]
   :param toPartyIdType: PartyID type of the receiver [ebMSS 3.1.1.1]
   :param cpaId: CPA Id [ebMSS 3.1.2]
   :param conversationId: ID of the conversation in which this message is involved [ebMSS 3.1.3]
   :param service: Service name [ebMSS 3.1.4]
   :param action: Action name [ebMSS 3.1.5]
   :param messageId: Unique identifier of the message [ebMSS 3.1.6.1]
   :param timestamp: Date/time of the message header creation expressed as UTC [ebMSS 3.1.6.2]
   :throws SOAPException: Description of the Exception
   :return: the newly added \ ``MessageHeader``\

addMessageHeader
^^^^^^^^^^^^^^^^

.. java:method:: public MessageHeader addMessageHeader() throws SOAPException
   :outertype: EbxmlMessage

   Adds a default \ ``MessageHeader``\  to this \ ``EbxmlMessage``\ .

   :throws SOAPException:
   :return: the newly added \ ``MessageHeader``\

addMessageOrder
^^^^^^^^^^^^^^^

.. java:method:: public void addMessageOrder(int status, int sequenceNumber) throws SOAPException
   :outertype: EbxmlMessage

   Add a MessageOrder element to the header.

   :param status: Status of the sequence number. It should have the value of either MessageOrder.STATUS_RESET or MessageOrder.STATUS_CONTINUE.
   :param sequenceNumber: Sequence number to be assigned to this message.
   :throws SOAPException: Description of the Exception

addPayloadContainer
^^^^^^^^^^^^^^^^^^^

.. java:method:: public PayloadContainer addPayloadContainer(DataHandler dataHandler, String contentId, String description) throws SOAPException
   :outertype: EbxmlMessage

   Add an ebXML message payload container.

   :param dataHandler: the \ ``DataHandler``\  that generates the payload content.
   :param contentId: the contentId of this payload attachment. The contentId must be unique among all payload attachment.
   :param description: the description of this payload.
   :throws SOAPException:
   :return: the \ ``PayloadContainer``\  object that is created and added.

addStatusRequest
^^^^^^^^^^^^^^^^

.. java:method:: public void addStatusRequest(String refToMessageId) throws SOAPException
   :outertype: EbxmlMessage

   Add a status request element to the message.

   :param refToMessageId: Identifier of the message it is referring to.
   :throws SOAPException:

addStatusResponse
^^^^^^^^^^^^^^^^^

.. java:method:: public void addStatusResponse(String refToMessageId, String messageStatus) throws SOAPException
   :outertype: EbxmlMessage

   Add a status response element to the message.

   :param refToMessageId: Identifier of the message it is referring to.
   :param messageStatus: Status string to be added in the response element.
   :throws SOAPException:

addStatusResponse
^^^^^^^^^^^^^^^^^

.. java:method:: public void addStatusResponse(String refToMessageId, String messageStatus, String timestamp) throws SOAPException
   :outertype: EbxmlMessage

   Add a status response element to the message.

   :param refToMessageId: Identifier of the message it is referring to.
   :param messageStatus: Status string to be added in the response element.
   :param timestamp: Timestamp of the status response expressed in UTC format.
   :throws SOAPException:

addSyncReply
^^^^^^^^^^^^

.. java:method:: public void addSyncReply() throws SOAPException
   :outertype: EbxmlMessage

   Add a SyncReply element to the message.

   :throws SOAPException:

getAckRequested
^^^^^^^^^^^^^^^

.. java:method:: public AckRequested getAckRequested()
   :outertype: EbxmlMessage

   Get acknowledgement request element.

   :return: \ ``AckRequested``\  object representing the element.

getAcknowledgment
^^^^^^^^^^^^^^^^^

.. java:method:: public Acknowledgment getAcknowledgment()
   :outertype: EbxmlMessage

   Get acknowledgement element.

   :return: \ ``Acknowledgement``\  object representing the element.

getAction
^^^^^^^^^

.. java:method:: public String getAction()
   :outertype: EbxmlMessage

   Gets action name

   :return: Action name

getBytes
^^^^^^^^

.. java:method:: public byte[] getBytes()
   :outertype: EbxmlMessage

   :return: Returns the bytestream.

getConversationId
^^^^^^^^^^^^^^^^^

.. java:method:: public String getConversationId()
   :outertype: EbxmlMessage

   Gets conversationId

   :return: Conversation ID

getCpaId
^^^^^^^^

.. java:method:: public String getCpaId()
   :outertype: EbxmlMessage

   Gets cpaId

   :return: CPA ID

getDatasource
^^^^^^^^^^^^^

.. java:method:: public DataSource getDatasource()
   :outertype: EbxmlMessage

   :return: Returns the datasource.

getDuplicateElimination
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean getDuplicateElimination()
   :outertype: EbxmlMessage

   Gets the flag stating if duplicate elimination is enabled or not.

   :return: true if duplicate elimination is required; false otherwise.

getErrorList
^^^^^^^^^^^^

.. java:method:: public ErrorList getErrorList()
   :outertype: EbxmlMessage

   Get the error list in the message.

   :return: \ ``ErrorList``\  object containing error list in the message. Returns null if it does not exist.

getFileName
^^^^^^^^^^^

.. java:method:: public String getFileName()
   :outertype: EbxmlMessage

   Gets the fileName attribute of the EbxmlMessage object. This function will only be used by the Hermes Server itself, and it is not expected for the client to call it.

   :return: The fileName value

getFromPartyIds
^^^^^^^^^^^^^^^

.. java:method:: public Iterator getFromPartyIds()
   :outertype: EbxmlMessage

   Gets the list of from party IDs. There can be multiple party IDs [ebMSS 3.1.1].

   :return: Iterator pointing to a list of party IDs.

getHeaderContainer
^^^^^^^^^^^^^^^^^^

.. java:method:: public HeaderContainer getHeaderContainer()
   :outertype: EbxmlMessage

   :return: Returns the headerContainer.

getManifest
^^^^^^^^^^^

.. java:method:: public Manifest getManifest()
   :outertype: EbxmlMessage

   Gets the Manifest element in this ebXML message

   :return: Manifest element

getMessageFromDataSource
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static Object getMessageFromDataSource(DataSource dataSource, boolean withAttachments) throws SOAPException, IOException
   :outertype: EbxmlMessage

getMessageHeader
^^^^^^^^^^^^^^^^

.. java:method:: public MessageHeader getMessageHeader()
   :outertype: EbxmlMessage

   Get the message header of this ebXML message.

   :return: \ ``MessageHeader``\  of this ebXML message.

getMessageId
^^^^^^^^^^^^

.. java:method:: public String getMessageId()
   :outertype: EbxmlMessage

   Gets messageId

   :return: Unique message identifier

getMessageOrder
^^^^^^^^^^^^^^^

.. java:method:: public MessageOrder getMessageOrder()
   :outertype: EbxmlMessage

   Get the message order element in the message.

   :return: \ ``MessageOrder``\  object if it exists in the ebXML message; null otherwise.

getMimeHeaders
^^^^^^^^^^^^^^

.. java:method:: public Map getMimeHeaders() throws IOException, SOAPException
   :outertype: EbxmlMessage

   Gets the MIME headers of this ebXML message

   :throws IOException: Description of the Exception
   :throws SOAPException: Description of the Exception
   :return: the MIME headers of this ebXML message

getMimeHeaders
^^^^^^^^^^^^^^

.. java:method:: public Map getMimeHeaders(String soapEncoding, String payloadEncoding) throws IOException, SOAPException
   :outertype: EbxmlMessage

   Gets the MIME headers of this ebXML message

   :param soapEncoding: content transfer encoding to be applied to SOAP part when computing length
   :param payloadEncoding: content transfer encoding to be applied to payload when computing length
   :throws IOException: Description of the Exception
   :throws SOAPException: Description of the Exception
   :return: the MIME headers of this ebXML message

getPayloadContainer
^^^^^^^^^^^^^^^^^^^

.. java:method:: public PayloadContainer getPayloadContainer(String contentId)
   :outertype: EbxmlMessage

   Gets the payload that is identified by the given content ID.

   :param contentId: Content ID of the payload to be retrieved.
   :return: \ ``PayloadContainer``\  of the given content ID or \ ``null``\  if no such \ ``PayloadContainer``\  exists

getPayloadContainers
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public Iterator getPayloadContainers()
   :outertype: EbxmlMessage

   Gets all \ ``PayloadContainer``\ s' attached in this \ ``EbxmlMessage``\  object.

   :return: An iterator point to a list of payload containers.

getPayloadCount
^^^^^^^^^^^^^^^

.. java:method:: public int getPayloadCount()
   :outertype: EbxmlMessage

   Gets the number of payloads in this ebXML message

   :return: the number of payloads

getPayloadInError
^^^^^^^^^^^^^^^^^

.. java:method:: public String getPayloadInError()
   :outertype: EbxmlMessage

   Checks whether the number of payloads in the SOAP message matches with the Manifest element in the header or not, and return the Content-ID of the inconsistent payload.

   :return: content-id of the inconsistent payload; null if all payloads are consistent.

getPersistenceHandler
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public Object getPersistenceHandler()
   :outertype: EbxmlMessage

   get the persistence handler if it is stored. This function will only be used by the Hermes Server itself, and it is not expected for the client to call it.

   :return: the persistence handler

getPersistenceName
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getPersistenceName()
   :outertype: EbxmlMessage

   get the Persistence name if it is stored. This function will only be used by the Hermes Server itself, and it is not expected for the client to call it.

   :return: the persitence name

getSOAPMessage
^^^^^^^^^^^^^^

.. java:method:: public SOAPMessage getSOAPMessage()
   :outertype: EbxmlMessage

   Gets the \ ``SOAPMessage``\  encapsulated in this \ ``EbxmlMessage``\ .

   :return: \ ``SOAPMessage``\  representing this \ ``EbxmlMessage``\

getService
^^^^^^^^^^

.. java:method:: public String getService()
   :outertype: EbxmlMessage

   Gets service name

   :return: Service name.

getServiceType
^^^^^^^^^^^^^^

.. java:method:: public String getServiceType()
   :outertype: EbxmlMessage

   Gets service type

   :return: Service type.

getSignatures
^^^^^^^^^^^^^

.. java:method:: public Iterator getSignatures()
   :outertype: EbxmlMessage

   Get the digital signatures in the message.

   :return: Iterator of \ ``Signature``\  objects in the message.

getSoapEnvelopeBytes
^^^^^^^^^^^^^^^^^^^^

.. java:method::  byte[] getSoapEnvelopeBytes()
   :outertype: EbxmlMessage

   Get the soap envelope in bytes. This function will only be used by the Hermes Server itself, and it is not expected for the client to call it.

getSoapEnvelopeBytesFromStream
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static byte[] getSoapEnvelopeBytesFromStream(InputStream stream) throws SOAPException
   :outertype: EbxmlMessage

   parse the message from InputStream and get the byte array of SOAP Envelope

   :param stream: the InputStream contains the message
   :throws MessageServerException: throw if there is error on parsing
   :return: the byte array of the Soap Envelope

getStatusRequest
^^^^^^^^^^^^^^^^

.. java:method:: public StatusRequest getStatusRequest()
   :outertype: EbxmlMessage

   Get the status request element in the message.

   :return: Content of the status request element stored in \ ``StatusRequest``\  object.

getStatusResponse
^^^^^^^^^^^^^^^^^

.. java:method:: public StatusResponse getStatusResponse()
   :outertype: EbxmlMessage

   Get the status response element in the message.

   :return: Content of the status response element stored in \ ``StatusResponse``\  object.

getSyncReply
^^^^^^^^^^^^

.. java:method:: public boolean getSyncReply()
   :outertype: EbxmlMessage

   Gets the flag stating if sync reply is enabled or not.

   :return: true if sync reply is enabled; false otherwise.

getTimeToLive
^^^^^^^^^^^^^

.. java:method:: public String getTimeToLive()
   :outertype: EbxmlMessage

   Gets TimeToLive of the message

   :return: TimeToLive expressed in UTC format.

getTimestamp
^^^^^^^^^^^^

.. java:method:: public String getTimestamp()
   :outertype: EbxmlMessage

   Gets timestamp

   :return: Timestamp of the message expressed in UTC format.

getToPartyIds
^^^^^^^^^^^^^

.. java:method:: public Iterator getToPartyIds()
   :outertype: EbxmlMessage

   Gets the list of to party IDs. There can be multiple party IDs [ebMSS 3.1.1].

   :return: Iterator pointing to a list of party IDs.

saveChanges
^^^^^^^^^^^

.. java:method:: public void saveChanges() throws SOAPException
   :outertype: EbxmlMessage

   Updates the encapsulated \ ``SOAPMessage``\  with all changes that have been made to it.

   :throws SOAPException:

   **See also:** :java:ref:`javax.xml.soap.SOAPMessage.saveChanges()`

saveRequired
^^^^^^^^^^^^

.. java:method:: public boolean saveRequired()
   :outertype: EbxmlMessage

   Indicates whether the encapsulated \ ``SOAPMessage``\  need to be updated by calling \ ``saveChanges``\  on it.

   :return: true if it is required to call saveChanges on the message; false otherwise.

   **See also:** :java:ref:`javax.xml.soap.SOAPMessage.saveRequired()`

setBytes
^^^^^^^^

.. java:method:: public void setBytes(byte[] bytes)
   :outertype: EbxmlMessage

   :param bytes: The bytestream to set.

setFileName
^^^^^^^^^^^

.. java:method:: public void setFileName(String filename)
   :outertype: EbxmlMessage

   Sets the fileName attribute of the EbxmlMessage object. This function will only be used by the Hermes Server itself, and it is not expected for the client to call it.

   :param filename: The new fileName value

setPayloadContainers
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public ArrayList setPayloadContainers(ArrayList payloads)
   :outertype: EbxmlMessage

   Sets the \ ``PayloadContainer``\

   :param payloads: The new payloadContainers value
   :return: The old payload container as an array list

setPersistenceInfo
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setPersistenceInfo(String persistenceName, Object handler, DataSource datasource)
   :outertype: EbxmlMessage

   set the persistence info to the message This function will only be used by the Hermes Server itself, and it is not expected for the client to call it.

   :param persistenceName: the name on the persistence handler
   :param handler: the persistence handler

setSoapEnvelopeBytes
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setSoapEnvelopeBytes(byte[] soapEnvelopeBytes)
   :outertype: EbxmlMessage

   set the soap envelope in bytes. Those bytes will be used to verify This function will only be used by the Hermes Server itself, and it is not expected for the client to call it. the signature.

writeTo
^^^^^^^

.. java:method:: public void writeTo(OutputStream out) throws IOException, SOAPException
   :outertype: EbxmlMessage

   Writes the encapsulated \ ``SOAPMessage``\  to the given output stream. The externalization format is as defined by the SOAP 1.1 with Attachments Specification.

   :param out: \ ``OutputStream``\  to write the message to.
   :throws IOException: Description of the Exception
   :throws SOAPException: Description of the Exception

writeTo
^^^^^^^

.. java:method:: public void writeTo(OutputStream out, String soapEncoding, String payloadEncoding) throws IOException, SOAPException
   :outertype: EbxmlMessage

   Writes the encapsulated \ ``SOAPMessage``\  to the given output stream. The externalization format is as defined by the SOAP 1.1 with Attachments Specification.

   :param out: \ ``OutputStream``\  to write the message to.
   :param soapEncoding: Description of the Parameter
   :param payloadEncoding: Description of the Parameter
   :throws IOException: Description of the Exception
   :throws SOAPException: Description of the Exception

