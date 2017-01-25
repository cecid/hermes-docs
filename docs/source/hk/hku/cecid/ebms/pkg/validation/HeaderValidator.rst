.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.pkg MessageHeader

.. java:import:: hk.hku.cecid.ebms.pkg PayloadContainer

.. java:import:: java.util HashSet

.. java:import:: java.util Iterator

.. java:import:: java.util Set

.. java:import:: java.net URI

.. java:import:: java.net URISyntaxException

HeaderValidator
===============

.. java:package:: hk.hku.cecid.ebms.pkg.validation
   :noindex:

.. java:type:: public class HeaderValidator

   Class for validating the header of an ebXML message. \ ``EbxmlValidationException``\  will be thrown in case of error.

   :author: Frankie Lam

Methods
-------
validate
^^^^^^^^

.. java:method:: public void validate(EbxmlMessage ebxmlMessage) throws EbxmlValidationException
   :outertype: HeaderValidator

   Validate the header of an ebXML message.

   :param ebxmlMessage: The header of the \ ``EbxmlMessage``\  object to be validated.

validatePartyId
^^^^^^^^^^^^^^^

.. java:method:: protected void validatePartyId(Iterator partyIds) throws EbxmlValidationException
   :outertype: HeaderValidator

   Validates the list of party IDs. The following rules are enforced:

   ..

   * Attribute "type" MUST be unique within the list of party IDs.
   * The party ID without the "type" attribute MUST be a URI.

   :param partyIds:

validatePayload
^^^^^^^^^^^^^^^

.. java:method:: protected void validatePayload(EbxmlMessage ebxmlMessage) throws EbxmlValidationException
   :outertype: HeaderValidator

   Validate payload. The following checks are applied: - All payload references with "cid:" as the prefix must exist. - All payload references must be a valid URI.

validateService
^^^^^^^^^^^^^^^

.. java:method:: protected void validateService(String service, String serviceType) throws EbxmlValidationException
   :outertype: HeaderValidator

   Validate service element. The following rules are enforced: - Service attribute must be a URI in the absence of type attribute.

   :param service:

validateURI
^^^^^^^^^^^

.. java:method:: protected boolean validateURI(String uri)
   :outertype: HeaderValidator

   Check if a URI is valid.

   :param uri: URI in string format to be validated.
   :return: true if the URI is valid; false otherwise.

