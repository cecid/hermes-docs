.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

AS2Response
===========

.. java:package:: hk.hku.cecid.edi.as2.listener
   :noindex:

.. java:type:: public class AS2Response

   The AS2Response class represents a SOAP response. It is independent of which transport protocol it is using and contains the SOAP message of the target response.

   :author: Hugo Y. K. Lam

Constructors
------------
AS2Response
^^^^^^^^^^^

.. java:constructor::  AS2Response()
   :outertype: AS2Response

   Creates a new instance of AS2Response.

AS2Response
^^^^^^^^^^^

.. java:constructor::  AS2Response(Object target)
   :outertype: AS2Response

   Creates a new instance of AS2Response.

   :param target: the target that this response should be committed to.

Methods
-------
getMessage
^^^^^^^^^^

.. java:method:: public AS2Message getMessage()
   :outertype: AS2Response

   Gets the SOAP message of this response.

   :return: the SOAP message of this response.

getTarget
^^^^^^^^^

.. java:method:: public Object getTarget()
   :outertype: AS2Response

   Gets the target that this response should be committed to.

   :return: the target that this response should be committed to.

setMessage
^^^^^^^^^^

.. java:method:: public void setMessage(AS2Message message)
   :outertype: AS2Response

   Sets the SOAP message of this response.

   :param message: the SOAP message of this response.

setTarget
^^^^^^^^^

.. java:method::  void setTarget(Object target)
   :outertype: AS2Response

   Sets the target that this response should be committed to.

   :param target: the target that this response should be committed to.

