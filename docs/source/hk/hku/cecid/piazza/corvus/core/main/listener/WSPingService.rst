.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPFaultException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequestException

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesAdaptor

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPElement

WSPingService
=============

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.listener
   :noindex:

.. java:type:: public class WSPingService extends WebServicesAdaptor

   WSPingService is a simple web service which provides a ping-pong function.

   :author: Hugo Y. K. Lam

Methods
-------
serviceRequested
^^^^^^^^^^^^^^^^

.. java:method:: public SOAPElement[] serviceRequested(SOAPElement[] bodies) throws SOAPRequestException
   :outertype: WSPingService

   Processes the web service ping and replies with a pong message.

   :throws SOAPRequestException: if unable to process the ping request.

