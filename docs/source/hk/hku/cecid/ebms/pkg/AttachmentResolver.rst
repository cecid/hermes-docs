.. java:import:: org.apache.xml.security.signature XMLSignatureInput

.. java:import:: org.apache.xml.security.utils.resolver ResourceResolverException

.. java:import:: org.apache.xml.security.utils.resolver ResourceResolverSpi

.. java:import:: org.apache.xml.security.utils.resolver ResourceResolverContext

.. java:import:: org.w3c.dom Attr

AttachmentResolver
==================

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type::  class AttachmentResolver extends ResourceResolverSpi

   A \ ``ResourceResolver``\  implementation used by Apache Security library. The URI in the \ ``Reference``\  element of a digital signature points to some internal or external resources. This \ ``AttachmentResolver``\  is used to provide the resources in the \ ``EbxmlMessage``\  payload attachments and also the \ ``SOAPPart``\  itself with Reference URI="".

   :author: cyng

Constructors
------------
AttachmentResolver
^^^^^^^^^^^^^^^^^^

.. java:constructor::  AttachmentResolver(EbxmlMessage ebxmlMessage)
   :outertype: AttachmentResolver

Methods
-------
engineCanResolveURI
^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean engineCanResolveURI(ResourceResolverContext context)
   :outertype: AttachmentResolver

engineResolveURI
^^^^^^^^^^^^^^^^

.. java:method:: public XMLSignatureInput engineResolveURI(ResourceResolverContext context) throws ResourceResolverException
   :outertype: AttachmentResolver

