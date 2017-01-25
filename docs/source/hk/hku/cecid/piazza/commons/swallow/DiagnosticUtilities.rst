.. java:import:: java.io IOException

.. java:import:: java.io OutputStream

.. java:import:: java.io Writer

.. java:import:: java.lang.management ManagementFactory

.. java:import:: java.lang.management ThreadInfo

.. java:import:: java.lang.management ThreadMXBean

DiagnosticUtilities
===================

.. java:package:: hk.hku.cecid.piazza.commons.swallow
   :noindex:

.. java:type:: public class DiagnosticUtilities

   The \ ``DiagnosticUtilities``\  is is a utility for providing useful information for monitoring and debugging the JVM.

   :author: Twinsen Tsang

Methods
-------
dumpAllThread
^^^^^^^^^^^^^

.. java:method:: public void dumpAllThread() throws IOException
   :outertype: DiagnosticUtilities

   Dump all threads information from the current JVM.

dumpAllThread
^^^^^^^^^^^^^

.. java:method:: public void dumpAllThread(OutputStream os, int stackTraceDepth) throws IOException
   :outertype: DiagnosticUtilities

   Dump all threads information from the current JVM to the specified OutputStream \ ``os``\ .

   :param os: The output stream to dump the threads information.
   :param stackTraceDepth: The depth of stack trace to dump, default is 3.
   :throws NullPointerException: when \ ``os``\  is null.
   :throws IllegalArgumentException: when \ ``stackTraceDepth``\  less than zero.

dumpAllThread
^^^^^^^^^^^^^

.. java:method:: public void dumpAllThread(Writer w, int stackTraceDepth) throws IOException
   :outertype: DiagnosticUtilities

   Dump all threads information from the current JVM to the specified OutputStream \ ``w``\ .

   :param w: The writer used to dump the threads information.
   :param stackTraceDepth: The depth of stack trace to dump, default is 3.
   :throws NullPointerException: when \ ``os``\  is null.
   :throws IllegalArgumentException: when \ ``stackTraceDepth``\  less than zero.

getInstance
^^^^^^^^^^^

.. java:method:: public static DiagnosticUtilities getInstance()
   :outertype: DiagnosticUtilities

   Get the single instance of \ ``DiagnosticUtilities``\ .

   :return: the single instance of \ ``DiagnosticUtilities``\ .

getNewInstance
^^^^^^^^^^^^^^

.. java:method:: public static DiagnosticUtilities getNewInstance()
   :outertype: DiagnosticUtilities

   Get the new instance of \ ``DiagnosticUtilities``\ .

   :return: the new instance of \ ``DiagnosticUtilities``\ .

main
^^^^

.. java:method:: public static void main(String[] args) throws IOException
   :outertype: DiagnosticUtilities

