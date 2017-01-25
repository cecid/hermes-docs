.. java:import:: java.net URLClassLoader

.. java:import:: java.util Properties

.. java:import:: hk.hku.cecid.piazza.commons.module Module

.. java:import:: hk.hku.cecid.piazza.commons.module ModuleException

.. java:import:: hk.hku.cecid.piazza.commons.swallow ShutdownHookEmailThread

.. java:import:: hk.hku.cecid.piazza.commons.util Instance

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

ShutdownHookEmailModule
=======================

.. java:package:: hk.hku.cecid.piazza.commons.swallow
   :noindex:

.. java:type:: public class ShutdownHookEmailModule extends Module

   The ShutdownHookEmailModule is a piazza common module which send email to the specified when the JVM is terminated. It is typical used to notify the operator for the termination of long-running java process like application server (for instance, Tomcat) through email. Background about this: This component is emerged when project swallow requires the detection of application crashes and therefore we want a reusable generic component for doing such.  Sample Module Descriptor

   .. parsed-literal::

      <module id="shutdown.email.module" name="Email shutdown hook module">
       <parameters>
        <parameter name="host" value="intraflow2.cs.hku.hk"/>
        <parameter name="protocol" value="smtp"/>
        <parameter name="username" value=""/>
        <parameter name="password" value=""/>
        <parameter name="from" value="yourDaemon@cecid.hku.hk"/>
        <parameter name="to" value="yourEmailAddress"/>
        <parameter name="cc" value="yourCCEmailAddress"/>
        <parameter name="verbose" value="false"/>
       </parameters>
      </module>

   :author: Twinsen Tsang

Constructors
------------
ShutdownHookEmailModule
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public ShutdownHookEmailModule(String descriptorLocation, boolean shouldInitialize)
   :outertype: ShutdownHookEmailModule

   Creates a new instance of \ ``ShutdownHookEmailModule``\ .

   :param descriptorLocation: the module descriptor.
   :throws ModuleException: if errors encountered when loading the module descriptor.

ShutdownHookEmailModule
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public ShutdownHookEmailModule(String descriptorLocation, ClassLoader loader, boolean shouldInitialize)
   :outertype: ShutdownHookEmailModule

   Creates a new instance of \ ``ShutdownHookEmailModule``\ .

   :param descriptorLocation: the module descriptor.
   :param shouldInitialize: true if the module should be initialized.
   :throws ModuleException: if errors encountered when loading the module descriptor.

ShutdownHookEmailModule
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public ShutdownHookEmailModule(String descriptorLocation, ClassLoader loader)
   :outertype: ShutdownHookEmailModule

   Creates a new instance of \ ``ShutdownHookEmailModule``\ .

   :param descriptorLocation: the module descriptor.
   :param loader: the class loader for this module.
   :throws ModuleException: if errors encountered when loading the module descriptor.

ShutdownHookEmailModule
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public ShutdownHookEmailModule(String descriptorLocation)
   :outertype: ShutdownHookEmailModule

   Creates a new instance of \ ``ShutdownHookEmailModule``\ .

   :param descriptorLocation: the module descriptor.

Methods
-------
createShutdownHookWorker
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @SuppressWarnings protected Thread createShutdownHookWorker() throws Throwable
   :outertype: ShutdownHookEmailModule

   Create the thread executed during JVM shutdown. By default, it create an new instance of ShutdownHookEmailThread associated with the property defined in this module descriptor. The thread created must conform the rule specified in the Java API. For detail, read \ `here <http://java.sun.com/j2se/1.5.0/docs/api/java/lang/Runtime.html#addShutdownHook(java.lang.Thread)>`_\

   :throws Throwable: any kind of execution for setup the shutdown hook worker.
   :return: The thread executed during JVM shutdown

getThread
^^^^^^^^^

.. java:method:: protected Thread getThread()
   :outertype: ShutdownHookEmailModule

init
^^^^

.. java:method:: @Override public void init()
   :outertype: ShutdownHookEmailModule

   Invoked for initialization. Wire up all property from the XML.

stop
^^^^

.. java:method:: public synchronized void stop()
   :outertype: ShutdownHookEmailModule

   A special hack for remove the shutdown hook registered during the \ :java:ref:`init()`\  phrase of this module. This is used for testing the module only. You rarely call this in your application.

