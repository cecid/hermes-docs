.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: javax.xml.soap MessageFactory

.. java:import:: javax.xml.soap MimeHeaders

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPMessage

EbxmlMessageFactory
===================

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class EbxmlMessageFactory extends MessageFactory

   Implementation of \ ``javax.xml.soap.MessageFactory``\

   :author: cyng

Constructors
------------
EbxmlMessageFactory
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EbxmlMessageFactory()
   :outertype: EbxmlMessageFactory

   Initializes EbxmlMessageFactory object.

Methods
-------
createEbxmlMessage
^^^^^^^^^^^^^^^^^^

.. java:method:: public EbxmlMessage createEbxmlMessage() throws SOAPException
   :outertype: EbxmlMessageFactory

   Create a simple ebXML message.

   :throws SOAPException:
   :return: A new ebXML message.

createEbxmlMessage
^^^^^^^^^^^^^^^^^^

.. java:method:: public EbxmlMessage createEbxmlMessage(MimeHeaders headers, InputStream in) throws IOException, SOAPException
   :outertype: EbxmlMessageFactory

   Create an ebXML message with given MIME headers and content in form of input stream.

   :param headers: MIME headers to be used in the new message.
   :param in: Content of ebXML message in the form of input stream.
   :throws IOException:
   :throws SOAPException:
   :return: \ ``EbxmlMessage``\  created.

createMessage
^^^^^^^^^^^^^

.. java:method:: public SOAPMessage createMessage() throws SOAPException
   :outertype: EbxmlMessageFactory

   Creates a simple ebXML SOAP message.

   :throws SOAPException:
   :return: \ ``SOAPMessage``\  of the ebXML message created.

createMessage
^^^^^^^^^^^^^

.. java:method:: public SOAPMessage createMessage(MimeHeaders headers, InputStream in) throws IOException, SOAPException
   :outertype: EbxmlMessageFactory

   Creates an ebXML SOAP message using given MIME headers and content in form of input stream.

   :param headers: MIME headers to be used in the new message.
   :param in: Content of ebXML message in the form of input stream.
   :throws IOException:
   :throws SOAPException:
   :return: \ ``SOAPMessage``\  of the ebXML message created.

