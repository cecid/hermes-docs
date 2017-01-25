.. java:import:: java.io IOException

.. java:import:: java.util ArrayList

.. java:import:: java.util HashMap

.. java:import:: java.util List

.. java:import:: java.util Map

.. java:import:: javax.activation DataHandler

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.soap SOAPException

.. java:import:: org.apache.commons.codec.binary Base64

.. java:import:: hk.hku.cecid.ebms.spa EbmsUtility

.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.pkg MessageHeader

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDVO

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageClassifier

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageServiceHandler

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageServiceHandlerException

.. java:import:: hk.hku.cecid.ebms.spa.listener EbmsRequest

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.json JsonParseException

.. java:import:: hk.hku.cecid.piazza.commons.rest RestRequest

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: hk.hku.cecid.piazza.commons.activation ByteArrayDataSource

.. java:import:: hk.hku.cecid.piazza.commons.util Generator

.. java:import:: hk.hku.cecid.hermes.api Constants

.. java:import:: hk.hku.cecid.hermes.api ErrorCode

.. java:import:: hk.hku.cecid.hermes.api.spa ApiPlugin

HermesMessageSendApiListener
============================

.. java:package:: hk.hku.cecid.hermes.api.listener
   :noindex:

.. java:type:: public class HermesMessageSendApiListener extends HermesProtocolApiListener

   HermesMessageSendApiListener

   :author: Patrick Yee

Methods
-------
processGetRequest
^^^^^^^^^^^^^^^^^

.. java:method:: protected Map<String, Object> processGetRequest(RestRequest request) throws RequestListenerException
   :outertype: HermesMessageSendApiListener

processPostRequest
^^^^^^^^^^^^^^^^^^

.. java:method:: protected Map<String, Object> processPostRequest(RestRequest request) throws RequestListenerException
   :outertype: HermesMessageSendApiListener

