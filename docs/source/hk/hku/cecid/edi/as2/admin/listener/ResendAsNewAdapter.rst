.. java:import:: hk.hku.cecid.edi.as2 AS2PlusProcessor

.. java:import:: hk.hku.cecid.edi.as2.dao AS2DAOHandler

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDVO

.. java:import:: hk.hku.cecid.edi.as2.module OutgoingMessageProcessor

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.corvus.admin.listener AdminPageletAdaptor

.. java:import:: java.io PrintWriter

.. java:import:: java.io StringWriter

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.transform Source

ResendAsNewAdapter
==================

.. java:package:: hk.hku.cecid.edi.as2.admin.listener
   :noindex:

.. java:type:: public class ResendAsNewAdapter extends AdminPageletAdaptor

Methods
-------
getCenterSource
^^^^^^^^^^^^^^^

.. java:method:: protected Source getCenterSource(HttpServletRequest request)
   :outertype: ResendAsNewAdapter

