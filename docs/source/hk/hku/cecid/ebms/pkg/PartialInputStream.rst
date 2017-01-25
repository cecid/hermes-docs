.. java:import:: java.io IOException

.. java:import:: java.io InputStream

PartialInputStream
==================

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type::  class PartialInputStream extends InputStream

   This is an implementation of \ ``java.io.InputStream``\  that represents part of data read from an \ ``InputStream``\ .

   :author: cyng

Constructors
------------
PartialInputStream
^^^^^^^^^^^^^^^^^^

.. java:constructor::  PartialInputStream(InputStream in, long offset, long length) throws IOException
   :outertype: PartialInputStream

   Constructor for the PartialInputStream object

   :param in: the origninal input stream
   :param offset: the offset the read data from the stream.
   :param length: the length of the data to be read
   :throws IOException: Description of the Exception

Methods
-------
close
^^^^^

.. java:method:: public void close() throws IOException
   :outertype: PartialInputStream

   close the stream

   :throws IOException: thrown when IO error occur during closing

read
^^^^

.. java:method:: public int read() throws IOException
   :outertype: PartialInputStream

   read a byte from the stream

   :throws IOException: thrown when IO error occur during reading.
   :return: the byte in int value from the stream.

