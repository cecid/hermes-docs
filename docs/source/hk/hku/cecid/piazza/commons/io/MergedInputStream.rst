.. java:import:: java.io IOException

.. java:import:: java.io InputStream

MergedInputStream
=================

.. java:package:: hk.hku.cecid.piazza.commons.io
   :noindex:

.. java:type:: public class MergedInputStream extends InputStream

   MergedInputStream is an input stream which can merge two input streams into one. When the read() method is called, the first input stream will be read at first. However, if it has already reached the end, the second input stream will be read.

   :author: Hugo Y. K. Lam

Constructors
------------
MergedInputStream
^^^^^^^^^^^^^^^^^

.. java:constructor:: public MergedInputStream(InputStream ins1, InputStream ins2)
   :outertype: MergedInputStream

   Creates a new instance of MergedInputStream.

   :param ins1: the first input stream to be merged.
   :param ins2: the second input stream to be merged.

Methods
-------
read
^^^^

.. java:method:: public int read() throws IOException
   :outertype: MergedInputStream

   Reads the first input stream and if it has reached the end, reads the second input stream. After this input stream has positioned to the second input stream, it will never come back to the first one.

   **See also:** :java:ref:`java.io.InputStream.read()`

