.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: javax.activation DataSource

ByteArrayDataSource
===================

.. java:package:: hk.hku.cecid.piazza.commons.activation
   :noindex:

.. java:type:: public class ByteArrayDataSource implements DataSource

   ByteArrayDataSource is an implementation of the javax.activation.DataSource that represents a data source of a byte array.

   :author: Hugo Y. K. Lam

Constructors
------------
ByteArrayDataSource
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public ByteArrayDataSource(byte[] bytes)
   :outertype: ByteArrayDataSource

   Creates a new instance of ByteArrayDataSource.

   :param bytes: the bytes source.

ByteArrayDataSource
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public ByteArrayDataSource(byte[] bytes, String contentType)
   :outertype: ByteArrayDataSource

   Creates a new instance of ByteArrayDataSource.

   :param bytes: the bytes source.
   :param contentType: the content type.

ByteArrayDataSource
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public ByteArrayDataSource(byte[] bytes, String contentType, String name)
   :outertype: ByteArrayDataSource

   Creates a new instance of ByteArrayDataSource.

   :param bytes: the bytes source.
   :param contentType: the content type.
   :param name: the name of the underlying content.

Methods
-------
getContentType
^^^^^^^^^^^^^^

.. java:method:: public String getContentType()
   :outertype: ByteArrayDataSource

   Gets the content type.

   :return: the content type.

   **See also:** :java:ref:`javax.activation.DataSource.getContentType()`

getInputStream
^^^^^^^^^^^^^^

.. java:method:: public InputStream getInputStream() throws IOException
   :outertype: ByteArrayDataSource

   Returns a new input stream representing the bytes source.

   :return: a new byte array input stream.

   **See also:** :java:ref:`javax.activation.DataSource.getInputStream()`

getName
^^^^^^^

.. java:method:: public String getName()
   :outertype: ByteArrayDataSource

   Gets the name of the underlying content.

   :return: the name of the underlying content.

   **See also:** :java:ref:`javax.activation.DataSource.getName()`

getOutputStream
^^^^^^^^^^^^^^^

.. java:method:: public OutputStream getOutputStream() throws IOException
   :outertype: ByteArrayDataSource

   This method always throw IO exception.

   :throws IOException: as output stream is not supported by this data source.

   **See also:** :java:ref:`javax.activation.DataSource.getOutputStream()`

