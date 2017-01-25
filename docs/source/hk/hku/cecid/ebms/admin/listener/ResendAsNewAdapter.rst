.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDVO

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageClassifier

.. java:import:: hk.hku.cecid.ebms.spa.handler OutboundMessageProcessor

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.corvus.admin.listener AdminPageletAdaptor

.. java:import:: java.io PrintWriter

.. java:import:: java.io StringWriter

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.transform Source

ResendAsNewAdapter
==================

.. java:package:: hk.hku.cecid.ebms.admin.listener
   :noindex:

.. java:type:: public class ResendAsNewAdapter extends AdminPageletAdaptor

Methods
-------
getCenterSource
^^^^^^^^^^^^^^^

.. java:method:: protected Source getCenterSource(HttpServletRequest request)
   :outertype: ResendAsNewAdapter

