.. java:import:: java.io File

.. java:import:: java.net URL

.. java:import:: java.util Iterator

.. java:import:: java.util Map

.. java:import:: java.util StringTokenizer

.. java:import:: junit.framework TestCase

.. java:import:: org.slf4j Logger

.. java:import:: org.slf4j LoggerFactory

.. java:import:: sun.misc BASE64Decoder

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data KVPairData

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.test.utils FixtureStore

.. java:import:: hk.hku.cecid.piazza.commons.test.utils SimpleHttpMonitor

EnvelopQuerySenderUnitTest
==========================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class EnvelopQuerySenderUnitTest extends TestCase

   The \ ``EnvelopQuerySenderUnitTest``\  is unit test of \ ``EnvelopQuerySender``\ .

   :author: Twinsen Tsang

Fields
------
PASSWORD
^^^^^^^^

.. java:field:: public static final String PASSWORD
   :outertype: EnvelopQuerySenderUnitTest

TEST_ENDPOINT
^^^^^^^^^^^^^

.. java:field:: public static final String TEST_ENDPOINT
   :outertype: EnvelopQuerySenderUnitTest

TEST_PORT
^^^^^^^^^

.. java:field:: public static final int TEST_PORT
   :outertype: EnvelopQuerySenderUnitTest

USER_NAME
^^^^^^^^^

.. java:field:: public static final String USER_NAME
   :outertype: EnvelopQuerySenderUnitTest

kvData
^^^^^^

.. java:field:: protected KVPairData kvData
   :outertype: EnvelopQuerySenderUnitTest

logger
^^^^^^

.. java:field::  Logger logger
   :outertype: EnvelopQuerySenderUnitTest

target
^^^^^^

.. java:field:: protected EnvelopQuerySender target
   :outertype: EnvelopQuerySenderUnitTest

   The testing target which is an PartnershipSender and the associated data

testClassLogger
^^^^^^^^^^^^^^^

.. java:field:: protected FileLogger testClassLogger
   :outertype: EnvelopQuerySenderUnitTest

Methods
-------
initTestData
^^^^^^^^^^^^

.. java:method:: public void initTestData()
   :outertype: EnvelopQuerySenderUnitTest

   Initialize the test data *

initTestTarget
^^^^^^^^^^^^^^

.. java:method:: public void initTestTarget() throws Exception
   :outertype: EnvelopQuerySenderUnitTest

   Initialize the test target which is a PartnershipSender.

setUp
^^^^^

.. java:method:: public void setUp() throws Exception
   :outertype: EnvelopQuerySenderUnitTest

   Setup the fixture.

tearDown
^^^^^^^^

.. java:method:: public void tearDown() throws Exception
   :outertype: EnvelopQuerySenderUnitTest

   Stop the HTTP monitor preventing JVM port binding *

testEnvelopQuery
^^^^^^^^^^^^^^^^

.. java:method:: public void testEnvelopQuery() throws Exception
   :outertype: EnvelopQuerySenderUnitTest

   Test whether the *

testSetMessageCriteriaProperty
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testSetMessageCriteriaProperty()
   :outertype: EnvelopQuerySenderUnitTest

   Test whether the setMessageCriteriaToDownload works well under valid data. *

testSetMessageCriteriaWithInvalid
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testSetMessageCriteriaWithInvalid()
   :outertype: EnvelopQuerySenderUnitTest

   Test whether the setMessageCriteriaToDownload throw exception when second argument is invalid. *

testSetMessageCriteriaWithNull
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testSetMessageCriteriaWithNull()
   :outertype: EnvelopQuerySenderUnitTest

   Test whether the setMessageCriteriaToDownload throw exception when 1 and 2 argument is null. *

testSetMessageCriteriaWithNull2
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testSetMessageCriteriaWithNull2()
   :outertype: EnvelopQuerySenderUnitTest

   Test whether the setMessageCriteriaToDownload throw exception when second argument is null. *

