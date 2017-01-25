SOAPRequestListener
===================

.. java:package:: hk.hku.cecid.piazza.commons.soap
   :noindex:

.. java:type:: public interface SOAPRequestListener

   SOAPRequestListener is a listener for handling SOAP requests.

   :author: Hugo Y. K. Lam

Methods
-------
processRequest
^^^^^^^^^^^^^^

.. java:method:: public void processRequest(SOAPRequest request, SOAPResponse response) throws SOAPRequestException
   :outertype: SOAPRequestListener

   Processes the SOAP request.

   :param request: the SOAP request.
   :param response: the SOAP response.
   :throws SOAPRequestException: if there is any error in processing the SOAP request.

