.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io InputStreamReader

.. java:import:: java.io OutputStream

.. java:import:: java.io OutputStreamWriter

.. java:import:: java.io Reader

.. java:import:: java.io StringReader

.. java:import:: java.io StringWriter

.. java:import:: java.io Writer

.. java:import:: java.nio.charset Charset

IOHandler
=========

.. java:package:: hk.hku.cecid.piazza.commons.io
   :noindex:

.. java:type:: public final class IOHandler

   IOHandler provides some convenient methods for handling some basic input and output funtions.

   :author: Hugo Y. K. Lam

Methods
-------
merge
^^^^^

.. java:method:: public static InputStream merge(InputStream ins1, InputStream ins2)
   :outertype: IOHandler

   Merges the given input streams into one input stream.

   :param ins1: the first input stream to be merged.
   :param ins2: the second input stream to be merged.
   :return: the merged input stream.

pipe
^^^^

.. java:method:: public static void pipe(InputStream ins, OutputStream out) throws IOException
   :outertype: IOHandler

   Pipes an input stream to an output stream.

   :param ins: the input stream to be read.
   :param out: the output stream to be written.
   :throws IOException: if there is IO error occurred during the operation.

pipe
^^^^

.. java:method:: public static void pipe(Reader reader, Writer writer) throws IOException
   :outertype: IOHandler

   Pipes a reader to a writer.

   :param reader: the reader to be read.
   :param writer: the writer to be written.
   :throws IOException: if there is IO error occurred during the operation.

readBytes
^^^^^^^^^

.. java:method:: public static byte[] readBytes(InputStream ins) throws IOException
   :outertype: IOHandler

   Reads an array of bytes from an input stream.

   :param ins: the input stream to be read.
   :throws IOException: if there is IO error occurred during the operation.
   :return: an array of bytes read from the specified input stream.

readBytes
^^^^^^^^^

.. java:method:: public static byte[] readBytes(Reader reader, Charset charset) throws IOException
   :outertype: IOHandler

   Reads an array of bytes from a reader.

   :param reader: the reader to be read.
   :param charset: the charset used to convert the characters.
   :throws IOException: if there is IO error occurred during the operation.
   :return: an array of bytes read from the specified reader.

readString
^^^^^^^^^^

.. java:method:: public static String readString(InputStream ins, Charset charset) throws IOException
   :outertype: IOHandler

   Reads a string from an input stream.

   :param ins: the input stream to be read.
   :param charset: the charset used to convert the bytes.
   :throws IOException: if there is IO error occurred during the operation.
   :return: a string read from the specified input stream.

readString
^^^^^^^^^^

.. java:method:: public static String readString(Reader reader) throws IOException
   :outertype: IOHandler

   Reads a string from a reader.

   :param reader: the reader to be read.
   :throws IOException: if there is IO error occurred during the operation.
   :return: a string read from the specified reader.

writeBytes
^^^^^^^^^^

.. java:method:: public static void writeBytes(byte[] bytes, OutputStream out) throws IOException
   :outertype: IOHandler

   Writes an array of bytes to an output stream.

   :param bytes: an array of bytes to write.
   :param out: the output stream to be written.
   :throws IOException: if there is IO error occurred during the operation.

writeBytes
^^^^^^^^^^

.. java:method:: public static void writeBytes(byte[] bytes, Writer writer, Charset charset) throws IOException
   :outertype: IOHandler

   Writes an array of bytes to a writer.

   :param bytes: an array of bytes to write.
   :param writer: to writer to be written.
   :param charset: the charset used to convert the bytes.
   :throws IOException: if there is IO error occurred during the operation.

writeString
^^^^^^^^^^^

.. java:method:: public static void writeString(String s, OutputStream out, Charset charset) throws IOException
   :outertype: IOHandler

   Writes a string to an output stream.

   :param s: the string to write.
   :param out: the output stream to be written.
   :param charset: the charset used to convert the characters.
   :throws IOException: if there is IO error occurred during the operation.

writeString
^^^^^^^^^^^

.. java:method:: public static void writeString(String s, Writer writer) throws IOException
   :outertype: IOHandler

   Writes a string to a writer.

   :param s: the string to write.
   :param writer: the writer to be written.
   :throws IOException: if there is IO error occurred during the operation.

