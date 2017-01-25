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

ShutdownHookEmailModuleUnitTest.CreateShudownHookWorkerAssertionThread
======================================================================

.. java:package:: hk.hku.cecid.piazza.commons.swallow
   :noindex:

.. java:type:: public static class CreateShudownHookWorkerAssertionThread extends Thread
   :outertype: ShutdownHookEmailModuleUnitTest

Constructors
------------
CreateShudownHookWorkerAssertionThread
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public CreateShudownHookWorkerAssertionThread(Properties assertionProperties, Thread shutdownThread)
   :outertype: ShutdownHookEmailModuleUnitTest.CreateShudownHookWorkerAssertionThread

Methods
-------
run
^^^

.. java:method:: public void run()
   :outertype: ShutdownHookEmailModuleUnitTest.CreateShudownHookWorkerAssertionThread

