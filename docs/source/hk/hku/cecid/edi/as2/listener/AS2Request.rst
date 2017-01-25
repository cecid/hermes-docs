.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

AS2Request
==========

.. java:package:: hk.hku.cecid.edi.as2.listener
   :noindex:

.. java:type:: public class AS2Request

   The AS2Request class represents a SOAP request. It is independent of which transport protocol it is using and contains the SOAP message of the original request.

   :author: Hugo Y. K. Lam

Constructors
------------
AS2Request
^^^^^^^^^^

.. java:constructor::  AS2Request()
   :outertype: AS2Request

   Creates a new instance of AS2Request.

AS2Request
^^^^^^^^^^

.. java:constructor::  AS2Request(Object source)
   :outertype: AS2Request

   Creates a new instance of AS2Request.

   :param source: the source which initiated this request.

Methods
-------
getMessage
^^^^^^^^^^

.. java:method:: public AS2Message getMessage()
   :outertype: AS2Request

   Gets the SOAP message of this request.

   :return: the SOAP message of this request.

getSource
^^^^^^^^^

.. java:method:: public Object getSource()
   :outertype: AS2Request

   Gets the source which initiated this request.

   :return: the source which initiated this request.

setMessage
^^^^^^^^^^

.. java:method::  void setMessage(AS2Message message)
   :outertype: AS2Request

   Sets the SOAP message of this request.

   :param message: the SOAP message of this request.

setSource
^^^^^^^^^

.. java:method::  void setSource(Object source)
   :outertype: AS2Request

   Sets the source which initiated this request.

   :param source: the source which initiated this request.

