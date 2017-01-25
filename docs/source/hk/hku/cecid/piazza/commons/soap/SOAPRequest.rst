.. java:import:: javax.xml.soap MimeHeaders

.. java:import:: javax.xml.soap SOAPMessage

SOAPRequest
===========

.. java:package:: hk.hku.cecid.piazza.commons.soap
   :noindex:

.. java:type:: public class SOAPRequest

   The SOAPRequest class represents a SOAP request. It is independent of which transport protocol it is using and contains the SOAP message of the original request.

   :author: Hugo Y. K. Lam

Constructors
------------
SOAPRequest
^^^^^^^^^^^

.. java:constructor::  SOAPRequest()
   :outertype: SOAPRequest

   Creates a new instance of SOAPRequest.

SOAPRequest
^^^^^^^^^^^

.. java:constructor::  SOAPRequest(Object source)
   :outertype: SOAPRequest

   Creates a new instance of SOAPRequest.

   :param source: the source which initiated this request.

Methods
-------
getBytes
^^^^^^^^

.. java:method:: public byte[] getBytes()
   :outertype: SOAPRequest

   Gets the SOAP message as bytes.

   :return: the byte array of the SOAP message.

getHeaders
^^^^^^^^^^

.. java:method:: public MimeHeaders getHeaders()
   :outertype: SOAPRequest

   Gets the mime headers of the request.

   :return: the mime headers of the request.

getMessage
^^^^^^^^^^

.. java:method:: public SOAPMessage getMessage()
   :outertype: SOAPRequest

   Gets the SOAP message of this request.

   :return: the SOAP message of this request.

getSource
^^^^^^^^^

.. java:method:: public Object getSource()
   :outertype: SOAPRequest

   Gets the source which initiated this request.

   :return: the source which initiated this request.

setBytes
^^^^^^^^

.. java:method::  void setBytes(byte[] bs)
   :outertype: SOAPRequest

   Sets the bytes of the SOAP message.

   :param bs: the byte array of the SOAP message.

setHeaders
^^^^^^^^^^

.. java:method::  void setHeaders(MimeHeaders headers)
   :outertype: SOAPRequest

   Sets the mime headers of the request.

   :param headers: the mime headers of the request.

setMessage
^^^^^^^^^^

.. java:method::  void setMessage(SOAPMessage message)
   :outertype: SOAPRequest

   Sets the SOAP message of this request.

   :param message: the SOAP message of this request.

setSource
^^^^^^^^^

.. java:method::  void setSource(Object source)
   :outertype: SOAPRequest

   Sets the source which initiated this request.

   :param source: the source which initiated this request.

