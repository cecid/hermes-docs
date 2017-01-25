.. java:import:: java.io InputStream

.. java:import:: junit.framework TestCase

.. java:import:: org.slf4j LoggerFactory

.. java:import:: org.slf4j Logger

.. java:import:: hk.hku.cecid.piazza.commons.test.utils FixtureStore

PartnershipOpVeriferUnitTest
============================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class PartnershipOpVeriferUnitTest extends TestCase

   The \ ``PartnershipOpVeriferUnitTest``\  is unit test of \ ``PartnershipOpVerifer``\ .

   :author: Twinsen Tsang

Fields
------
ADDOP_SUCCESS_SAMPLE
^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String ADDOP_SUCCESS_SAMPLE
   :outertype: PartnershipOpVeriferUnitTest

DELETEOP_SUCCESS_SAMPLE
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String DELETEOP_SUCCESS_SAMPLE
   :outertype: PartnershipOpVeriferUnitTest

ERROR_SAMPLE_0
^^^^^^^^^^^^^^

.. java:field:: public static final String ERROR_SAMPLE_0
   :outertype: PartnershipOpVeriferUnitTest

ERROR_SAMPLE_1
^^^^^^^^^^^^^^

.. java:field:: public static final String ERROR_SAMPLE_1
   :outertype: PartnershipOpVeriferUnitTest

UPDATEOP_SUCCESS_SAMPLE
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static final String UPDATEOP_SUCCESS_SAMPLE
   :outertype: PartnershipOpVeriferUnitTest

logger
^^^^^^

.. java:field::  Logger logger
   :outertype: PartnershipOpVeriferUnitTest

Methods
-------
initTestTarget
^^^^^^^^^^^^^^

.. java:method:: public void initTestTarget() throws Exception
   :outertype: PartnershipOpVeriferUnitTest

   Initialize the test target which is a Partnership Operation Verifier.

setUp
^^^^^

.. java:method:: public void setUp() throws Exception
   :outertype: PartnershipOpVeriferUnitTest

   Setup the fixture.

tearDown
^^^^^^^^

.. java:method:: public void tearDown() throws Exception
   :outertype: PartnershipOpVeriferUnitTest

   Setup the fixture.

testValidateAddSuccess
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testValidateAddSuccess() throws Exception
   :outertype: PartnershipOpVeriferUnitTest

   Test whether the validation process execute property for add operation executed properly. *

testValidateDeleteSuccess
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testValidateDeleteSuccess() throws Exception
   :outertype: PartnershipOpVeriferUnitTest

   Test whether the validation process execute property for delete operation executed properly. *

testValidateUpdateSuccess
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testValidateUpdateSuccess() throws Exception
   :outertype: PartnershipOpVeriferUnitTest

   Test whether the validation process execute property for update operation executed properly. *

testValidateWithErrorSample0
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testValidateWithErrorSample0() throws Exception
   :outertype: PartnershipOpVeriferUnitTest

   Test whether the validation process throw exception when the HTML content violate the field constraint (this case, 'Retry Interval must be integer');

testValidateWithErrorSample1
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testValidateWithErrorSample1() throws Exception
   :outertype: PartnershipOpVeriferUnitTest

   Test whether the validation process throw exception when the HTML content violate the field constraint (this case, 'CPA ID cannot be empty');

testValidateWithNullStream
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void testValidateWithNullStream() throws Exception
   :outertype: PartnershipOpVeriferUnitTest

   Test whether it throws exception when null stream is passed as arugment *

