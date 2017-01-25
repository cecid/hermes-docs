Mailcap
=======

.. java:package:: hk.hku.cecid.piazza.commons.activation
   :noindex:

.. java:type:: public class Mailcap

   Mailcap represents a single mailcap in the MailcapCommandMap. It is a convenient class for constructing a mailcap to be added to the MailcapCommandMap and for easy comparison if necessary.

   :author: Kevin Tsang

   **See also:** :java:ref:`javax.activation.MailcapCommandMap`

Constructors
------------
Mailcap
^^^^^^^

.. java:constructor:: public Mailcap(String mimeType, String commandName, String className)
   :outertype: Mailcap

   Creates a new instance of Mailcap.

   :param mimeType: the MIME type.
   :param commandName: the command name.
   :param className: the handling class name.

Methods
-------
getClassName
^^^^^^^^^^^^

.. java:method:: public String getClassName()
   :outertype: Mailcap

   Gets the handling class name.

   :return: the handling class name.

getCommandName
^^^^^^^^^^^^^^

.. java:method:: public String getCommandName()
   :outertype: Mailcap

   Gets the command name.

   :return: the command name.

getMimeType
^^^^^^^^^^^

.. java:method:: public String getMimeType()
   :outertype: Mailcap

   Gets the MIME type.

   :return: the MIME type.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: Mailcap

   Returns a string representation of this mailcap.

   :return: a mailcap formatted string.

   **See also:** :java:ref:`java.lang.Object.toString()`

