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

MessageHeader
=============

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class MessageHeader extends HeaderElement

   An ebXML \ ``MessageHeader``\  in the SOAP Header of a \ ``HeaderContainer``\

   :author: cyng

Fields
------
ATTRIBUTE_TYPE
^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_TYPE
   :outertype: MessageHeader

   \ ``MessageHeader``\  Type attribute name

ELEMENT_ACTION
^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_ACTION
   :outertype: MessageHeader

   \ ``MessageHeader``\  Action element name

ELEMENT_CONVERSATION_ID
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_CONVERSATION_ID
   :outertype: MessageHeader

   \ ``MessageHeader``\  ConversationID element name

ELEMENT_CPA_ID
^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_CPA_ID
   :outertype: MessageHeader

   \ ``MessageHeader``\  CPAID element name

ELEMENT_DUPLICATE_ELIMINATION
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_DUPLICATE_ELIMINATION
   :outertype: MessageHeader

   \ ``MessageHeader``\  DuplicateElimination element name

ELEMENT_FROM
^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_FROM
   :outertype: MessageHeader

   \ ``MessageHeader``\  From element name

ELEMENT_MESSAGE_DATA
^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_MESSAGE_DATA
   :outertype: MessageHeader

   \ ``MessageHeader``\  MessageData element name

ELEMENT_MESSAGE_ID
^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_MESSAGE_ID
   :outertype: MessageHeader

   \ ``MessageHeader``\  MessageId element name

ELEMENT_PARTY_ID
^^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_PARTY_ID
   :outertype: MessageHeader

   \ ``MessageHeader``\  PartyID element name

ELEMENT_REF_TO_MESSAGE_ID
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_REF_TO_MESSAGE_ID
   :outertype: MessageHeader

   \ ``MessageHeader``\  RefToMessageID element name

ELEMENT_ROLE
^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_ROLE
   :outertype: MessageHeader

   \ ``MessageHeader``\  Role element name

ELEMENT_SERVICE
^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_SERVICE
   :outertype: MessageHeader

   \ ``MessageHeader``\  Service element name

ELEMENT_TIMESTAMP
^^^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_TIMESTAMP
   :outertype: MessageHeader

   \ ``MessageHeader``\  Timestamp element name

ELEMENT_TIME_TO_LIVE
^^^^^^^^^^^^^^^^^^^^

.. java:field:: static final String ELEMENT_TIME_TO_LIVE
   :outertype: MessageHeader

   \ ``MessageHeader``\  TimeToLive element name

ELEMENT_TO
^^^^^^^^^^

.. java:field:: static final String ELEMENT_TO
   :outertype: MessageHeader

   \ ``MessageHeader``\  To element name

MESSAGE_HEADER
^^^^^^^^^^^^^^

.. java:field:: static final String MESSAGE_HEADER
   :outertype: MessageHeader

   \ ``MessageHeader``\  element name

TIME_ZONE
^^^^^^^^^

.. java:field:: static final String TIME_ZONE
   :outertype: MessageHeader

   Standard time zone used in Message Service Handler

Constructors
------------
MessageHeader
^^^^^^^^^^^^^

.. java:constructor::  MessageHeader(SOAPEnvelope soapEnvelope) throws SOAPException
   :outertype: MessageHeader

   Initializes data structures in \ ``MessageHeader``\  object using the given \ ``SOAPEnvelope``\ .

   :param soapEnvelope: \ ``SOAPEnvelope``\  into which the \ ``MessageHeader``\  is added.
   :throws SOAPException:

MessageHeader
^^^^^^^^^^^^^

.. java:constructor::  MessageHeader(SOAPEnvelope soapEnvelope, String fromPartyId, String fromPartyIdType, String toPartyId, String toPartyIdType, String cpaId, String conversationId, String service, String action, String messageId, String timestamp) throws SOAPException
   :outertype: MessageHeader

   Constructs a \ ``MessageHeader``\  with the given mandatory fields. No further modification on the fields specified are allowed.

   :param soapEnvelope: \ ``SOAPEnvelope``\  into which the \ ``MessageHeader``\  is added.
   :param fromPartyId: PartyID of the sender.
   :param fromPartyIdType: PartyID type of the sender.
   :param toPartyId: PartyID of the recipient.
   :param toPartyIdType: PartyID type of the recipient.
   :param cpaId: CPA ID.
   :param conversationId: Conversation ID of the message.
   :param service: Service name.
   :param action: Action name.
   :param messageId: Unique message identifier.
   :param timestamp: Timestamp of the message header creation.
   :throws SOAPException:

MessageHeader
^^^^^^^^^^^^^

