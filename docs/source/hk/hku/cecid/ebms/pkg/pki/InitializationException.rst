InitializationException
=======================

.. java:package:: hk.hku.cecid.ebms.pkg.pki
   :noindex:

.. java:type:: public class InitializationException extends Exception

   Exception class representing the error during initialization.

   :author: kcyee

Constructors
------------
InitializationException
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public InitializationException(String msg)
   :outertype: InitializationException

   Construtor with message.

   :param msg: the message of the exception

InitializationException
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public InitializationException(String msg, Exception e)
   :outertype: InitializationException

   Instantiate the exception with a nested exception

   :param msg: the message of the exception
   :param e: the exception to be wrapped

Methods
-------
getMessage
^^^^^^^^^^

.. java:method:: public String getMessage()
   :outertype: InitializationException

   It overrides the getMessage() method so it also reports the nested exception , if it exists.

   :return: the exception message.

getNestedException
^^^^^^^^^^^^^^^^^^

.. java:method:: public Exception getNestedException()
   :outertype: InitializationException

   :return: the nested exception

