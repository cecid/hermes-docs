.. java:import:: java.util HashMap

.. java:import:: java.util Map

.. java:import:: javax.activation DataHandler

.. java:import:: javax.activation DataSource

PayloadContainer
================

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class PayloadContainer

   An encapsulation of the payload container in an \ ``EbxmlMessage``\  [ebMSS 2.1.4].

   A Payload Container contains an ebXML MIME header as well as application payload, as illustrated in the following diagram:

   1. Content-ID:
   2. Content-type: application/xml
   3.
   4.<PurchaseOrder>
   5.  <Product>...</Product>
   6.  ...
   7.</PurchaseOrder>
   Line 1-2: ebXML MIME headers. Line 4-7: Application payload

   This class encapsulates the structure of payload container in an ebXML message.

   :author: cyng

Fields
------
HREF_PREFIX
^^^^^^^^^^^

.. java:field:: public static final String HREF_PREFIX
   :outertype: PayloadContainer

   The prefix of "href" attribute of this \ ``PayloadContainer``\ .

Constructors
------------
PayloadContainer
^^^^^^^^^^^^^^^^

.. java:constructor:: public PayloadContainer(DataHandler dataHandler, String contentId, Reference reference)
   :outertype: PayloadContainer

   Create a \ ``PayloadContainer``\  from the specified \ ``DataHandler``\ .

Methods
-------
getContentId
^^^^^^^^^^^^

.. java:method:: public String getContentId()
   :outertype: PayloadContainer

   Get contentId.

getContentLength
^^^^^^^^^^^^^^^^

.. java:method:: public long getContentLength()
   :outertype: PayloadContainer

   Get the content length of this payload. Note that the content length returned will be -1 if this container is not created from AttachmentDataSource. Also, the length returned does not take Content-Transfer-Encoding into account, if any.

   :return: content length of this payload

getContentType
^^^^^^^^^^^^^^

.. java:method:: public String getContentType()
   :outertype: PayloadContainer

   Get content type of this attachment.

getDataHandler
^^^^^^^^^^^^^^

.. java:method:: public DataHandler getDataHandler()
   :outertype: PayloadContainer

   Get \ ``javax.activation.DataHandler``\  of this attachment.

getHref
^^^^^^^

.. java:method:: public String getHref()
   :outertype: PayloadContainer

   Get "href" attribute which is equal to the prefixed contentId.

getMimeHeaders
^^^^^^^^^^^^^^

.. java:method:: public Map getMimeHeaders()
   :outertype: PayloadContainer

getReference
^^^^^^^^^^^^

.. java:method:: public Reference getReference()
   :outertype: PayloadContainer

   Get \ ``Reference``\  inside the \ ``Manifest``\  associated with this \ ``PayloadContainer``\ .

setMimeHeader
^^^^^^^^^^^^^

.. java:method:: public void setMimeHeader(String name, String value)
   :outertype: PayloadContainer

