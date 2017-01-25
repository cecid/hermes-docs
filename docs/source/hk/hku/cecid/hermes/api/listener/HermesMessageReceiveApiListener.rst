.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io InputStream

.. java:import:: java.io IOException

.. java:import:: java.util ArrayList

.. java:import:: java.util HashMap

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: java.util Map

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.soap AttachmentPart

.. java:import:: javax.xml.soap SOAPException

.. java:import:: org.apache.commons.codec.binary Base64

.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageServerDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDVO

.. java:import:: hk.hku.cecid.ebms.spa.handler EbxmlMessageDAOConvertor

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageClassifier

.. java:import:: hk.hku.cecid.ebms.spa.task MessageValidationException

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.json JsonParseException

.. java:import:: hk.hku.cecid.piazza.commons.rest RestRequest

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: hk.hku.cecid.hermes.api Constants

.. java:import:: hk.hku.cecid.hermes.api ErrorCode

.. java:import:: hk.hku.cecid.hermes.api.spa ApiPlugin

HermesMessageReceiveApiListener
===============================

.. java:package:: hk.hku.cecid.hermes.api.listener
   :noindex:

.. java:type:: public class HermesMessageReceiveApiListener extends HermesProtocolApiListener

   HermesMessageReceiveApiListener

   :author: Patrick Yee

Fields
------
MAX_NUMBER
^^^^^^^^^^

.. java:field:: public static int MAX_NUMBER
   :outertype: HermesMessageReceiveApiListener

Methods
-------
processGetRequest
^^^^^^^^^^^^^^^^^

.. java:method:: protected Map<String, Object> processGetRequest(RestRequest request) throws RequestListenerException
   :outertype: HermesMessageReceiveApiListener

processPostRequest
^^^^^^^^^^^^^^^^^^

.. java:method:: protected Map<String, Object> processPostRequest(RestRequest request) throws RequestListenerException
   :outertype: HermesMessageReceiveApiListener

