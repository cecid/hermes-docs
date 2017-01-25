.. java:import:: java.io InputStream

.. java:import:: org.w3c.dom Document

.. java:import:: org.w3c.dom Element

XMLDSigner
==========

.. java:package:: hk.hku.cecid.ebms.pkg.pki
   :noindex:

.. java:type:: public interface XMLDSigner

   This interface defines a standard way to have the document signed. Different classes will implement the interface using different library behind.

   :author: kcyee

Methods
-------
addDocument
^^^^^^^^^^^

.. java:method:: public void addDocument(String uri, InputStream is, String contentType)
   :outertype: XMLDSigner

   Adds a reference to a document attachment to the signature.

   :param uri: the URI of the document attachment
   :param is: the input stream of the content of the document
   :param contentType: the content type of the document

getElement
^^^^^^^^^^

.. java:method:: public Element getElement()
   :outertype: XMLDSigner

   Gets the DOM element of the signature generated.

   :return: the DOM element of the signature

setEnvelope
^^^^^^^^^^^

.. java:method:: public void setEnvelope(Document doc) throws SignException
   :outertype: XMLDSigner

   Set the envelope to host the Signature element. That is the XML document where the Signature element to be added. The digital signature here will always be an enveloped signature. The envelope will be included in the process of signing.

   :param doc: the XML document to host the Signature element
   :throws SignException:

setTrustAnchor
^^^^^^^^^^^^^^

.. java:method:: public void setTrustAnchor(CompositeKeyStore ks)
   :outertype: XMLDSigner

   Sets the trust anchor for verfication of certificate path.

   :param ks: the keystore providing the trusted certificates

sign
^^^^

.. java:method:: public void sign(CompositeKeyStore ks, String alias, char[] password) throws SignException
   :outertype: XMLDSigner

   Signs the envelope and documents by using the specified key in the keystore.

   :param ks: the keystore holding the key for signing
   :param alias: the alias of the key for signing
   :param password: the password for accessing the key for signing
   :throws SignException: when there is any error in the processing of signing

verify
^^^^^^

.. java:method:: public boolean verify() throws VerifyException
   :outertype: XMLDSigner

   Verifies the signature in the envelope passed in, which may reference the documents specified using the addDocument method.

   :throws VerifyException: when there is any error in the processing of verification
   :return: true if the signature can be verified successfully, false if otherwise.

