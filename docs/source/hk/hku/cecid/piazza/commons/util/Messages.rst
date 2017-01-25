Messages
========

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public interface Messages

   Messages is a common interface of a collection of messages.

   :author: Hugo Y. K. Lam

Methods
-------
getDefaultLocale
^^^^^^^^^^^^^^^^

.. java:method:: public String getDefaultLocale()
   :outertype: Messages

   Gets the default locale of this messenger.

   :return: the default locale.

getDefaultMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public String getDefaultMessage()
   :outertype: Messages

   Gets the default message of this messenger.

   :return: the default message.

getErrorMessage
^^^^^^^^^^^^^^^

.. java:method:: public String getErrorMessage(String name)
   :outertype: Messages

   Gets an error message.

   :param name: the name of the message.
   :return: the message with the specified name.

getErrorMessage
^^^^^^^^^^^^^^^

.. java:method:: public String getErrorMessage(String name, String def)
   :outertype: Messages

   Gets an error message.

   :param name: the name of the message.
   :param def: a default message.
   :return: the message with the specified name.

getMessage
^^^^^^^^^^

.. java:method:: public String getMessage(String name)
   :outertype: Messages

   Gets a general message.

   :param name: the name of the message.
   :return: the message with the specified name.

getMessage
^^^^^^^^^^

.. java:method:: public String getMessage(String name, String def)
   :outertype: Messages

   Gets a general message.

   :param name: the name of the message.
   :param def: a default message.
   :return: the message with the specified name.

getMessage
^^^^^^^^^^

.. java:method:: public String getMessage(String name, String def, String type)
   :outertype: Messages

   Gets a message of the specified type.

   :param name: the name of the message.
   :param def: a default message.
   :param type: the type of the message.
   :return: the message with the specified name.

getMessage
^^^^^^^^^^

.. java:method:: public String getMessage(String name, String def, String type, String locale)
   :outertype: Messages

   Gets a message of the specified type and locale.

   :param name: the name of the message.
   :param def: a default message.
   :param type: the type of the message.
   :param locale: the locale of the message.
   :return: the message with the specified name.

getWarningMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public String getWarningMessage(String name)
   :outertype: Messages

   Gets a warning message.

   :param name: the name of the message.
   :return: the message with the specified name.

getWarningMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public String getWarningMessage(String name, String def)
   :outertype: Messages

   Gets a warning message.

   :param name: the name of the message.
   :param def: a default message.
   :return: the message with the specified name.

setDefaultLocale
^^^^^^^^^^^^^^^^

.. java:method:: public void setDefaultLocale(String locale)
   :outertype: Messages

   Sets the default locale of this messenger.

   :param locale: the default locale

setDefaultMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void setDefaultMessage(String string)
   :outertype: Messages

   Sets the default message of this messenger.

   :param string: the default message.

