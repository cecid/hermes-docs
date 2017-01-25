.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

AckRequested
============

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class AckRequested extends HeaderElement

   An ebXML \ ``AckRequested``\  in the SOAP Header of a \ ``HeaderContainer``\  [ebMSS 6.3.1].

   :author: cyng

Fields
------
ACK_REQUESTED
^^^^^^^^^^^^^

.. java:field:: static final String ACK_REQUESTED
   :outertype: AckRequested

   \ ``AckRequested``\  element name.

ATTRIBUTE_SIGNED
^^^^^^^^^^^^^^^^

.. java:field:: static final String ATTRIBUTE_SIGNED
   :outertype: AckRequested

   Name of the Signed attribute.

Constructors
------------
AckRequested
^^^^^^^^^^^^

.. java:constructor::  AckRequested(SOAPEnvelope soapEnvelope, boolean signed) throws SOAPException
   :outertype: AckRequested

   Constructs a \ ``AckRequested``\  with the given mandatory fields.

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header of which the \ ``AckRequested``\  element is added to.
   :param signed: Indicates if a signed acknowledgement response is requested. True if a signed response is requested; false otherwise.
   :throws SOAPException:

AckRequested
^^^^^^^^^^^^

.. java:constructor::  AckRequested(SOAPEnvelope soapEnvelope, SOAPElement soapElement) throws SOAPException
   :outertype: AckRequested

   Constructs a \ ``AckRequested``\  with the given mandatory fields.

   :param soapEnvelope: \ ``SOAPEnvelope``\ , the header of which the \ ``AckRequested``\  element is added to.
   :param soapElement: \ ``SOAPElement``\  containing acknowledgement request.
   :throws SOAPException:

Methods
-------
getSigned
^^^^^^^^^

.. java:method:: public boolean getSigned()
   :outertype: AckRequested

   Gets the flag that if a signed acknowledgement response is requested.

   :return: true if a signed acknowledgement response is requested; false otherwise.

