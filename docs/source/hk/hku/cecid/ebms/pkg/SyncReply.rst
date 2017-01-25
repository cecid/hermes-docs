.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

SyncReply
=========

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class SyncReply extends HeaderElement

   An ebXML \ ``SyncReply``\  in the SOAP Header of a \ ``HeaderContainer``\  [ebMSS 4.3].

   :author: tslam

Fields
------
SYNC_REPLY
^^^^^^^^^^

.. java:field:: static final String SYNC_REPLY
   :outertype: SyncReply

   \ ``SyncReply``\  element name

Constructors
------------
SyncReply
^^^^^^^^^

.. java:constructor::  SyncReply(SOAPEnvelope soapEnvelope) throws SOAPException
   :outertype: SyncReply

   Constructs a \ ``SyncReply``\  with the given mandatory fields.

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header container of which the \ ``SyncReply``\  is attached to.
   :throws SOAPException:

SyncReply
^^^^^^^^^

.. java:constructor::  SyncReply(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: SyncReply

   Constructs an \ ``SyncReply``\  object by parsing the given \ ``SOAPElement``\ .

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header container of which the \ ``SyncReply``\  is attached to.
   :param soapElement: Empty \ ``SOAPElement``\ .
   :throws SOAPException:

