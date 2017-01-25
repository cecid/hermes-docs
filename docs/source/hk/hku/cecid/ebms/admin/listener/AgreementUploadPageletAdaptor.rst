.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDVO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.module ComponentException

.. java:import:: hk.hku.cecid.piazza.commons.security SMimeMessage

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: hk.hku.cecid.piazza.commons.util UtilitiesException

.. java:import:: hk.hku.cecid.piazza.corvus.admin.listener AdminPageletAdaptor

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: java.util Date

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.transform Source

.. java:import:: javax.xml.datatype DatatypeFactory

.. java:import:: javax.xml.datatype Duration

.. java:import:: org.apache.commons.fileupload DiskFileUpload

.. java:import:: org.apache.commons.fileupload FileItem

.. java:import:: org.apache.commons.fileupload FileUpload

.. java:import:: org.dom4j DocumentException

AgreementUploadPageletAdaptor
=============================

.. java:package:: hk.hku.cecid.ebms.admin.listener
   :noindex:

.. java:type:: public class AgreementUploadPageletAdaptor extends AdminPageletAdaptor

   :author: Donahue Sze

Fields
------
X_ATTR_PARTY_NAME
^^^^^^^^^^^^^^^^^

.. java:field::  String X_ATTR_PARTY_NAME
   :outertype: AgreementUploadPageletAdaptor

X_CAN_SEND
^^^^^^^^^^

.. java:field::  String X_CAN_SEND
   :outertype: AgreementUploadPageletAdaptor

X_CHANNEL_ID
^^^^^^^^^^^^

.. java:field::  String X_CHANNEL_ID
   :outertype: AgreementUploadPageletAdaptor

X_COLLABORATION_PROTOCOL_AGREEMENT
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field::  String X_COLLABORATION_PROTOCOL_AGREEMENT
   :outertype: AgreementUploadPageletAdaptor

X_COLLABORATION_ROLE
^^^^^^^^^^^^^^^^^^^^

.. java:field::  String X_COLLABORATION_ROLE
   :outertype: AgreementUploadPageletAdaptor

X_DELIVERY_CHANNEL
^^^^^^^^^^^^^^^^^^

.. java:field::  String X_DELIVERY_CHANNEL
   :outertype: AgreementUploadPageletAdaptor

X_DOC_EXCHANGE
^^^^^^^^^^^^^^

.. java:field::  String X_DOC_EXCHANGE
   :outertype: AgreementUploadPageletAdaptor

X_EBXML_SENDER_BINDING
^^^^^^^^^^^^^^^^^^^^^^

.. java:field::  String X_EBXML_SENDER_BINDING
   :outertype: AgreementUploadPageletAdaptor

X_ENDPOINT
^^^^^^^^^^

.. java:field::  String X_ENDPOINT
   :outertype: AgreementUploadPageletAdaptor

X_MESSAGING_CHARACTERISTICS
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field::  String X_MESSAGING_CHARACTERISTICS
   :outertype: AgreementUploadPageletAdaptor

X_PARTY_INFO
^^^^^^^^^^^^

.. java:field::  String X_PARTY_INFO
   :outertype: AgreementUploadPageletAdaptor

X_RELIABLE_MESSAGING
^^^^^^^^^^^^^^^^^^^^

.. java:field::  String X_RELIABLE_MESSAGING
   :outertype: AgreementUploadPageletAdaptor

X_SENDER_DIGITAL_ENVELOPE
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field::  String X_SENDER_DIGITAL_ENVELOPE
   :outertype: AgreementUploadPageletAdaptor

X_SENDER_NON_REPUDIATION
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field::  String X_SENDER_NON_REPUDIATION
   :outertype: AgreementUploadPageletAdaptor

X_SERVICE
^^^^^^^^^

.. java:field::  String X_SERVICE
   :outertype: AgreementUploadPageletAdaptor

X_SERVICE_BINDING
^^^^^^^^^^^^^^^^^

.. java:field::  String X_SERVICE_BINDING
   :outertype: AgreementUploadPageletAdaptor

X_THIS_PARTY_ACTION_BINDING
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field::  String X_THIS_PARTY_ACTION_BINDING
   :outertype: AgreementUploadPageletAdaptor

X_TP_NAMESPACE
^^^^^^^^^^^^^^

.. java:field::  String X_TP_NAMESPACE
   :outertype: AgreementUploadPageletAdaptor

X_TRANSPORT
^^^^^^^^^^^

.. java:field::  String X_TRANSPORT
   :outertype: AgreementUploadPageletAdaptor

X_TRANSPORT_RECEIVER
^^^^^^^^^^^^^^^^^^^^

.. java:field::  String X_TRANSPORT_RECEIVER
   :outertype: AgreementUploadPageletAdaptor

selectedPartyName
^^^^^^^^^^^^^^^^^

.. java:field::  String selectedPartyName
   :outertype: AgreementUploadPageletAdaptor

Methods
-------
getCenterSource
^^^^^^^^^^^^^^^

.. java:method:: protected Source getCenterSource(HttpServletRequest request)
   :outertype: AgreementUploadPageletAdaptor

