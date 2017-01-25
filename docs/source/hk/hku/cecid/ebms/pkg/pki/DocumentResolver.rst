.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io InputStream

.. java:import:: org.apache.xml.security.signature XMLSignatureInput

.. java:import:: org.apache.xml.security.utils.resolver ResourceResolverException

.. java:import:: org.apache.xml.security.utils.resolver ResourceResolverSpi

.. java:import:: org.apache.xml.security.utils.resolver ResourceResolverContext

.. java:import:: org.w3c.dom Attr

DocumentResolver
================

.. java:package:: hk.hku.cecid.ebms.pkg.pki
   :noindex:

.. java:type:: public class DocumentResolver extends ResourceResolverSpi

   This class is needed by the Apache XML Security library for locating and loading the document attachments.

   :author: kcyee

Fields
------
docs
^^^^

.. java:field:: protected DocumentDetail[] docs
   :outertype: DocumentResolver

   Internal variable for holding the document parameters.

Constructors
------------
DocumentResolver
^^^^^^^^^^^^^^^^

.. java:constructor:: public DocumentResolver(DocumentDetail[] docs)
   :outertype: DocumentResolver

   Construct with an array of document parameters.

   :param docs: array of document parameters

Methods
-------
engineCanResolveURI
^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean engineCanResolveURI(ResourceResolverContext context)
   :outertype: DocumentResolver

   Sees whether the resolver can resolve the document specified by the URI or not.

   :param uri:
   :param baseUri:
   :return: true if the resolver can locate the document specified, false if otherwise.

engineResolveURI
^^^^^^^^^^^^^^^^

.. java:method:: public XMLSignatureInput engineResolveURI(ResourceResolverContext context) throws ResourceResolverException
   :outertype: DocumentResolver

   Gets the document (encapsulated in the XMLSignatureInput object) by specifying the URI.

   :param uri:
   :param baseUri:
   :return: the document encapsulated in the XMLSignatureInput object

