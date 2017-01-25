.. java:import:: java.io File

.. java:import:: java.net URL

.. java:import:: hk.hku.cecid.piazza.commons.test.utils FixtureStore

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data AS2AdminData

.. java:import:: hk.hku.cecid.corvus.ws.data AS2PartnershipData

AS2PartnershipSenderUnitTest
============================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class AS2PartnershipSenderUnitTest extends PartnershipSenderUnitTest

   The \ ``AS2PartnershipSenderUnitTest``\  is unit test of \ ``AS2PartnershipSender``\ .

   :author: Twinsen Tsang

Methods
-------
initTestData
^^^^^^^^^^^^

.. java:method:: public void initTestData()
   :outertype: AS2PartnershipSenderUnitTest

   Initialize the test data *

initTestTarget
^^^^^^^^^^^^^^

.. java:method:: public void initTestTarget() throws Exception
   :outertype: AS2PartnershipSenderUnitTest

   Initialize the test target which is a HTTP Sender.

