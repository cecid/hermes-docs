.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageServiceHandler

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

EbmsInboundListener
===================

.. java:package:: hk.hku.cecid.ebms.spa.listener
   :noindex:

.. java:type:: public class EbmsInboundListener extends EbmsAdaptor

   :author: Donahue Sze

Methods
-------
listenerCreated
^^^^^^^^^^^^^^^

.. java:method:: public void listenerCreated() throws RequestListenerException
   :outertype: EbmsInboundListener

   Handles event for servlet start up

listenerDestroyed
^^^^^^^^^^^^^^^^^

.. java:method:: public void listenerDestroyed() throws RequestListenerException
   :outertype: EbmsInboundListener

processRequest
^^^^^^^^^^^^^^

.. java:method:: public void processRequest(EbmsRequest request, EbmsResponse response) throws RequestListenerException
   :outertype: EbmsInboundListener

