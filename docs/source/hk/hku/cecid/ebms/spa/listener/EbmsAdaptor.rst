.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPHttpAdaptor

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequestException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPResponse

EbmsAdaptor
===========

.. java:package:: hk.hku.cecid.ebms.spa.listener
   :noindex:

.. java:type:: public abstract class EbmsAdaptor extends SOAPHttpAdaptor

   :author: Donahue Sze Window - Preferences - Java - Code Style - Code Templates

Methods
-------
processRequest
^^^^^^^^^^^^^^

.. java:method:: public abstract void processRequest(EbmsRequest request, EbmsResponse response) throws RequestListenerException
   :outertype: EbmsAdaptor

processRequest
^^^^^^^^^^^^^^

.. java:method:: public void processRequest(SOAPRequest soapRequest, SOAPResponse soapResponse) throws SOAPRequestException
   :outertype: EbmsAdaptor

