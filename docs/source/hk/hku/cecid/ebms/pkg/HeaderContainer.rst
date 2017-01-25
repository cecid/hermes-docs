.. java:import:: hk.hku.cecid.ebms.pkg.validation SOAPValidationException

.. java:import:: java.util ArrayList

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPBody

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

.. java:import:: javax.xml.soap SOAPHeader

.. java:import:: javax.xml.soap SOAPPart

HeaderContainer
===============

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type::  class HeaderContainer

   An encapsulation of the Header Container of an \ ``EbxmlMessage``\ .

   :author: cyng

Constructors
------------
HeaderContainer
^^^^^^^^^^^^^^^

.. java:constructor::  HeaderContainer(SOAPPart soapPart) throws SOAPException
   :outertype: HeaderContainer

   Creates a \ ``HeaderContainer``\  using the specified \ ``SOAPPart``\

Methods
-------
addExtensionElement
^^^^^^^^^^^^^^^^^^^

.. java:method::  void addExtensionElement(ExtensionElement extensionElement) throws SOAPException
   :outertype: HeaderContainer

   Add an \ ``ExtensionElement``\ , e.g. \ ``MessageHeader``\  (a \ ``HeaderElement``\ ) or \ ``Manifest``\  (a \ ``BodyElement``\ ), to this \ ``HeaderContainer``\

getAckRequested
^^^^^^^^^^^^^^^

.. java:method::  AckRequested getAckRequested()
   :outertype: HeaderContainer

getAcknowledgment
^^^^^^^^^^^^^^^^^

.. java:method::  Acknowledgment getAcknowledgment()
   :outertype: HeaderContainer

getErrorList
^^^^^^^^^^^^

.. java:method::  ErrorList getErrorList()
   :outertype: HeaderContainer

getManifest
^^^^^^^^^^^

.. java:method::  Manifest getManifest()
   :outertype: HeaderContainer

getMessageHeader
^^^^^^^^^^^^^^^^

.. java:method::  MessageHeader getMessageHeader()
   :outertype: HeaderContainer

getMessageOrder
^^^^^^^^^^^^^^^

.. java:method::  MessageOrder getMessageOrder()
   :outertype: HeaderContainer

getSignatures
^^^^^^^^^^^^^

.. java:method::  Iterator getSignatures()
   :outertype: HeaderContainer

getStatusRequest
^^^^^^^^^^^^^^^^

.. java:method::  StatusRequest getStatusRequest()
   :outertype: HeaderContainer

getStatusResponse
^^^^^^^^^^^^^^^^^

.. java:method::  StatusResponse getStatusResponse()
   :outertype: HeaderContainer

getSyncReply
^^^^^^^^^^^^

.. java:method::  SyncReply getSyncReply()
   :outertype: HeaderContainer

