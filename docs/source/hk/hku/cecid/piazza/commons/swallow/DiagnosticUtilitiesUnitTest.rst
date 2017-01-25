.. java:import:: hk.hku.cecid.piazza.commons.swallow DiagnosticUtilities

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io IOException

.. java:import:: java.io OutputStream

.. java:import:: org.junit Test

.. java:import:: org.junit Assert

DiagnosticUtilitiesUnitTest
===========================

.. java:package:: hk.hku.cecid.piazza.commons.swallow
   :noindex:

.. java:type:: public class DiagnosticUtilitiesUnitTest

   The \ ``DiagnoisticUtilitiesUnitTest``\  is MANUAL unit test of \ ``DiagnoisticUtilities``\ .

   :author: Twinsen Tsang

Methods
-------
testDumpAllThread
^^^^^^^^^^^^^^^^^

.. java:method:: @Test public void testDumpAllThread()
   :outertype: DiagnosticUtilitiesUnitTest

   It is not an automated test-case. Just for manual diagnostic method.

testDumpAllThreadWithIllegalStackTraceDepth
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Test public void testDumpAllThreadWithIllegalStackTraceDepth() throws IOException
   :outertype: DiagnosticUtilitiesUnitTest

   Test whether operation dumpAllThread throws IllegalArgumentException when stack trace depth is less than zero.

testDumpAllThreadWithNullStream
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Test public void testDumpAllThreadWithNullStream() throws IOException
   :outertype: DiagnosticUtilitiesUnitTest

   Test whether operation dumpAllThread throws NullPointerException when output stream is null.

testGetInstance
^^^^^^^^^^^^^^^

.. java:method:: @Test public void testGetInstance()
   :outertype: DiagnosticUtilitiesUnitTest

   Test whether the singleton instance is instantiated successfully through \ :java:ref:`DiagnosticUtilities.getInstance()`\