.. java:constructor::  MessageHeader(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: MessageHeader

   Constructs a \ ``MessageHeader``\  with the given \ ``SOAPEnvelope``\  and \ ``SOAPElement``\ .

   :param soapEnvelope: \ ``SOAPEnvelope``\  into which the \ ``MessageHeader``\  is added.
   :param soapElement: \ ``SOAPElement``\  to be parsed and stored in the MessageHeader.
   :throws SOAPException:

Methods
-------
addDescription
^^^^^^^^^^^^^^

.. java:method:: public void addDescription(String description) throws SOAPException
   :outertype: MessageHeader

   Add  element with default \ ``xml:lang``\

   :param description: Description to be added to \ ``MessageHeader``\
   :throws SOAPException:

addDescription
^^^^^^^^^^^^^^

.. java:method:: public void addDescription(String description, String lang) throws SOAPException
   :outertype: MessageHeader

   Add  element with specified \ ``xml:lang``\ . This method can be called repeatedly to add several descriptions to the \ ``MessageHeader``\

   :param description: Description to be added to \ ``MessageHeader``\
   :param lang: Language of the description specified in \ ` RFC 1766 <http://www.ietf.org/rfc/rfc1766.txt>`_\  and ISO639.
   :throws SOAPException:

addFromPartyId
^^^^^^^^^^^^^^

.. java:method:: public void addFromPartyId(String id) throws SOAPException
   :outertype: MessageHeader

   Add sender's PartyID into \ ``MessageHeader``\

   :param id: Sender's PartyID string.
   :throws SOAPException:

addFromPartyId
^^^^^^^^^^^^^^

.. java:method:: public void addFromPartyId(String id, String type) throws SOAPException
   :outertype: MessageHeader

   Add sender's PartyID and its type into \ ``MessageHeader``\

   :param id: Sender's PartyID string.
   :param type: PartyID type.
   :throws SOAPException:

addToPartyId
^^^^^^^^^^^^

.. java:method:: public void addToPartyId(String id) throws SOAPException
   :outertype: MessageHeader

   Add recipient's PartyID into \ ``MessageHeader``\

   :param id: Recipient's PartyID string.
   :throws SOAPException:

addToPartyId
^^^^^^^^^^^^

.. java:method:: public void addToPartyId(String id, String type) throws SOAPException
   :outertype: MessageHeader

   Add recipient's PartyID and its type into \ ``MessageHeader``\

   :param id: Recipient's PartyID string.
   :param type: PartyID type.
   :throws SOAPException:

getAction
^^^^^^^^^

.. java:method:: public String getAction()
   :outertype: MessageHeader

   Get action name.

   :return: Action name.

getConversationId
^^^^^^^^^^^^^^^^^

.. java:method:: public String getConversationId()
   :outertype: MessageHeader

   Get conversationId

   :return: Conversation ID of the message.

getCpaId
^^^^^^^^

.. java:method:: public String getCpaId()
   :outertype: MessageHeader

   Get cpaId.

   :return: Collaborative Protocol Agreement ID.

getDescriptionCount
^^^^^^^^^^^^^^^^^^^

.. java:method:: public int getDescriptionCount()
   :outertype: MessageHeader

   Gets the number of \ ``Description``\  elements in this \ ``MessageHeader``\ .

   :return: The number of \ ``Description``\  elements.

getDescriptions
^^^^^^^^^^^^^^^

.. java:method:: public Iterator getDescriptions()
   :outertype: MessageHeader

   Get all \ ``Description``\  elements in this \ ``MessageHeader``\ .

   :return: an \ ``Iterator``\  of \ ``Description``\ s'.

getDuplicateElimination
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean getDuplicateElimination()
   :outertype: MessageHeader

   Get current setting of duplication elimination.

   :return: true if duplicate elimination is enabled; false otherwise.

getFrom
^^^^^^^

.. java:method::  ExtensionElement getFrom()
   :outertype: MessageHeader

   Get From core extension element.

   :return: From extension element object.

getFromPartyIds
^^^^^^^^^^^^^^^

.. java:method:: public Iterator getFromPartyIds()
   :outertype: MessageHeader

   Get Sender's PartyId in header. It can have one or more occurrences.

   :return: Iterator pointing to a list of senders' Party IDs.

getFromRole
^^^^^^^^^^^

.. java:method:: public String getFromRole()
   :outertype: MessageHeader

   Get Role element in the From core extension element.

   :return: Role name.

getMessageData
^^^^^^^^^^^^^^

.. java:method::  ExtensionElement getMessageData()
   :outertype: MessageHeader

   Get MessageData core extension element.

   :return: MessageData \ ``ExtensionElement``\

getMessageId
^^^^^^^^^^^^

.. java:method:: public String getMessageId()
   :outertype: MessageHeader

   Get messageId.

   :return: Unique message identifier.

getRefToMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public String getRefToMessageId()
   :outertype: MessageHeader

   Get the unique identifier of the message this message refers to.

   :return: ID of the message being referred to.

getService
^^^^^^^^^^

.. java:method:: public String getService()
   :outertype: MessageHeader

   Get service name

   :return: Service name.

getServiceType
^^^^^^^^^^^^^^

.. java:method:: public String getServiceType()
   :outertype: MessageHeader

   Get the service type string.

   :return: Service type string.

getTimeToLive
^^^^^^^^^^^^^

.. java:method:: public String getTimeToLive()
   :outertype: MessageHeader

   Get TimeToLive

   :return: TimeToLive expressed in UTC format.

getTimestamp
^^^^^^^^^^^^

.. java:method:: public String getTimestamp()
   :outertype: MessageHeader

   Get header creation timestamp expressed in UTC format.

   :return: Timestamp expressed in UTC format.

getTo
^^^^^

.. java:method::  ExtensionElement getTo()
   :outertype: MessageHeader

   Get To core extension element.

   :return: To extension element object.

getToPartyIds
^^^^^^^^^^^^^

.. java:method:: public Iterator getToPartyIds()
   :outertype: MessageHeader

   Get recipient's PartyId in header. It can have one or more occurrences.

   :return: Iterator pointing to a list of recipients' Party IDs.

getToRole
^^^^^^^^^

.. java:method:: public String getToRole()
   :outertype: MessageHeader

   Get Role element in the To core extension element.

   :return: Role name.

setAction
^^^^^^^^^

.. java:method:: public void setAction(String action) throws SOAPException
   :outertype: MessageHeader

   Set action name. This property can be set only once.

   :param action: Action name.
   :throws SOAPException:

setConversationId
^^^^^^^^^^^^^^^^^

.. java:method:: public void setConversationId(String conversationId) throws SOAPException
   :outertype: MessageHeader

   Set conversationId. This property can be set only once.

   :param conversationId: Conversation ID of the message.
   :throws SOAPException:

setCpaId
^^^^^^^^

.. java:method:: public void setCpaId(String cpaId) throws SOAPException
   :outertype: MessageHeader

   Set cpaId of the message header. This property can be set only once.

   :param cpaId: Collaborative Protocol Agreement ID.
   :throws SOAPException:

setDuplicateElimination
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setDuplicateElimination() throws SOAPException
   :outertype: MessageHeader

   Enable duplication elimination function. This property can be set only once.

   :throws SOAPException:

setFromRole
^^^^^^^^^^^

.. java:method:: public void setFromRole(String role) throws SOAPException
   :outertype: MessageHeader

   Set Role element in the From core extension element.

   :param role: Role name.
   :throws SOAPException:

setMessageId
^^^^^^^^^^^^

.. java:method:: public void setMessageId(String messageId) throws SOAPException
   :outertype: MessageHeader

   Set messageId. This property can be set only once.

   :param messageId: Unique message identifier.
   :throws SOAPException:

setRefToMessageId
^^^^^^^^^^^^^^^^^

.. java:method:: public void setRefToMessageId(String messageId) throws SOAPException
   :outertype: MessageHeader

   Set optional "RefToMessageId" element. This property can be set only once.

   :param messageId: Message ID to be set in the current message header.
   :throws SOAPException:

setService
^^^^^^^^^^

.. java:method:: public void setService(String serviceName) throws SOAPException
   :outertype: MessageHeader

   Set service name. This property can be set only once.

   :param serviceName: Service name.
   :throws SOAPException:

setService
^^^^^^^^^^

.. java:method:: public void setService(String serviceName, String serviceType) throws SOAPException
   :outertype: MessageHeader

   Set service. This property can be set only once.

   :param serviceName: Service name.
   :param serviceType: Service type string.
   :throws SOAPException:

setServiceType
^^^^^^^^^^^^^^

.. java:method:: public void setServiceType(String type) throws SOAPException
   :outertype: MessageHeader

   Set optional "type" attribute in service element

   :throws SOAPException:

setTimeToLive
^^^^^^^^^^^^^

.. java:method:: public void setTimeToLive(String time) throws SOAPException
   :outertype: MessageHeader

   Set optional "TimeToLive" element. This property can be set only once.

   :param time: TimeToLive expressed in UTC format.
   :throws SOAPException:

setTimeToLive
^^^^^^^^^^^^^

.. java:method:: public void setTimeToLive(Date time) throws SOAPException
   :outertype: MessageHeader

   Convert local date/time to UTC string and set TimeToLive value. This property can be set only once.

   :param time: Local date/time to be converted to UTC format and set as TimeToLive value.
   :throws SOAPException:

setTimestamp
^^^^^^^^^^^^

.. java:method:: public void setTimestamp(String timestamp) throws SOAPException
   :outertype: MessageHeader

   Set timestamp.

   :param timestamp: Header creation timestamp expressed in UTC format.
   :throws SOAPException:

setToRole
^^^^^^^^^

.. java:method:: public void setToRole(String role) throws SOAPException
   :outertype: MessageHeader

   Set Role element in the To core extension element.

   :param role: Role name.
   :throws SOAPException:

