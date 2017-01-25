.. java:import:: java.net URL

.. java:import:: java.util Map

.. java:import:: java.io UnsupportedEncodingException

.. java:import:: hk.hku.cecid.piazza.commons.test.utils FixtureStore

.. java:import:: junit.framework TestCase

.. java:import:: org.junit Assert

.. java:import:: org.slf4j LoggerFactory

.. java:import:: org.slf4j Logger

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

DataFactoryUnitTest
===================

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class DataFactoryUnitTest extends TestCase

   The \ ``DataFactoryUnitTest``\  is unit test of \ ``DataFactory``\ .

   :author: Twinsen Tsang

Fields
------
AS2_ADMIN_DATA_SAMPLE0
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String AS2_ADMIN_DATA_SAMPLE0
   :outertype: DataFactoryUnitTest

AS2_MESSAGE_DATA_SAMPLE0
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String AS2_MESSAGE_DATA_SAMPLE0
   :outertype: DataFactoryUnitTest

AS2_MESSAGE_DATA_STORE0
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String AS2_MESSAGE_DATA_STORE0
   :outertype: DataFactoryUnitTest

AS2_PARTNERSHIP_DATA_LOAD0
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String AS2_PARTNERSHIP_DATA_LOAD0
   :outertype: DataFactoryUnitTest

   This is the fixture name for testing the reading capabilities for AS2Partnership in DataFactory.

AS2_PARTNERSHIP_DATA_STORE0
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String AS2_PARTNERSHIP_DATA_STORE0
   :outertype: DataFactoryUnitTest

   This is the fixture name for testing the storing capabilities for DataFactory. This fixture does not contains any data initially.

EBMS_ADMIN_DATA_SAMPLE0
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBMS_ADMIN_DATA_SAMPLE0
   :outertype: DataFactoryUnitTest

EBMS_CONFIG_DATA_SAMPLE0
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBMS_CONFIG_DATA_SAMPLE0
   :outertype: DataFactoryUnitTest

EBMS_HISTORY_QUERY_DATA_STORE0
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBMS_HISTORY_QUERY_DATA_STORE0
   :outertype: DataFactoryUnitTest

EBMS_MESSAGE_DATA_SAMPLE0
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBMS_MESSAGE_DATA_SAMPLE0
   :outertype: DataFactoryUnitTest

EBMS_MESSAGE_DATA_STORE0
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBMS_MESSAGE_DATA_STORE0
   :outertype: DataFactoryUnitTest

EBMS_PARTNERSHIP_DATA_LOAD0
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBMS_PARTNERSHIP_DATA_LOAD0
   :outertype: DataFactoryUnitTest

   This is the fixture name for testing the reading capabilities for EBMSPartnership in DataFactory.

EBMS_PARTNERSHIP_DATA_STORE0
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String EBMS_PARTNERSHIP_DATA_STORE0
   :outertype: DataFactoryUnitTest

   This is the fixture name for testing the storing capabilities for DataFactory. This fixture does not contains any data initially.

logger
^^^^^^

.. java:field:: final Logger logger
   :outertype: DataFactoryUnitTest

Methods
-------
setUp
^^^^^

.. java:method:: protected void setUp() throws Exception
   :outertype: DataFactoryUnitTest

tearDown
^^^^^^^^

.. java:method:: protected void tearDown() throws Exception
   :outertype: DataFactoryUnitTest

testCcreateEbmsMessageHistoryQueryDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testCcreateEbmsMessageHistoryQueryDataFromXML() throws Exception
   :outertype: DataFactoryUnitTest

testCreateAS2AdminData
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testCreateAS2AdminData() throws Exception
   :outertype: DataFactoryUnitTest

   Test whether the DataFactory able to load AS2 Administrator Data from the fixture *

testCreateAS2MessageData
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testCreateAS2MessageData() throws Exception
   :outertype: DataFactoryUnitTest

testCreateAS2PartnershipData
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testCreateAS2PartnershipData() throws Exception
   :outertype: DataFactoryUnitTest

   Test whether the DataFactory able to create EBMS Partnership Data from the fixture *

testCreateEBMSAdminData
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testCreateEBMSAdminData() throws Exception
   :outertype: DataFactoryUnitTest

   Test whether the DataFactory able to load EBMS Administrator Data from the fixture *

testCreateEBMSConfigData
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testCreateEBMSConfigData() throws Exception
   :outertype: DataFactoryUnitTest

testCreateEBMSPartnershipData
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testCreateEBMSPartnershipData() throws Exception
   :outertype: DataFactoryUnitTest

   Test whether the DataFactory able to create EBMS Partnership Data from the fixture *

testStoreAS2MessageData
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testStoreAS2MessageData() throws Exception
   :outertype: DataFactoryUnitTest

   Test whether the DataFactory able to store AS2 Message Data to the fixture *

testStoreAS2PartnershipData
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testStoreAS2PartnershipData() throws Exception
   :outertype: DataFactoryUnitTest

   Test whether the DataFactory able to store AS2 Partnership Data to the fixture *

testStoreEBMSMessageData
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testStoreEBMSMessageData() throws Exception
   :outertype: DataFactoryUnitTest

   Test whether the DataFactory able to store EBMS Message Data to the fixture *

testStoreEBMSPartnershipData
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testStoreEBMSPartnershipData() throws Exception
   :outertype: DataFactoryUnitTest

   Test whether the DataFactory able to store EBMS Partnership Data to the fixture *

