.. java:import:: hk.hku.cecid.edi.as2 AS2PlusProcessor

.. java:import:: hk.hku.cecid.edi.as2.dao PartnershipDAO

.. java:import:: hk.hku.cecid.edi.as2.dao PartnershipDVO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: hk.hku.cecid.piazza.corvus.admin.listener AdminPageletAdaptor

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.security MessageDigest

.. java:import:: java.security.cert CertificateException

.. java:import:: java.security.cert CertificateFactory

.. java:import:: java.security.cert X509Certificate

.. java:import:: java.util Hashtable

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.transform Source

.. java:import:: org.apache.commons.fileupload DiskFileUpload

.. java:import:: org.apache.commons.fileupload FileItem

.. java:import:: org.apache.commons.fileupload FileUpload

.. java:import:: org.apache.commons.fileupload FileUploadException

PartnershipPageletAdaptor
=========================

.. java:package:: hk.hku.cecid.edi.as2.admin.listener
   :noindex:

.. java:type:: public class PartnershipPageletAdaptor extends AdminPageletAdaptor

   :author: Donahue Sze

Methods
-------
getCenterSource
^^^^^^^^^^^^^^^

.. java:method:: protected Source getCenterSource(HttpServletRequest request)
   :outertype: PartnershipPageletAdaptor

getHashtable
^^^^^^^^^^^^

.. java:method:: public Hashtable getHashtable(HttpServletRequest request) throws FileUploadException, IOException
   :outertype: PartnershipPageletAdaptor

