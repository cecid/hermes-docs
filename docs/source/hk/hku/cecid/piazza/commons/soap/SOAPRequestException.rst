SOAPRequestException
====================

.. java:package:: hk.hku.cecid.piazza.commons.soap
   :noindex:

.. java:type:: public class SOAPRequestException extends hk.hku.cecid.piazza.commons.GenericException

   SOAPRequestException represents all kinds of exception related to a SOAP request or its process.

   :author: Hugo Y. K. Lam

Constructors
------------
SOAPRequestException
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SOAPRequestException()
   :outertype: SOAPRequestException

   Creates a new instance of SOAPRequestException.

SOAPRequestException
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SOAPRequestException(String message)
   :outertype: SOAPRequestException

   Creates a new instance of SOAPRequestException.

   :param message: the error message.

SOAPRequestException
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SOAPRequestException(Throwable cause)
   :outertype: SOAPRequestException

   Creates a new instance of SOAPRequestException.

   :param cause: the cause of this exception.

SOAPRequestException
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public SOAPRequestException(String message, Throwable cause)
   :outertype: SOAPRequestException

   Creates a new instance of SOAPRequestException.

   :param message: the error message.
   :param cause: the cause of this exception.

Methods
-------
getSOAPFault
^^^^^^^^^^^^

.. java:method:: public SOAPFaultException getSOAPFault()
   :outertype: SOAPRequestException

   Gets the SOAP fault exception which caused this exception.

   :return: the SOAP fault exception which caused this exception or null if there is none.

isSOAPFault
^^^^^^^^^^^

.. java:method:: public boolean isSOAPFault()
   :outertype: SOAPRequestException

   Checks if this exception is caused by a SOAP fault exception.

   :return: true if this exception is caused by a SOAP fault exception.

