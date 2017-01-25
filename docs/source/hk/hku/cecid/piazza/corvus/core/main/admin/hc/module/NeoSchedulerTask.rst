.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: hk.hku.cecid.edi.as2 AS2Processor

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDAO

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDVO

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDataSourceDAO

.. java:import:: hk.hku.cecid.edi.as2.dao RepositoryDAO

.. java:import:: hk.hku.cecid.edi.as2.dao RepositoryDVO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao Transaction

.. java:import:: hk.hku.cecid.piazza.corvus.core.main.admin AdminMainProcessor

NeoSchedulerTask
================

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.admin.hc.module
   :noindex:

.. java:type:: public class NeoSchedulerTask extends SchedulerTask

Methods
-------
cleanAS2
^^^^^^^^

.. java:method:: @Override protected Transaction cleanAS2(int months) throws Exception
   :outertype: NeoSchedulerTask

