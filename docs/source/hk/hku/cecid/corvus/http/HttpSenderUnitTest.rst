.. java:import:: java.io File

.. java:import:: java.io InputStream

.. java:import:: java.net URL

.. java:import:: java.net MalformedURLException

.. java:import:: java.util Map

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: java.util ArrayList

.. java:import:: junit.framework TestCase

.. java:import:: sun.misc BASE64Encoder

.. java:import:: org.slf4j LoggerFactory

.. java:import:: org.slf4j Logger

.. java:import:: org.apache.http.client.methods HttpPost

.. java:import:: org.apache.http.client.methods HttpRequestBase

.. java:import:: org.apache.http NameValuePair

.. java:import:: org.apache.http.message BasicNameValuePair

.. java:import:: org.apache.http.client.entity UrlEncodedFormEntity

.. java:import:: org.apache.http.entity.mime MultipartEntityBuilder

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.test.utils FixtureStore

.. java:import:: hk.hku.cecid.piazza.commons.test.utils SimpleHttpMonitor

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data KVPairData

HttpSenderUnitTest
==================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class HttpSenderUnitTest extends TestCase

   The \ ``HttpSenderUnitTest``\  is unit test of \ ``HttpSender``\ . TODO: Inadequate Test-case for testing looping.

   :author: Twinsen Tsang

Fields
------
TEST_ENDPOINT
^^^^^^^^^^^^^

.. java:field:: public static final String TEST_ENDPOINT
   :outertype: HttpSenderUnitTest

TEST_PORT
^^^^^^^^^

.. java:field:: public static final int TEST_PORT
   :outertype: HttpSenderUnitTest

logger
^^^^^^

.. java:field::  Logger logger
   :outertype: HttpSenderUnitTest

Methods
-------
initTestTarget
^^^^^^^^^^^^^^

.. java:method:: public void initTestTarget() throws Exception
   :outertype: HttpSenderUnitTest

   Initialize the test target which is a HTTP Sender.

setUp
^^^^^

.. java:method:: public void setUp() throws Exception
   :outertype: HttpSenderUnitTest

   Setup the fixture.

tearDown
^^^^^^^^

.. java:method:: public void tearDown() throws Exception
   :outertype: HttpSenderUnitTest

   Stop the HTTP monitor preventing JVM port binding *

testLoopTimeProperty
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testLoopTimeProperty()
   :outertype: HttpSenderUnitTest

   Test \ :java:ref:`HttpSender.getLoopTimes()`\  and \ :java:ref:`HttpSender.setLoopTimes(int)`\  *

testSendWithBasicAuthentication
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testSendWithBasicAuthentication() throws Exception
   :outertype: HttpSenderUnitTest

   Test wether the HTTP sender able to send the HTTP header with 'Authorization' header.

testSendWithMultipart
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testSendWithMultipart() throws Exception
   :outertype: HttpSenderUnitTest

   Test whether the HTTP sender able to send the HTTP header with multi-part to our monitor successfully.

testSendWithNoContent
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testSendWithNoContent() throws Exception
   :outertype: HttpSenderUnitTest

   Test whether the HTTP sender able to send the HTTP header to our monitor successfully.

testSendWithParameter
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testSendWithParameter() throws Exception
   :outertype: HttpSenderUnitTest

   Test whether the HTTP sender able to send the HTTP header with POST parameter to our monitor successfully.

testServiceEndpointProperty
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testServiceEndpointProperty() throws MalformedURLException
   :outertype: HttpSenderUnitTest

   Test \ :java:ref:`HttpSender.setServiceEndPoint(URL)`\  *

testServiceEndpointPropertyWithInvalidData
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testServiceEndpointPropertyWithInvalidData() throws MalformedURLException
   :outertype: HttpSenderUnitTest

   Test whether \ :java:ref:`HttpSender.setServiceEndPoint(String)`\  with invalid data.

testUserObjectProperty
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testUserObjectProperty()
   :outertype: HttpSenderUnitTest

   Test \ :java:ref:`HttpSender.getUserObject()`\  *

