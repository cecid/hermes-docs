.. java:import:: java.io File

.. java:import:: java.net URL

.. java:import:: hk.hku.cecid.piazza.commons.test.utils FixtureStore

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSAdminData

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSPartnershipData

EBMSPartnershipSenderUnitTest
=============================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class EBMSPartnershipSenderUnitTest extends PartnershipSenderUnitTest

   The \ ``EBMSPartnershipSenderUnitTest``\  is unit test of \ ``EBMSPartnershipSender``\ .

   :author: Twinsen Tsang

Methods
-------
initTestData
^^^^^^^^^^^^

.. java:method:: public void initTestData()
   :outertype: EBMSPartnershipSenderUnitTest

   Initialize the test data *

initTestTarget
^^^^^^^^^^^^^^

.. java:method:: public void initTestTarget() throws Exception
   :outertype: EBMSPartnershipSenderUnitTest

   Initialize the test target which is a HTTP Sender.

