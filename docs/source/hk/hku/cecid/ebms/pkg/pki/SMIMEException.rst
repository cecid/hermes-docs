SMIMEException
==============

.. java:package:: hk.hku.cecid.ebms.pkg.pki
   :noindex:

.. java:type:: public class SMIMEException extends Exception

   The exception will be thrown when generating SMIME mime body or mime message

   :author: achong

Constructors
------------
SMIMEException
^^^^^^^^^^^^^^

.. java:constructor:: public SMIMEException(String msg)
   :outertype: SMIMEException

   Construtor with message.

   :param msg: the message of the exception

SMIMEException
^^^^^^^^^^^^^^

.. java:constructor:: public SMIMEException(String msg, Exception e)
   :outertype: SMIMEException

   Instantiate the exception with a nested exception

   :param msg: the message of the exception
   :param e: the exception to be wrapped

Methods
-------
getMessage
^^^^^^^^^^

.. java:method:: public String getMessage()
   :outertype: SMIMEException

   It overrides the getMessage() method so it also reports the nested exception , if it exists.

   :return: the exception message.

getNestedException
^^^^^^^^^^^^^^^^^^

.. java:method:: public Exception getNestedException()
   :outertype: SMIMEException

   :return: the nested exception

