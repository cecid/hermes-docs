.. java:import:: java.io InputStream

Payload
=======

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class Payload implements Data

   The Payload is a data object representing a payload
   in the SOAP message.

   :author: Twinsen Tsang

Constructors
------------
Payload
^^^^^^^

.. java:constructor:: public Payload(String filePath, String contentType)
   :outertype: Payload

   Explicit Constructor.

   :param filePath: The payload filepath.
   :param contentType: The content type of payload.

Payload
^^^^^^^

.. java:constructor:: public Payload(InputStream inputStream, String contentType)
   :outertype: Payload

   :param inputStream:
   :param contentType:

Methods
-------
getContentType
^^^^^^^^^^^^^^

.. java:method:: public String getContentType()
   :outertype: Payload

   :return: The content type of payload.

getFilePath
^^^^^^^^^^^

.. java:method:: public String getFilePath()
   :outertype: Payload

   :return: The filepath of the payload.

getInputStream
^^^^^^^^^^^^^^

.. java:method:: public InputStream getInputStream()
   :outertype: Payload

   :return: The input stream of the payload

setFilePath
^^^^^^^^^^^

.. java:method:: public void setFilePath(String filepath)
   :outertype: Payload

   Set filepath of the payload. (This method is open to set the filename of payload for message receiver)

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: Payload

   toString method

