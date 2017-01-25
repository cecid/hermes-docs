.. java:import:: java.io BufferedReader

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io File

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io InputStreamReader

.. java:import:: java.io OutputStream

.. java:import:: java.net URL

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap MessageFactory

.. java:import:: javax.xml.soap MimeHeaders

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPMessage

.. java:import:: org.apache.commons.fileupload RequestContext

.. java:import:: org.junit After

.. java:import:: org.junit Before

.. java:import:: org.junit Test

.. java:import:: org.slf4j Logger

.. java:import:: org.slf4j LoggerFactory

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSMessageHistoryRequestData

.. java:import:: hk.hku.cecid.corvus.ws EBMSMessageHistoryQuerySender

.. java:import:: hk.hku.cecid.corvus.ws.data KVPairData

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.test.utils FixtureStore

.. java:import:: hk.hku.cecid.piazza.commons.test.utils SimpleSoapMonitor

.. java:import:: junit.framework Assert

.. java:import:: junit.framework TestCase

EBMSMessageHistoryQuerySenderTest
=================================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class EBMSMessageHistoryQuerySenderTest extends TestCase

Fields
------
PASSWORD
^^^^^^^^

.. java:field:: public static final String PASSWORD
   :outertype: EBMSMessageHistoryQuerySenderTest

TEST_ENDPOINT
^^^^^^^^^^^^^

.. java:field:: public static final String TEST_ENDPOINT
   :outertype: EBMSMessageHistoryQuerySenderTest

TEST_PORT
^^^^^^^^^

.. java:field:: public static final int TEST_PORT
   :outertype: EBMSMessageHistoryQuerySenderTest

USER_NAME
^^^^^^^^^

.. java:field:: public static final String USER_NAME
   :outertype: EBMSMessageHistoryQuerySenderTest

kvData
^^^^^^

.. java:field:: protected KVPairData kvData
   :outertype: EBMSMessageHistoryQuerySenderTest

logger
^^^^^^

.. java:field::  Logger logger
   :outertype: EBMSMessageHistoryQuerySenderTest

target
^^^^^^

.. java:field:: protected EBMSMessageHistoryQuerySender target
   :outertype: EBMSMessageHistoryQuerySenderTest

   The testing target which is an PartnershipSender and the associated data

testClassLogger
^^^^^^^^^^^^^^^

.. java:field:: protected FileLogger testClassLogger
   :outertype: EBMSMessageHistoryQuerySenderTest

Methods
-------
initTest
^^^^^^^^

.. java:method:: public void initTest() throws Exception
   :outertype: EBMSMessageHistoryQuerySenderTest

setUp
^^^^^

.. java:method:: @Before public void setUp() throws Exception
   :outertype: EBMSMessageHistoryQuerySenderTest

   Setup the fixture.

tearDown
^^^^^^^^

.. java:method:: @After public void tearDown() throws Exception
   :outertype: EBMSMessageHistoryQuerySenderTest

testFail_NegativeQueryLimit
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Test public void testFail_NegativeQueryLimit() throws Exception
   :outertype: EBMSMessageHistoryQuerySenderTest

testNormalCriteriaData
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Test public void testNormalCriteriaData() throws Exception
   :outertype: EBMSMessageHistoryQuerySenderTest

testNullCriteriaData
^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Test public void testNullCriteriaData() throws Exception
   :outertype: EBMSMessageHistoryQuerySenderTest

testSpecialCharacterCriteriaData
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Test public void testSpecialCharacterCriteriaData() throws Exception
   :outertype: EBMSMessageHistoryQuerySenderTest

testWildcardCriteriaData
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Test public void testWildcardCriteriaData() throws Exception
   :outertype: EBMSMessageHistoryQuerySenderTest

