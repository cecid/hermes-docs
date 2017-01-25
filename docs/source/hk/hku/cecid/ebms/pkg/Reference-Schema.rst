.. java:import:: hk.hku.cecid.ebms.pkg.validation SOAPValidationException

.. java:import:: java.util ArrayList

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap Name

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPEnvelope

.. java:import:: javax.xml.soap SOAPException

Reference.Schema
================

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public static final class Schema
   :outertype: Reference

   A \ ``Schema``\  inside a \ ``Reference``\  [ebMSS 3.2.1.1]. The schema is not necessarily an XML or DTD schema; it can be any kind of schema such as Database schema.

Constructors
------------
Schema
^^^^^^

.. java:constructor::  Schema(String location, String version)
   :outertype: Reference.Schema

   Initializes the schema object using given location and version inforamtion.

   :param location: URI of the schema.
   :param version: Version identifier of the schema.

Methods
-------
getLocation
^^^^^^^^^^^

.. java:method:: public String getLocation()
   :outertype: Reference.Schema

   Get the location URI of the schema.

   :return: URI of the schema.

getVersion
^^^^^^^^^^

.. java:method:: public String getVersion()
   :outertype: Reference.Schema

   Get version identifier oif the schema.

   :return: Version identifier of the schema.

