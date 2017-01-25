.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.security SMimeMessage

.. java:import:: hk.hku.cecid.piazza.commons.util Generator

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: java.io BufferedInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: java.net InetAddress

.. java:import:: java.util Date

.. java:import:: java.util Enumeration

.. java:import:: javax.mail MessagingException

.. java:import:: javax.mail.internet InternetHeaders

.. java:import:: javax.mail.internet MimeBodyPart

AS2Message
==========

.. java:package:: hk.hku.cecid.edi.as2.pkg
   :noindex:

.. java:type:: public class AS2Message

   AS2Message represents an AS2 message.

   :author: Hugo Y. K. Lam

Constructors
------------
AS2Message
^^^^^^^^^^

.. java:constructor:: public AS2Message()
   :outertype: AS2Message

   Creates a new instance of AS2Message.

AS2Message
^^^^^^^^^^

.. java:constructor:: public AS2Message(InputStream message) throws AS2MessageException
   :outertype: AS2Message

   Creates a new instance of AS2Message.

   :param message: the message as input stream.
   :throws AS2MessageException: if unable to construct from the given input stream.

AS2Message
^^^^^^^^^^

.. java:constructor:: public AS2Message(InternetHeaders headers, InputStream content) throws AS2MessageException
   :outertype: AS2Message

   Creates a new instance of AS2Message.

   :param headers: the headers of this message.
   :param content: the content stream.
   :throws AS2MessageException: if unable to construct from the given content stream.

Methods
-------
addHeader
^^^^^^^^^

.. java:method:: public void addHeader(String name, String value)
   :outertype: AS2Message

   Adds a message header of the specified name.

   :param name: the header name.
   :param value: the header value.

generateID
^^^^^^^^^^

.. java:method:: public static String generateID()
   :outertype: AS2Message

   Generates a new AS2 message ID.

   :return: a new AS2 message ID.

getBodyPart
^^^^^^^^^^^

.. java:method:: public MimeBodyPart getBodyPart()
   :outertype: AS2Message

   Gets the MIME body part of this message.

   :return: the MIME body part.

getContent
^^^^^^^^^^

.. java:method:: public Object getContent() throws AS2MessageException
   :outertype: AS2Message

   Gets the content of this message.

   :throws AS2MessageException: if unable to get the content.
   :return: the content part.

getContentStream
^^^^^^^^^^^^^^^^

.. java:method:: public InputStream getContentStream() throws AS2MessageException
   :outertype: AS2Message

   Gets the content stream of this message.

   :throws AS2MessageException: if unable to retrieve the stream.
   :return: the content stream of this message.

getContentType
^^^^^^^^^^^^^^

.. java:method:: public String getContentType() throws AS2MessageException
   :outertype: AS2Message

   Gets the content type.

   :throws AS2MessageException: if unable to get the content type.
   :return: the content type.

getDispositionNotification
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public DispositionNotification getDispositionNotification() throws AS2MessageException
   :outertype: AS2Message

   Gets the MDN of this message.

   :throws AS2MessageException: if unable to construct the MDN.
   :return: the MDN.

getDispositionNotificationOptions
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public DispositionNotificationOptions getDispositionNotificationOptions()
   :outertype: AS2Message

   Gets the disposition notification options.

   :return: the disposition notification options.

getFromPartyID
^^^^^^^^^^^^^^

.. java:method:: public String getFromPartyID()
   :outertype: AS2Message

   Gets the "from" party ID.

   :return: the "from" party ID.

getHeader
^^^^^^^^^

.. java:method:: public String getHeader(String name)
   :outertype: AS2Message

   Gets a message header of the specified name.

   :param name: the header name.
   :return: the header value.

getHeader
^^^^^^^^^

.. java:method:: public String getHeader(String name, String def)
   :outertype: AS2Message

   Gets a message header of the specified name.

   :param name: the header name.
   :param def: the default value.
   :return: the header value.

getHeaders
^^^^^^^^^^

.. java:method:: public InternetHeaders getHeaders()
   :outertype: AS2Message

   Gets the headers of this message.

   :return: a copy of the headers of this message.

getInputStream
^^^^^^^^^^^^^^

.. java:method:: public InputStream getInputStream() throws AS2MessageException
   :outertype: AS2Message

   Gets the input stream of this message's content. Any transfer encodings will be decoded before the input stream is provided.

   :throws AS2MessageException: if unable to retrieve the stream.
   :return: the input stream of this message's content.

getMessageID
^^^^^^^^^^^^

.. java:method:: public String getMessageID()
   :outertype: AS2Message

   Gets the message ID.

   :return: the message ID.

getToPartyID
^^^^^^^^^^^^

.. java:method:: public String getToPartyID()
   :outertype: AS2Message

   Gets the "to" party ID.

   :return: the "to" party ID.

isDispositionNotification
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isDispositionNotification()
   :outertype: AS2Message

   Checks if this message is an MDN.

   :return: true if this message is an MDN.

isReceiptRequested
^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isReceiptRequested()
   :outertype: AS2Message

   Checks if receipt of message is requested.

   :return: true if receipt of message is requested.

isReceiptSynchronous
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isReceiptSynchronous()
   :outertype: AS2Message

   Checks if the receipt of message should be sent synchronously.

   :return: true if the receipt of message should be sent synchronously.

removeHeader
^^^^^^^^^^^^

.. java:method:: public void removeHeader(String name)
   :outertype: AS2Message

   Removes a message header of the specified name.

   :param name: the header name.

reply
^^^^^

.. java:method:: public AS2Message reply() throws AS2MessageException
   :outertype: AS2Message

   Replies this message.

   :throws AS2MessageException: if unable to construct the message.
   :return: the reply message.

requestReceipt
^^^^^^^^^^^^^^

.. java:method:: public void requestReceipt(String returnUrl, String micAlg)
   :outertype: AS2Message

setBodyPart
^^^^^^^^^^^

.. java:method:: public void setBodyPart(MimeBodyPart bp)
   :outertype: AS2Message

   Sets the MIME body part of this message.

setContent
^^^^^^^^^^

.. java:method:: public void setContent(Object content, String contentType) throws AS2MessageException
   :outertype: AS2Message

   Sets a content to this message.

   :param content: the content part.
   :param contentType: the content type.
   :throws AS2MessageException: if unable to set the content.

setFromPartyID
^^^^^^^^^^^^^^

.. java:method:: public void setFromPartyID(String id)
   :outertype: AS2Message

setHeader
^^^^^^^^^

.. java:method:: public void setHeader(String name, String value)
   :outertype: AS2Message

   Sets a message header of the specified name.

   :param name: the header name.
   :param value: the header value.

setMessageID
^^^^^^^^^^^^

.. java:method:: public void setMessageID(String id)
   :outertype: AS2Message

setToPartyID
^^^^^^^^^^^^

.. java:method:: public void setToPartyID(String id)
   :outertype: AS2Message

toByteArray
^^^^^^^^^^^

.. java:method:: public byte[] toByteArray() throws AS2MessageException
   :outertype: AS2Message

   Returns a byte array which represents this message.

   :throws AS2MessageException: if unable to convert this message into bytes.
   :return: a byte array which represents this message.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: AS2Message

   Returns a string representation of this message.

   :return: a string representation of this message.

   **See also:** :java:ref:`java.lang.Object.toString()`

writeTo
^^^^^^^

.. java:method:: public void writeTo(OutputStream outs) throws AS2MessageException
   :outertype: AS2Message

   Writes the message to the given output stream.

   :param outs: the output stream to be written.
   :throws AS2MessageException: if unable to write the message.

