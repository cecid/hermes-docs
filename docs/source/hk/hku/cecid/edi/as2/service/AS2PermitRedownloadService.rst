.. java:import:: hk.hku.cecid.edi.as2 AS2Exception

.. java:import:: hk.hku.cecid.edi.as2 AS2PlusProcessor

.. java:import:: hk.hku.cecid.edi.as2.util AS2MessageStatusReverser

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPFaultException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPRequestException

.. java:import:: hk.hku.cecid.piazza.commons.soap SOAPResponse

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesAdaptor

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesRequest

.. java:import:: hk.hku.cecid.piazza.commons.soap WebServicesResponse

.. java:import:: javax.xml.soap SOAPBodyElement

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPException

AS2PermitRedownloadService
==========================

.. java:package:: hk.hku.cecid.edi.as2.service
   :noindex:

.. java:type:: public class AS2PermitRedownloadService extends WebServicesAdaptor

Fields
------
NAMESPACE
^^^^^^^^^

.. java:field:: public static String NAMESPACE
   :outertype: AS2PermitRedownloadService

Methods
-------
serviceRequested
^^^^^^^^^^^^^^^^

.. java:method:: public void serviceRequested(WebServicesRequest request, WebServicesResponse response) throws SOAPException, DAOException, SOAPFaultException
   :outertype: AS2PermitRedownloadService

