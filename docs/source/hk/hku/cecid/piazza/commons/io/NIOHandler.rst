.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: java.io FileInputStream

.. java:import:: java.nio.channels Channels

.. java:import:: java.nio.channels FileChannel

.. java:import:: java.nio.channels ReadableByteChannel

.. java:import:: java.nio.channels WritableByteChannel

.. java:import:: java.nio ByteBuffer

NIOHandler
==========

.. java:package:: hk.hku.cecid.piazza.commons.io
   :noindex:

.. java:type:: public class NIOHandler

   NIOHandler provides some convenient methods for handling some basic input and output funtions which has adopted the features of java NIO package. Creation Date: 5/10/2006

   :author: Twinsen

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.io.IOHandler`, :java:ref:`java.nio.ByteBuffer`, :java:ref:`java.nio.MappedByteBuffer`, :java:ref:`java.nio.channels.Channels`

Fields
------
DEFAULT_PAGE_SIZE
^^^^^^^^^^^^^^^^^

.. java:field:: public static final int DEFAULT_PAGE_SIZE
   :outertype: NIOHandler

   The default page size for memory mapped stream.

MAX_BUFFER_SIZE
^^^^^^^^^^^^^^^

.. java:field:: public static final int MAX_BUFFER_SIZE
   :outertype: NIOHandler

   The max buffer size of ByteBuffer is 10mb.

Methods
-------
pipe
^^^^

.. java:method:: public static void pipe(FileInputStream fins, OutputStream out) throws IOException
   :outertype: NIOHandler

   Pipes an file input stream to an output stream.

   :param fins: the file input stream to be read.
   :param out: the output stream to be written.
   :throws IOException: if there is IO error occurred during the operation.

pipe
^^^^

.. java:method:: public static void pipe(FileInputStream fins, OutputStream out, int startPosition, long size) throws IOException
   :outertype: NIOHandler

   Pipes an file input stream to an output stream.

   :param fins: the file input stream to be read.
   :param out: the output stream to be written.
   :throws IOException: if there is IO error occurred during the operation.

pipe
^^^^

.. java:method:: public static void pipe(InputStream ins, OutputStream out) throws IOException
   :outertype: NIOHandler

   Pipes an input stream to an output stream.

   :param ins: the input stream to be read.
   :param out: the output stream to be written.
   :throws IOException: if there is IO error occurred during the operation.

readByteBuffer
^^^^^^^^^^^^^^

.. java:method:: public static ByteBuffer readByteBuffer(InputStream ins) throws IOException
   :outertype: NIOHandler

   Reads an array of bytes from an input stream.

   :param ins: the input stream to be read.
   :throws IOException: if there is IO error occurred during the operation.
   :return: a bytes buffer read from the specified input stream.

readBytes
^^^^^^^^^

.. java:method:: public static byte[] readBytes(InputStream ins) throws IOException
   :outertype: NIOHandler

   Reads an array of bytes from an input stream.

   :param ins: the input stream to be read.
   :throws IOException: if there is IO error occurred during the operation.
   :return: an array of bytes read from the specified input stream.

writeBytes
^^^^^^^^^^

.. java:method:: public static void writeBytes(byte[] bytes, OutputStream out) throws IOException
   :outertype: NIOHandler

   Writes an array of bytes to an output stream.

   :param bytes: an array of bytes to write.
   :param out: the output stream to be written.
   :throws IOException: if there is IO error occurred during the operation.

writeBytes
^^^^^^^^^^

.. java:method:: public static void writeBytes(ByteBuffer src, OutputStream out) throws IOException
   :outertype: NIOHandler

   Writes a byte buffer to an output stream.

   :param src: a byte buffer to write.
   :param out: the output stream to be written.
   :throws IOException: if there is IO error occurred during the operation.

