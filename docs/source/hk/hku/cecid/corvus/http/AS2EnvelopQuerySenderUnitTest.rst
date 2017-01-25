.. java:import:: java.io File

.. java:import:: java.io InputStream

.. java:import:: java.net URL

.. java:import:: hk.hku.cecid.piazza.commons.test.utils FixtureStore

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.corvus.http EnvelopQuerySenderUnitTest

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data AS2AdminData

AS2EnvelopQuerySenderUnitTest
=============================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class AS2EnvelopQuerySenderUnitTest extends EnvelopQuerySenderUnitTest

   The \ ``AS2EnvelopQuerySenderUnitTest``\  is unit test of \ ``AS2EnvelopQuerySender``\ .

   :author: Twinsen Tsang

Methods
-------
initTestData
^^^^^^^^^^^^

.. java:method:: public void initTestData()
   :outertype: AS2EnvelopQuerySenderUnitTest

   Initialize the test data *

initTestTarget
^^^^^^^^^^^^^^

.. java:method:: public void initTestTarget() throws Exception
   :outertype: AS2EnvelopQuerySenderUnitTest

   Initialize the test target which is a PartnershipSender.

testEnvelopQuery
^^^^^^^^^^^^^^^^

.. java:method:: public void testEnvelopQuery() throws Exception
   :outertype: AS2EnvelopQuerySenderUnitTest

