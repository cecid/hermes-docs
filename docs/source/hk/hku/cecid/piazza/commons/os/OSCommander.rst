.. java:import:: java.io BufferedInputStream

.. java:import:: java.io BufferedReader

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io File

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io InputStreamReader

.. java:import:: java.io OutputStream

.. java:import:: java.io RandomAccessFile

.. java:import:: java.lang.reflect Method

.. java:import:: java.util ArrayList

.. java:import:: java.util Collections

.. java:import:: java.util Iterator

.. java:import:: org.apache.commons.io FileSystemUtils

.. java:import:: hk.hku.cecid.piazza.commons.module ModuleException

.. java:import:: hk.hku.cecid.piazza.commons.module SystemComponent

.. java:import:: hk.hku.cecid.piazza.commons.util ConsoleLogger

.. java:import:: hk.hku.cecid.piazza.commons.util Logger

OSCommander
===========

.. java:package:: hk.hku.cecid.piazza.commons.os
   :noindex:

.. java:type:: public class OSCommander

   The OS Manager provides interface for executing platform command console so that it can execute the console command through this interface.  Creation Date: 04/05/2009

   :author: Philip Wong

Fields
------
ONE_GB
^^^^^^

.. java:field:: public static final long ONE_GB
   :outertype: OSCommander

REDIRECT_ERROR_STREAM
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static boolean REDIRECT_ERROR_STREAM
   :outertype: OSCommander

Constructors
------------
OSCommander
^^^^^^^^^^^

.. java:constructor:: public OSCommander()
   :outertype: OSCommander

OSCommander
^^^^^^^^^^^

.. java:constructor:: public OSCommander(SystemComponent sys)
   :outertype: OSCommander

Methods
-------
createDummyFile
^^^^^^^^^^^^^^^

.. java:method:: public void createDummyFile(String path, long size) throws Exception
   :outertype: OSCommander

   Create a dummy file with the specified path and size for Linux, Mac OS X & SunOS.

   :param path: The absolute path of the dummy files.
   :param size: The size of dummy files.
   :throws IOException:
   :return: true if the operation run successfully.

execNoWaitAsInputStream
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public BufferedInputStream execNoWaitAsInputStream(String... args) throws IOException
   :outertype: OSCommander

execNoWaitAsInputStream
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public BufferedInputStream execNoWaitAsInputStream(File dir, String... args) throws IOException
   :outertype: OSCommander

execNoWaitAsProcess
^^^^^^^^^^^^^^^^^^^

.. java:method:: protected Process execNoWaitAsProcess(String... args) throws IOException
   :outertype: OSCommander

execNoWaitAsProcess
^^^^^^^^^^^^^^^^^^^

.. java:method:: protected Process execNoWaitAsProcess(File dir, String... args) throws IOException
   :outertype: OSCommander

execNoWaitAsReader
^^^^^^^^^^^^^^^^^^

.. java:method:: public BufferedReader execNoWaitAsReader(String... args) throws IOException
   :outertype: OSCommander

execNoWaitAsReader
^^^^^^^^^^^^^^^^^^

.. java:method:: public BufferedReader execNoWaitAsReader(File dir, String... args) throws IOException
   :outertype: OSCommander

execWaitAsOutputStream
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void execWaitAsOutputStream(OutputStream os, String... args) throws IOException, InterruptedException
   :outertype: OSCommander

execWaitAsOutputStream
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void execWaitAsOutputStream(OutputStream os, File dir, String... args) throws IOException, InterruptedException
   :outertype: OSCommander

execWaitAsString
^^^^^^^^^^^^^^^^

.. java:method:: public String execWaitAsString(String... args) throws IOException, InterruptedException
   :outertype: OSCommander

execWaitAsString
^^^^^^^^^^^^^^^^

.. java:method:: public String execWaitAsString(File dir, String... args) throws IOException, InterruptedException
   :outertype: OSCommander

getDiskFreespace
^^^^^^^^^^^^^^^^

.. java:method:: public long getDiskFreespace(String path) throws IOException
   :outertype: OSCommander

getOSName
^^^^^^^^^

.. java:method:: public String getOSName()
   :outertype: OSCommander

getOSVersion
^^^^^^^^^^^^

.. java:method:: public String getOSVersion()
   :outertype: OSCommander

init
^^^^

.. java:method:: protected void init()
   :outertype: OSCommander

writeTo
^^^^^^^

.. java:method:: public void writeTo(InputStream is, OutputStream os)
   :outertype: OSCommander

