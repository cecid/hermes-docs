.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: javax.activation DataSource

InputStreamDataSource
=====================

.. java:package:: hk.hku.cecid.piazza.commons.activation
   :noindex:

.. java:type:: public class InputStreamDataSource implements DataSource

   InputStreamDataSource is an implementation of the javax.activation.DataSource It is designed to be used by SOAPMailSender as a bridge of InputStream and OutputStream for base64 encoding transformation.

   :author: Philip Wong

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.soap.SOAPMailSender`

Constructors
------------
InputStreamDataSource
^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public InputStreamDataSource(InputStream is, String contentType, String name)
   :outertype: InputStreamDataSource

   Creates a new instance of InputStreamDataSource by BodyPart.

   :param is: the input stream.
   :param contentType: the content type.
   :param name: the filename if any.

Methods
-------
getContentType
^^^^^^^^^^^^^^

.. java:method:: public String getContentType()
   :outertype: InputStreamDataSource

   Gets the content type.

   :return: the content type when this data source created.

getInputStream
^^^^^^^^^^^^^^

.. java:method:: public InputStream getInputStream() throws IOException
   :outertype: InputStreamDataSource

   Gets the input stream.

   :return: the input stream when this data source created.

getName
^^^^^^^

.. java:method:: public String getName()
   :outertype: InputStreamDataSource

   Gets the filename.

   :return: the content type when this data source created.

getOutputStream
^^^^^^^^^^^^^^^

.. java:method:: public OutputStream getOutputStream() throws IOException
   :outertype: InputStreamDataSource

   Returns new byte array from a new BytesArrayOutStream always. Logically, it is required to copy binary content from the input stream to output stream. But it is found the same result without touching binary content.

   :return: the content type when this data source created.

