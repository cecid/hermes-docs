.. java:import:: hk.hku.cecid.ebms.pkg.validation SOAPValidationException

.. java:import:: java.util ArrayList

.. java:import:: java.util Calendar

.. java:import:: java.util Date

.. java:import:: java.util Iterator

.. java:import:: java.util TimeZone

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

MessageHeader.PartyId
=====================

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public static final class PartyId
   :outertype: MessageHeader

   A \ ``PartyId``\  inside \ ``From``\  or \ ``To``\

Constructors
------------
PartyId
^^^^^^^

.. java:constructor::  PartyId(String id, String type)
   :outertype: MessageHeader.PartyId

   Initializes \ ``PartyId``\  object

Methods
-------
getId
^^^^^

.. java:method:: public String getId()
   :outertype: MessageHeader.PartyId

   Gets party ID.

   :return: Party ID stored in this object.

getType
^^^^^^^

.. java:method:: public String getType()
   :outertype: MessageHeader.PartyId

   Gets value of the "type" attribute .

   :return: Value of the "type" attribute.

