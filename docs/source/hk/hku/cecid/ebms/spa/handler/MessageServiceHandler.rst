.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.pkg SignatureException

.. java:import:: hk.hku.cecid.ebms.pkg SignatureHandler

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.listener EbmsRequest

.. java:import:: hk.hku.cecid.ebms.spa.listener EbmsResponse

.. java:import:: hk.hku.cecid.piazza.commons.module ActiveModule

.. java:import:: hk.hku.cecid.piazza.commons.security KeyStoreManagementException

.. java:import:: hk.hku.cecid.piazza.commons.security KeyStoreTrustManager

.. java:import:: java.security.cert Certificate

.. java:import:: java.util Properties

MessageServiceHandler
=====================

.. java:package:: hk.hku.cecid.ebms.spa.handler
   :noindex:

.. java:type:: public class MessageServiceHandler

   EbxmlMessageDAOConvertor Service Handler that supports asynchronous communication and reliable messaging.

   :author: cyng

Fields
------
INBOX
^^^^^

.. java:field:: public String INBOX
   :outertype: MessageServiceHandler

OUTBOX
^^^^^^

.. java:field:: public String OUTBOX
   :outertype: MessageServiceHandler

PEEK_THREAD_COUNT
^^^^^^^^^^^^^^^^^

.. java:field:: public String PEEK_THREAD_COUNT
   :outertype: MessageServiceHandler

THREAD_COUNT
^^^^^^^^^^^^

.. java:field:: public String THREAD_COUNT
   :outertype: MessageServiceHandler

messageServiceHandler_destroyFlag
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static boolean messageServiceHandler_destroyFlag
   :outertype: MessageServiceHandler

messageServiceHandler_initFlag
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: static boolean messageServiceHandler_initFlag
   :outertype: MessageServiceHandler

popFolder
^^^^^^^^^

.. java:field:: public String popFolder
   :outertype: MessageServiceHandler

popHost
^^^^^^^

.. java:field:: public String popHost
   :outertype: MessageServiceHandler

popPassword
^^^^^^^^^^^

.. java:field:: public String popPassword
   :outertype: MessageServiceHandler

popPort
^^^^^^^

.. java:field:: public String popPort
   :outertype: MessageServiceHandler

popProtocol
^^^^^^^^^^^

.. java:field:: public String popProtocol
   :outertype: MessageServiceHandler

popUsername
^^^^^^^^^^^

.. java:field:: public String popUsername
   :outertype: MessageServiceHandler

smtpFromMailAddress
^^^^^^^^^^^^^^^^^^^

.. java:field:: public String smtpFromMailAddress
   :outertype: MessageServiceHandler

smtpHost
^^^^^^^^

.. java:field:: public String smtpHost
   :outertype: MessageServiceHandler

smtpPassword
^^^^^^^^^^^^

.. java:field:: public String smtpPassword
   :outertype: MessageServiceHandler

smtpPort
^^^^^^^^

.. java:field:: public String smtpPort
   :outertype: MessageServiceHandler

smtpProtocol
^^^^^^^^^^^^

.. java:field:: public String smtpProtocol
   :outertype: MessageServiceHandler

smtpUsername
^^^^^^^^^^^^

.. java:field:: public String smtpUsername
   :outertype: MessageServiceHandler

Methods
-------
createSignatureHandler
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static SignatureHandler createSignatureHandler(EbxmlMessage message) throws SignatureException
   :outertype: MessageServiceHandler

createSignatureHandler
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static SignatureHandler createSignatureHandler(EbxmlMessage message, Certificate certificate) throws SignatureException
   :outertype: MessageServiceHandler

destroy
^^^^^^^

.. java:method:: public synchronized void destroy()
   :outertype: MessageServiceHandler

getInstance
^^^^^^^^^^^

.. java:method:: public static synchronized MessageServiceHandler getInstance()
   :outertype: MessageServiceHandler

isHasPop
^^^^^^^^

.. java:method:: public boolean isHasPop()
   :outertype: MessageServiceHandler

   :return: Returns the hasPop.

isHasSmtp
^^^^^^^^^

.. java:method:: public boolean isHasSmtp()
   :outertype: MessageServiceHandler

   :return: Returns the hasSmtp.

isInboundAgreementCheck
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isInboundAgreementCheck()
   :outertype: MessageServiceHandler

   :return: Returns the isInboundAgreementCheck.

isOutboundAgreementCheck
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isOutboundAgreementCheck()
   :outertype: MessageServiceHandler

   :return: Returns the isOutboundAgreementCheck.

isSignHeaderOnly
^^^^^^^^^^^^^^^^

.. java:method:: public boolean isSignHeaderOnly()
   :outertype: MessageServiceHandler

   :return: Returns the isSignHeaderOnly.

processInboundMessage
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void processInboundMessage(EbmsRequest request, EbmsResponse response) throws MessageServiceHandlerException
   :outertype: MessageServiceHandler

processOutboundMessage
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void processOutboundMessage(EbmsRequest request, EbmsResponse response) throws MessageServiceHandlerException
   :outertype: MessageServiceHandler

