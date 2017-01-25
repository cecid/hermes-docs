.. java:import:: hk.hku.cecid.ebms.pkg.pki CertResolver

.. java:import:: java.io IOException

.. java:import:: java.security KeyStoreException

.. java:import:: java.security NoSuchAlgorithmException

.. java:import:: java.security NoSuchProviderException

.. java:import:: java.security PublicKey

.. java:import:: java.security.cert Certificate

.. java:import:: java.security.cert CertificateException

.. java:import:: java.util Iterator

.. java:import:: javax.net.ssl X509TrustManager

.. java:import:: javax.xml.soap SOAPException

SignatureHandler
================

.. java:package:: hk.hku.cecid.ebms.pkg
   :noindex:

.. java:type:: public class SignatureHandler

   :author: Donahue Sze

Constructors
------------
SignatureHandler
^^^^^^^^^^^^^^^^

.. java:constructor:: public SignatureHandler(EbxmlMessage message, String username, char[] password, String keyStoreLocation, X509TrustManager trustman) throws SignatureException
   :outertype: SignatureHandler

SignatureHandler
^^^^^^^^^^^^^^^^

.. java:constructor:: public SignatureHandler(EbxmlMessage message, Certificate cert) throws SignatureException
   :outertype: SignatureHandler

Methods
-------
sign
^^^^

.. java:method:: public void sign() throws SOAPException, SignatureException
   :outertype: SignatureHandler

   Sign this \ ``EbxmlMessage``\  with XML signature

   :throws SOAPException:
   :throws SignatureException:

sign
^^^^

.. java:method:: public void sign(String algorithm) throws SOAPException, SignatureException
   :outertype: SignatureHandler

   Sign this \ ``EbxmlMessage``\  with XML signature

   :param algorithm: Specifies the algorithm used to generate the digital signature. Refer to \ ` XML-Signature Syntax and Processing: Algorithm Identifiers and Implementation Requirements  <http://www.w3.org/TR/2002/REC-xmldsig-core-20020212/#sec-AlgID>`_\  for details.
   :throws SOAPException:
   :throws SignatureException:

sign
^^^^

.. java:method:: public void sign(String algorithm, String digestAlgorithm, boolean signEnvelopeOnly) throws SOAPException, SignatureException
   :outertype: SignatureHandler

   Sign this \ ``EbxmlMessage``\  with XML signature

   :param algorithm: Specifies the algorithm used to generate the digital signature. Refer to \ ` XML-Signature Syntax and Processing: Algorithm Identifiers and Implementation Requirements  <http://www.w3.org/TR/2002/REC-xmldsig-core-20020212/#sec-AlgID>`_\  for details.
   :param signEnvelopeOnly: whether it should sign the envelope only, without signing the payload.
   :param digestAlgorithm: Description of the Parameter
   :throws SOAPException:
   :throws SignatureException:

verify
^^^^^^

.. java:method:: public boolean verify() throws SOAPException, SignatureException
   :outertype: SignatureHandler

   Verify the message using trusted keystore.

   :throws SOAPException:
   :throws SignatureException:
   :return: true if the digital signature is valid; false otherwise.

verifyByPublicKey
^^^^^^^^^^^^^^^^^

.. java:method:: public boolean verifyByPublicKey() throws SOAPException, SignatureException
   :outertype: SignatureHandler

