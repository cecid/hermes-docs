.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDVO

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao PartnershipDVO

.. java:import:: hk.hku.cecid.ebms.spa.handler EbxmlMessageDAOConvertor

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageClassifier

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: java.net MalformedURLException

.. java:import:: java.net URL

AgreementHandler
================

.. java:package:: hk.hku.cecid.ebms.spa.task
   :noindex:

.. java:type:: public class AgreementHandler

   :author: Donahue Sze

Constructors
------------
AgreementHandler
^^^^^^^^^^^^^^^^

.. java:constructor:: public AgreementHandler(MessageDVO message, boolean isCheckAgreement) throws MessageValidationException, DAOException
   :outertype: AgreementHandler

AgreementHandler
^^^^^^^^^^^^^^^^

.. java:constructor:: public AgreementHandler(EbxmlMessage ebxmlMessage, String messageBox, String messageType, boolean isCheckAgreement) throws MessageValidationException, DAOException
   :outertype: AgreementHandler

Methods
-------
getActor
^^^^^^^^

.. java:method:: public String getActor()
   :outertype: AgreementHandler

   :return: Returns the actor.

getDsAlgorithm
^^^^^^^^^^^^^^

.. java:method:: public String getDsAlgorithm()
   :outertype: AgreementHandler

   :return: Returns the dsAlgorithm.

getEncryptAlgorithm
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getEncryptAlgorithm()
   :outertype: AgreementHandler

   :return: Returns the encryptAlgorithm.

getEncryptCert
^^^^^^^^^^^^^^

.. java:method:: public byte[] getEncryptCert()
   :outertype: AgreementHandler

   :return: Returns the encryptCert.

getMdAlgorithm
^^^^^^^^^^^^^^

.. java:method:: public String getMdAlgorithm()
   :outertype: AgreementHandler

   :return: Returns the mdAlgorithm.

getRetries
^^^^^^^^^^

.. java:method:: public int getRetries()
   :outertype: AgreementHandler

   :return: Returns the retries.

getRetryInterval
^^^^^^^^^^^^^^^^

.. java:method:: public int getRetryInterval()
   :outertype: AgreementHandler

   :return: Returns the retryInterval.

getSignCert
^^^^^^^^^^^

.. java:method:: public byte[] getSignCert()
   :outertype: AgreementHandler

   :return: Returns the signCert.

getToPartyProtocol
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getToPartyProtocol()
   :outertype: AgreementHandler

   :return: Returns the toPartyProtocol.

getToPartyURL
^^^^^^^^^^^^^

.. java:method:: public URL getToPartyURL()
   :outertype: AgreementHandler

   :return: Returns the toPartyURL.

isEncrypt
^^^^^^^^^

.. java:method:: public boolean isEncrypt()
   :outertype: AgreementHandler

   :return: Returns the isEncrypt.

isHostnameVerified
^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isHostnameVerified()
   :outertype: AgreementHandler

   :return: Returns the isHostnameVerified.

isSign
^^^^^^

.. java:method:: public boolean isSign()
   :outertype: AgreementHandler

   :return: Returns the isSign.

