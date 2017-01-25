.. java:import:: java.io File

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: java.net URL

.. java:import:: java.util Iterator

.. java:import:: java.util Map

.. java:import:: java.util HashMap

.. java:import:: java.util LinkedHashMap

.. java:import:: junit.framework TestCase

.. java:import:: org.apache.commons.fileupload FileItemIterator

.. java:import:: org.apache.commons.fileupload FileItemStream

.. java:import:: org.apache.commons.fileupload FileUpload

.. java:import:: org.apache.commons.fileupload RequestContext

.. java:import:: org.slf4j Logger

.. java:import:: org.slf4j LoggerFactory

.. java:import:: sun.misc BASE64Decoder

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data KVPairData

.. java:import:: hk.hku.cecid.piazza.commons.test.utils FixtureStore

.. java:import:: hk.hku.cecid.piazza.commons.test.utils SimpleHttpMonitor

PartnershipSenderUnitTest
=========================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class PartnershipSenderUnitTest extends TestCase

   The \ ``PartnershipSenderUnitTest``\  is unit test of \ ``PartnershipSender``\ . TODO: Inadequate Test-case for error path.

   :author: Twinsen Tsang

Fields
------
PASSWORD
^^^^^^^^

.. java:field:: public static final String PASSWORD
   :outertype: PartnershipSenderUnitTest

TEST_ENDPOINT
^^^^^^^^^^^^^

.. java:field:: public static final String TEST_ENDPOINT
   :outertype: PartnershipSenderUnitTest

TEST_PORT
^^^^^^^^^

.. java:field:: public static final int TEST_PORT
   :outertype: PartnershipSenderUnitTest

USER_NAME
^^^^^^^^^

.. java:field:: public static final String USER_NAME
   :outertype: PartnershipSenderUnitTest

kvData
^^^^^^

.. java:field:: protected KVPairData kvData
   :outertype: PartnershipSenderUnitTest

logger
^^^^^^

.. java:field::  Logger logger
   :outertype: PartnershipSenderUnitTest

target
^^^^^^

.. java:field:: protected PartnershipSender target
   :outertype: PartnershipSenderUnitTest

   The testing target which is an PartnershipSender and the associated data

testClassLogger
^^^^^^^^^^^^^^^

.. java:field:: protected FileLogger testClassLogger
   :outertype: PartnershipSenderUnitTest

Methods
-------
initTestData
^^^^^^^^^^^^

.. java:method:: public void initTestData()
   :outertype: PartnershipSenderUnitTest

   Initialize the test data *

initTestTarget
^^^^^^^^^^^^^^

.. java:method:: public void initTestTarget() throws Exception
   :outertype: PartnershipSenderUnitTest

   Initialize the test target which is a PartnershipSender.

setUp
^^^^^

.. java:method:: public void setUp() throws Exception
   :outertype: PartnershipSenderUnitTest

   Setup the fixture.

tearDown
^^^^^^^^

.. java:method:: public void tearDown() throws Exception
   :outertype: PartnershipSenderUnitTest

   Stop the HTTP monitor preventing JVM port binding *

testAddPartnership
^^^^^^^^^^^^^^^^^^

.. java:method:: public void testAddPartnership() throws Exception
   :outertype: PartnershipSenderUnitTest

   Test whether the add partnership request operation perform correctly *

testDeletePartnership
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testDeletePartnership() throws Exception
   :outertype: PartnershipSenderUnitTest

   Test whether the update partnership request operation perform correctly *

testUpdatePartnership
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testUpdatePartnership() throws Exception
   :outertype: PartnershipSenderUnitTest

   Test whether the update partnership request operation perform correctly *

