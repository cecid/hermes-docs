.. java:import:: java.io BufferedReader

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: java.io StringReader

.. java:import:: javax.mail.internet MimeMessage

.. java:import:: javax.mail.internet MimeUtility

.. java:import:: javax.xml.soap MessageFactory

.. java:import:: javax.xml.soap MimeHeaders

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPMessage

.. java:import:: javax.xml.soap SOAPConstants

.. java:import:: hk.hku.cecid.piazza.commons.net ConnectionException

.. java:import:: hk.hku.cecid.piazza.commons.test.utils FixtureStore

.. java:import:: org.junit After

.. java:import:: org.junit Assert

.. java:import:: org.junit Before

.. java:import:: org.junit Test

.. java:import:: junit.framework TestCase

SOAPMailSenderTest
==================

.. java:package:: hk.hku.cecid.piazza.commons.soap
   :noindex:

.. java:type:: public class SOAPMailSenderTest extends TestCase

Methods
-------
setUp
^^^^^

.. java:method:: @Before public void setUp() throws Exception
   :outertype: SOAPMailSenderTest

tearDown
^^^^^^^^

.. java:method:: @After public void tearDown() throws Exception
   :outertype: SOAPMailSenderTest

testCreatedMessage
^^^^^^^^^^^^^^^^^^

.. java:method:: @Test public void testCreatedMessage() throws Exception
   :outertype: SOAPMailSenderTest

testCreatedMessageLineMaxLimit
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: @Test public void testCreatedMessageLineMaxLimit()
   :outertype: SOAPMailSenderTest

