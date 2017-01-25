.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.util Instance

.. java:import:: java.awt.datatransfer DataFlavor

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: javax.activation ActivationDataFlavor

.. java:import:: javax.activation DataContentHandler

.. java:import:: javax.activation DataSource

ByteStreamDataContentHandler
============================

.. java:package:: hk.hku.cecid.piazza.commons.activation
   :noindex:

.. java:type:: public class ByteStreamDataContentHandler implements DataContentHandler

   ByteStreamDataContentHandler is an implementation of the javax.activation.DataContentHandler that represents a data content handler of a byte stream.

   :author: Hugo Y. K. Lam

Constructors
------------
ByteStreamDataContentHandler
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public ByteStreamDataContentHandler()
   :outertype: ByteStreamDataContentHandler

   Creates a new instance of ByteStreamDataContentHandler.

Methods
-------
getContent
^^^^^^^^^^

.. java:method:: public Object getContent(DataSource ds) throws IOException
   :outertype: ByteStreamDataContentHandler

   Returns a byte stream, which is described by the first DataFlavor returned by the getTransferDataFlavors() method, representing the specified data.

   :param ds: the data source representing the data to be converted.
   :throws IOException: if unable to convert the data.
   :return: the byte stream representing the data.

   **See also:** :java:ref:`javax.activation.DataContentHandler.getContent(javax.activation.DataSource)`

getTransferData
^^^^^^^^^^^^^^^

.. java:method:: public Object getTransferData(DataFlavor df, DataSource ds) throws IOException
   :outertype: ByteStreamDataContentHandler

   Returns a byte stream which represents the data to be transferred, ignoring the specified flavor.

   :param df: the data flavor representing the requested type.
   :param ds: the DataSource representing the data to be converted.
   :throws IOException: if unable to convert the data.
   :return: the byte stream representing the data.

   **See also:** :java:ref:`javax.activation.DataContentHandler.getTransferData(java.awt.datatransfer.DataFlavor,javax.activation.DataSource)`

getTransferDataFlavors
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public DataFlavor[] getTransferDataFlavors()
   :outertype: ByteStreamDataContentHandler

   Returns an array of DataFlavor objects indicating the flavors the data can be provided in.

   :return: an array of DataFlavor objects.

   **See also:** :java:ref:`javax.activation.DataContentHandler.getTransferDataFlavors()`

writeTo
^^^^^^^

.. java:method:: public void writeTo(Object obj, String mimeType, OutputStream os) throws IOException
   :outertype: ByteStreamDataContentHandler

   Converts the object to a byte stream of the specified MIME type and write it to the output stream.

   :param obj: the object to be converted.
   :param mimeType: the requested MIME type of the resulting byte stream.
   :param os: the output stream into which to write the converted byte stream.
   :throws IOException: if unable to convert the given object.

   **See also:** :java:ref:`javax.activation.DataContentHandler.writeTo(java.lang.Object,java.lang.String,java.io.OutputStream)`

