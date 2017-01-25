.. java:import:: java.util ArrayList

.. java:import:: java.util Collection

.. java:import:: java.util List

.. java:import:: java.util Properties

.. java:import:: org.junit Ignore

.. java:import:: org.junit Test

.. java:import:: org.junit Assert

.. java:import:: org.junit.runner RunWith

.. java:import:: org.junit.runners Parameterized

.. java:import:: org.junit.runners Parameterized.Parameters

.. java:import:: hk.hku.cecid.piazza.commons.swallow ShutdownHookEmailModule

.. java:import:: hk.hku.cecid.piazza.commons.swallow ShutdownHookEmailThread

.. java:import:: hk.hku.cecid.piazza.commons.test ModuleTest

.. java:import:: hk.hku.cecid.piazza.commons.util Instance

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

ShutdownHookEmailModuleUnitTest
===============================

.. java:package:: hk.hku.cecid.piazza.commons.swallow
   :noindex:

.. java:type:: @RunWith public class ShutdownHookEmailModuleUnitTest extends ModuleTest<ShutdownHookEmailModule>

   The \ ``ShutdownHookEmailModuleUnitTest``\  is unit test of \ ``ShutdownHookEmailModule``\ .

   :author: Twinsen Tsang

Fields
------
MODULE_DESCRIPTORS
^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String[] MODULE_DESCRIPTORS
   :outertype: ShutdownHookEmailModuleUnitTest

Constructors
------------
ShutdownHookEmailModuleUnitTest
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public ShutdownHookEmailModuleUnitTest(String moduleDescriptor)
   :outertype: ShutdownHookEmailModuleUnitTest

   Create an instance of parameterized (parameter=module descriptor) ShutdownHookEmailModuleUnitTest.

   :param moduleDescriptor: The parameterized module descriptor.

Methods
-------
getModuleDescription
^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Override public String getModuleDescription()
   :outertype: ShutdownHookEmailModuleUnitTest

getModuleDescriptionSet
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @SuppressWarnings @Parameters public static Collection getModuleDescriptionSet()
   :outertype: ShutdownHookEmailModuleUnitTest

initAtOnce
^^^^^^^^^^

.. java:method:: @Override public boolean initAtOnce()
   :outertype: ShutdownHookEmailModuleUnitTest

tearDown
^^^^^^^^

.. java:method:: @Override public void tearDown() throws Exception
   :outertype: ShutdownHookEmailModuleUnitTest

testCreateShutdownHookWorker
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Test public void testCreateShutdownHookWorker() throws Throwable
   :outertype: ShutdownHookEmailModuleUnitTest

   Test whether the \ :java:ref:`ShutdownHookEmailModule.createShutdownHookWorker()`\  able to wire up all properties from the module descriptor and it is an instance of ShutdownHookEmailThread. Note that the assertion actually take place in a helper class called CreateShudownHookWorkerAssertionThread. It is essential because the ShutdownHook worker thread is loaded through a clone of current class loader and therefore the class only appear in that domain.

testGetThread
^^^^^^^^^^^^^

.. java:method:: @Test public void testGetThread()
   :outertype: ShutdownHookEmailModuleUnitTest

   Test whether \ :java:ref:`ShutdownHookEmailModule.getThread()`\  always return non null value.

testOnCreateMailNotificationBody
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Test @Ignore public void testOnCreateMailNotificationBody() throws Throwable
   :outertype: ShutdownHookEmailModuleUnitTest

   This test has not implemented yet because the mail subject is subject to change.

testOnCreateMailNotificationSubject
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Test @Ignore public void testOnCreateMailNotificationSubject() throws Throwable
   :outertype: ShutdownHookEmailModuleUnitTest

   This test has not implemented yet because the mail subject is subject to change.

testShutdownHookRegisteredToRuntime
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Test public void testShutdownHookRegisteredToRuntime() throws Throwable
   :outertype: ShutdownHookEmailModuleUnitTest

   Test whether the thread from \ :java:ref:`ShutdownHookEmailModule.getThread()`\  is registered inside the runtime shutdown hook.

testStop
^^^^^^^^

.. java:method:: @Test @Ignore public void testStop()
   :outertype: ShutdownHookEmailModuleUnitTest

   This test has not implemented yet because it is not a automated test case (it is for debugging purpose only).

