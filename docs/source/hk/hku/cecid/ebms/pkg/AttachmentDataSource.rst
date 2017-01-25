.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io File

.. java:import:: java.io FileInputStream

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: javax.activation DataSource

.. java:import:: javax.mail MessagingException

.. java:import:: javax.mail.internet MimeUtility

AttachmentDataSource
====================

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class AttachmentDataSource implements DataSource

   This is an implementation of \ ``javax.activation.DataSource``\  that encapsulates attachment data in a SOAP message.

   :author: cyng

Constructors
------------
AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(byte[] data, String contentType)
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object from an array of binary data.

   :param data: Byte array containing data for the \ ``AttachmentDataSource``\
   :param contentType: Content type of the data.

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(byte[] data, String contentType, String name)
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object from an array of binary data, and assign a name to the data source.

   :param data: Byte array containing data for the \ ``AttachmentDataSource``\
   :param contentType: Content type of the data.
   :param name: Name assigned to the \ ``AttachmentDataSource``\

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(byte[] data, String contentType, String encoding, String name)
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object from an array of binary data, and assign a name to the data source.

   :param data: Byte array containing data for the \ ``AttachmentDataSource``\
   :param contentType: Content type of the data.
   :param encoding: Content-Transfer-Encoding of the data.
   :param name: Name assigned to the \ ``AttachmentDataSource``\

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(String fileName, String contentType) throws IOException
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object from a file.

   :param fileName: Name of the file to be loaded.
   :param contentType: Content type of the file.
   :throws IOException:

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(String fileName, String contentType, boolean loadToMem) throws IOException
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object from a file.

   :param fileName: Name of the file to be loaded.
   :param contentType: Content type of the file.
   :param loadToMem: Load all data to memory upon creation
   :throws IOException:

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(File file, String contentType) throws IOException
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object from a \ ``File``\  object.

   :param file: \ ``File``\  object containing information on the file to be loaded.
   :param contentType: Content type of the file.
   :throws IOException:

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(File file, String contentType, boolean loadToMem) throws IOException
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object from a \ ``File``\  object.

   :param file: \ ``File``\  object containing information on the file to be loaded.
   :param contentType: Content type of the file.
   :param loadToMem: Load all data to memory upon creation
   :throws IOException:

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(InputStream in, String contentType) throws IOException
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object from an \ ``InputStream``\ .

   :param in: \ ``InputStream``\  from which the data is read and stored in the data source.
   :param contentType: Content type of the data.
   :throws IOException:

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(InputStream in, String contentType, String name) throws IOException
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object from an \ ``InputStream``\  with a given name.

   :param in: \ ``InputStream``\  from which the data is read and stored in the data source.
   :param contentType: Content type of the data.
   :param name: Name assigned to the \ ``AttachmentDataSource``\ .
   :throws IOException:

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(InputStream in, String contentType, String encoding, String name) throws IOException
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object from an \ ``InputStream``\  with the specified Content-Transfer-Encoding and name.

   :param in: \ ``InputStream``\  from which the data is read and stored in the data source.
   :param contentType: Content type of the data.
   :param encoding: Content-Transfer-Encoding of the data.
   :param name: Name assigned to the \ ``AttachmentDataSource``\ .
   :throws IOException:

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(String fileName, long offset, long length, String contentType) throws IOException
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object using the data of \ ``length``\  in a file starting from \ ``offset``\  with the specified Content-Type.

   :param fileName: Name of the file to be loaded.
   :param offset: Offset from the start of the file.
   :param length: Length of data to be read.
   :param contentType: Content type of the data.

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(String fileName, long offset, long length, String contentType, boolean loadToMem) throws IOException
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object using the data of \ ``length``\  in a file starting from \ ``offset``\  with the specified Content-Type.

   :param fileName: Name of the file to be loaded.
   :param offset: Offset from the start of the file.
   :param length: Length of data to be read.
   :param contentType: Content type of the data.
   :param loadToMem: Load all data to memory upon creation

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(String fileName, long offset, long length, String contentType, String encoding) throws IOException
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object using the data of \ ``length``\  in a file starting from \ ``offset``\ . with the specified Content-Type and Content-Transfer-Encoding.

   :param fileName: Name of the file to be loaded.
   :param offset: Offset from the start of the file.
   :param length: Length of data to be read.
   :param contentType: Content type of the data.
   :param encoding: Content-Transfer-Encoding of the data.

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(String fileName, long offset, long length, String contentType, String encoding, boolean loadToMem) throws IOException
   :outertype: AttachmentDataSource

   Constructs an \ ``AttachmentDataSource``\  object using the data of \ ``length``\  in a file starting from \ ``offset``\ . with the specified Content-Type and Content-Transfer-Encoding.

   :param fileName: Name of the file to be loaded.
   :param offset: Offset from the start of the file.
   :param length: Length of data to be read.
   :param contentType: Content type of the data.
   :param encoding: Content-Transfer-Encoding of the data.
   :param loadToMem: Load all data to memory upon creation

AttachmentDataSource
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AttachmentDataSource(DataSource dataSource, long offset, long length, String contentType, String encoding, boolean loadToMem) throws IOException
   :outertype: AttachmentDataSource

Methods
-------
getByteArray
^^^^^^^^^^^^

.. java:method:: public byte[] getByteArray() throws IOException
   :outertype: AttachmentDataSource

   Gets a byte array of data in this data source.

   :return: A byte array of data.

getContentType
^^^^^^^^^^^^^^

.. java:method:: public String getContentType()
   :outertype: AttachmentDataSource

   Gets the content type of data stored in this \ ``AttachmentDataSource``\ .

   :return: Content type of data stored in data source.

getInputStream
^^^^^^^^^^^^^^

.. java:method:: public InputStream getInputStream() throws IOException
   :outertype: AttachmentDataSource

   Gets \ ``InputStream``\  from which data in the \ ``AttachmentDataSource``\  can be read.

   :throws IOException:
   :return: An \ ``InputStream``\ .

getLength
^^^^^^^^^

.. java:method:: public long getLength()
   :outertype: AttachmentDataSource

   Gets the length of data in this data source

   :return: length of data

getName
^^^^^^^

.. java:method:: public String getName()
   :outertype: AttachmentDataSource

   Gets the name of the \ ``AttachmentDataSource``\ .

   :return: Name of data source.

getOutputStream
^^^^^^^^^^^^^^^

.. java:method:: public OutputStream getOutputStream() throws IOException
   :outertype: AttachmentDataSource

   This method should never be called. It implements the \ ``getOutputStream()``\  method of the \ ``javax.activation.DataSource``\  interface and \ ``IOException``\  will be thrown as the result of invocation.

   :throws IOException:
   :return: This method always result in \ ``IOException``\ ; it never returns normally.

setName
^^^^^^^

.. java:method:: public void setName(String name)
   :outertype: AttachmentDataSource

   Sets the name of the \ ``AttachmentDataSource``\ .

   :param name: Name of data source.

