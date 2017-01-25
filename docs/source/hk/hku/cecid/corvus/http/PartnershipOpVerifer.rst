.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.net ConnectException

.. java:import:: javax.xml.parsers SAXParser

.. java:import:: javax.xml.parsers SAXParserFactory

.. java:import:: javax.xml.parsers ParserConfigurationException

.. java:import:: org.slf4j LoggerFactory

.. java:import:: org.slf4j Logger

.. java:import:: org.xml.sax Attributes

.. java:import:: org.xml.sax SAXException

.. java:import:: org.xml.sax.helpers DefaultHandler

.. java:import:: org.w3c.tidy Tidy

PartnershipOpVerifer
====================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class PartnershipOpVerifer

   The \ ``PartnershipOpVerifer``\  is an helper class for verifying whether the partnership operation has been executed successfully. Since H2O does not have any build-in SOAP-based web service for managing the partnerships under remote behavior, The PartnershipOpVerifer acts as a validator for validating the \ **HTML content**\  returning from the H2O administration web page.  The main method of this class is \ :java:ref:`validate(InputStream)`\  and the arugment is the input stream. The input stream SHOULD contains the HTML content after you executed add/delete/update partnership in either AS2/EBMS partnership administration page.

   :author: Twinsen Tsang

Fields
------
OP_ADD_SUCCESS
^^^^^^^^^^^^^^

.. java:field:: public static final String OP_ADD_SUCCESS
   :outertype: PartnershipOpVerifer

OP_DELETE_SUCCESS
^^^^^^^^^^^^^^^^^

.. java:field:: public static final String OP_DELETE_SUCCESS
   :outertype: PartnershipOpVerifer

OP_NO
^^^^^

.. java:field:: public static final String OP_NO
   :outertype: PartnershipOpVerifer

OP_UPDATE_SUCCESS
^^^^^^^^^^^^^^^^^

.. java:field:: public static final String OP_UPDATE_SUCCESS
   :outertype: PartnershipOpVerifer

logger
^^^^^^

.. java:field:: final Logger logger
   :outertype: PartnershipOpVerifer

Constructors
------------
PartnershipOpVerifer
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public PartnershipOpVerifer()
   :outertype: PartnershipOpVerifer

   Default constructor.

Methods
-------
validate
^^^^^^^^

.. java:method:: public void validate(InputStream ins) throws SAXException, ParserConfigurationException
   :outertype: PartnershipOpVerifer

   Validate the HTML content received after executed partnership operation. The content is passed as a input stream \ ``ins``\ .  This operation is quite expensive because it first transform the whole HTML content received to a well-formed XHTML before parsing by the SAX Parser.

   :param ins: The HTML content to validate the result of partnership operation
   :throws SAXException: ..

   #. When unable to down-load the HTML DTD from the web. Check your Internet connectivity
   #. When IO related problems occur
   :throws ParserConfigurationException: When SAX parser mis-configures.

