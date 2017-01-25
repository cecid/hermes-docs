.. java:import:: hk.hku.cecid.ebms.spa.handler InboundMessageProcessor

.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.piazza.commons.test.utils FixtureStore

.. java:import:: java.io File

.. java:import:: java.lang.reflect Method

.. java:import:: java.net URL

.. java:import:: org.junit After

.. java:import:: org.junit Assert

.. java:import:: org.junit Before

.. java:import:: org.junit Test

.. java:import:: junit.framework TestCase

InboundMessageProcessorTest
===========================

.. java:package:: hk.hku.cecid.ebms.handler
   :noindex:

.. java:type:: public class InboundMessageProcessorTest extends TestCase

   The \ ``InboundMessageProcessorTest``\  is the testcase for \ ``InboundMessageProcessor``\ .

   :author: Philip Wong

   **See also:** :java:ref:`hk.hku.cecid.ebms.handler.InboundMessageProcessor`

Methods
-------
setUp
^^^^^

.. java:method:: @Before public void setUp() throws Exception
   :outertype: InboundMessageProcessorTest

tearDown
^^^^^^^^

.. java:method:: @After public void tearDown() throws Exception
   :outertype: InboundMessageProcessorTest

testCheckExpiredMessage
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Test public void testCheckExpiredMessage() throws Exception
   :outertype: InboundMessageProcessorTest

