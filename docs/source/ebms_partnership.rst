.. _ebms_partnership:

Reference of ebMS 2.0 Partnership configuration
===============================================

ebMS 2.0 Partnership parameter
------------------------------

Here is the summary of the ebMS 2.0 Partnership parameter.

1. `Partnership ID`_
#. `CPA ID`_
#. `Service`_
#. `Action`_
#. `Disabled`_
#. `Transport Endpoint`_
#. `Hostname Verified in SSL?`_
#. `Sync Reply Mode`_
#. `Acknowledgement Requested`_
#. `Acknowledgement Signed Requested`_
#. `Duplicate Elimination`_
#. `Message Order`_
#. `Signing Required?`_
#. `Encryption Required? (Mail Only)`_
#. `Certificate For Encryption`_
#. `Maximum Retries`_
#. `Retry Interval (ms)`_
#. `Certificate For Verification`_

Partnership ID
^^^^^^^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | The unique identifier of the ebMS 2.0 partnership in local Hermes 2.                                             |
|                 |                                                                                                                  |
|                 | The value of this field has no restriction but **RECOMMENDED** to be an identifier between sender and recipient. |
|                 |                                                                                                                  |
|                 | It is **mandatory** and it's maximum length of this field is 255.                                                |
|                 |                                                                                                                  |
+-----------------+------------------------------------------------------------------------------------------------------------------+

CPA ID
^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | The CPA (Collaboration Protocol Agreement) ID. It is a string that identifies the parameters governing the       |
|                 | exchange of messages between the parties. The recipient of a message **MUST** be able to resolve the CPA ID to   |
|                 | an individual set of parameters, taking into account the sender of the message.                                  |
|                 |                                                                                                                  |
|                 | Simply said, it is just an arbitary and mandatory string that can be used to identify sender and recipient.      |
|                 |                                                                                                                  |
|                 | See [OASIS ebXML Messaging Service Spec v2.0] for detail.                                                        |
+-----------------+------------------------------------------------------------------------------------------------------------------+

Service
^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | In Hermes 2, the Service parameter is used for Partnership mapping between **Sender** and **Recipient**. And it  |
|                 | should follow URN format (Uniform Resource Naming).                                                              |
+-----------------+------------------------------------------------------------------------------------------------------------------+

Action
^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | It identifies a process within a Service that processes the ebMS message. Action SHALL be unique within the      |
|                 | Service in which it is defined. The value of the Action element is specified by the designer of the service.     |
|                 | It is mandatory and it's maximum length of this field is 255.                                                    |
+-----------------+------------------------------------------------------------------------------------------------------------------+

Disabled
^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | The boolean option indicates whether the partnership is disabled or not.                                         |
|                 |                                                                                                                  |
|                 | Disabled partnership does not deliver / receive any outgoing message / incoming respectively.                    |
+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ **true** = disabled ], [ **false** = enabled ]                                                                 |
+-----------------+------------------------------------------------------------------------------------------------------------------+

Transport Endpoint
^^^^^^^^^^^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | The endpoint URL of the recipient message gateway.                                                               |
|                 |                                                                                                                  |
|                 | If the recipient message gateway is Hermes 2 and using HTTP/HTTPS as transport protocol, the endpoint URL is     |
|                 | formatted as http://<RECIPIENT HOST>:<PORT>/corvus/httpd/ebms/inbound.                                           |
|                 |                                                                                                                  |
|                 | Otherwise, if the recipient host is SMTP gateway, the endpoint URL is formatted as mailto:<EMAIL ADDRESS>.       |
|                 |                                                                                                                  |
|                 | It is **mandatory** and the format MUST be a **HTTP/HTTPS URL/EMAIL ADDRESS**.                                   |
+-----------------+------------------------------------------------------------------------------------------------------------------+

Hostname Verified in SSL?
^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | The boolean flag indicates whether HTTP SSL/TLS protocol is used and required verifying the recipient hostname.  |
|                 |                                                                                                                  |
|                 | It is relevant if **HTTPS** transport protocol is set under the Transport Endpoint                               |
+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ **true** = hostname verified using SSL , **false** = none ]                                                    |
+-----------------+------------------------------------------------------------------------------------------------------------------+

Sync Reply Mode
^^^^^^^^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the receiver should reply the incoming ebMS message in same HTTP/HTTPS connection the sender   |
|                 | uses for delivery.                                                                                               |
|                 |                                                                                                                  |
|                 | This parameter is only applied to HTTP/HTTPS protocol and applicable for sending partnership.                    |
|                 |                                                                                                                  |
+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ **mshSignalsOnly** = synchronous reply ], [ **none** = asynchronous reply ]                                    |
+-----------------+------------------------------------------------------------------------------------------------------------------+

An example of synchronous reply from the recipient:
ebMS message acknowledgement is included in the HTTP/SOAP response when synchronous reply is applied.

.. image:: /_static/images/first_step/ebms-send-sync.png


An example of asynchronous reply from the recipient:
ebMS message acknowledgement will be delivered through another HTTP/SOAP connection from the recipient to the sender.

.. image:: /_static/images/first_step/ebms-send-async.png

Acknowledgement Requested
^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the recipient is requested to send an ebMS acknowledgment back to the sender.                  |
|                 |                                                                                                                  |
|                 | Both sender and recipient MUST enable this (by setting to **always**) for interoperability of this features,     |
|                 | otherwise the recipient returns the negative acknowledgment.                                                     |
|                 |                                                                                                                  |
|                 | An acknowledgment is a kind of ebMS Message which has <acknowledgment> element. It is an receipt that recipient  |
|                 | sends back to the sender after receiving an ebMS message.                                                        |
|                 |                                                                                                                  |
|                 | The mode of acknowledgment sending back depends on the value Sync Reply Mode. If Sync Reply Mode is enabled, the |
|                 | acknowledgment will return immediately in the same HTTP connection. If the recipient is Hermes 2, the            |
|                 | acknolwedgment will be put in an outgoing queue and keep waiting until it is delivered to the sender.            |
|                 |                                                                                                                  |
|                 | It is **RECOMMENDED** to set this parameter to **always** for reliable messaging.                                |
+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ always = acknowledgment requested ], [ none = acknowledgment does not request ]                                |
+-----------------+------------------------------------------------------------------------------------------------------------------+

Acknowledgement Signed Requested
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the recipient MUST sign the ebMS acknowledgment digitally using its private key before         |
|                  | delivering back to the sender.                                                                                   |
|                  |                                                                                                                  |
|                  | Both sender and recipient MUST enable this (by setting to true) for interoperability of this features.           |
|                  |                                                                                                                  |
|                  | Otherwise the recipient returns negative acknowledgment.                                                         |
|                  |                                                                                                                  |
|                  | The format of the private key **SHOULD BE** in PKCS12 and the signatures created is conformed to W3C XML         |
|                  | Signatures Specification [XMLDsig].                                                                              |
|                  |                                                                                                                  |
|                  | The sender partnership MUST set Acknowledgment Requested always from recipient for running this features         |
|                  | properly.                                                                                                        |
|                  |                                                                                                                  |
|                  | Also, the recipient is required to provide the public certificate for verifying the signature in the             |  
|                  | acknowledgment.                                                                                                  |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Dependencies** | [ **Acknowledgment Requested** = always ],                                                                       |
|                  |                                                                                                                  |
|                  | [ **Certificate For Verification REQUIRED** ]                                                                    |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Options**      | [ **true** = acknowledgment MUST be digitally signed ],                                                          |
|                  |                                                                                                                  |
|                  | [ **false** = acknolwedgment MUST not be digitally signed ]                                                      |
+------------------+------------------------------------------------------------------------------------------------------------------+
                     
Duplicate Elimination
^^^^^^^^^^^^^^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the recipient ignores duplicate message received.                                              |
|                 |                                                                                                                  |
|                 | Both sender and recipient MUST enable this (by setting to **always**) for interoperability of this features.     |
|                 | Otherwise the recipient returns negative acknowledgment.                                                         |
+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ **always** = ignores duplicate message. ],                                                                     |
|                 |                                                                                                                  |
|                 | [ **never** = delivers duplicate message. ]                                                                      |
+-----------------+------------------------------------------------------------------------------------------------------------------+

Message Order
^^^^^^^^^^^^^

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the recipient **MUST** receive ebMS messages in the same sequence as external application /    |
|                  | client first requested Hermes 2 to send through web service.                                                     |
|                  |                                                                                                                  |
|                  | Both sender and recipient MUST enable this (by setting to **Guaranteed**) for interoperability of this features. |
|                  | Otherwise the recipient returns negative acknowledgment.                                                         |
|                  |                                                                                                                  |
|                  | For example, if the external application / client has requested sender Hermes 2 to deliver 10 ebMS messages      |
|                  | in order using **Message Order**. The order of received messages in recipient SHOULD be the same as the          |
|                  | application / client requested to sender Hermes 2.                                                               |
|                  |                                                                                                                  |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Dependencies** | [ **Sync Reply Mode** = none ],                                                                                  |
|                  |                                                                                                                  |
|                  | [ **Acknowledgment Requested** = always ],                                                                       |
|                  |                                                                                                                  |
|                  | [ **Duplicate Elimination** = always ]                                                                           |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Options**      | [ **Guaranteed** = The recipient receives ebMS messages in the order of sending. ],                              |
|                  |                                                                                                                  |
|                  | [ **NotGuaranteed** = The recipient receives in best effort behavior. ]                                          |
+------------------+------------------------------------------------------------------------------------------------------------------+
                                                                                                                                                                                                                                                                      
Signing Required?
^^^^^^^^^^^^^^^^^

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the sender **MUST** sign the ebMS Message digitally using its private key.                     |
|                  |                                                                                                                  |
|                  | Both sender and recipient MUST enable this (by setting to **true**) for interoperability of this features,       |
|                  | otherwise the recipient returns negative acknowledgment.                                                         | 
|                  |                                                                                                                  |
|                  | The format of the private key **SHOULD BE** in PKCS12 and the signature created is conformed to W3C XML          |
|                  | Signatures Specification [XMLDsig].                                                                              |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Options**      | [ **true** = The outgoing ebMS message MUST be digitally signed. ],                                              |
|                  |                                                                                                                  |
|                  | [ **false** = The outgoing ebMS message does not require to sign digitally. ]                                    |
+------------------+------------------------------------------------------------------------------------------------------------------+

Encryption Required? (Mail Only)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the sender **MUST** encrypt the ebMS Message using recipient's public certificate defined in   |
|                  | Certificate for Encryption.                                                                                      |
|                  |                                                                                                                  |
|                  | It is applicable only when using **SMTP** protocol, Transport Endpoint started with mailto:                      |
|                  |                                                                                                                  |
|                  | The encryption method is based on S/MIME standard.                                                               |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Dependencies** | [ **Transport Endpoint** = started with mailto: ],                                                               |
|                  |                                                                                                                  |
|                  | [ **Sync Reply Mode** = none ],                                                                                  |
|                  |                                                                                                                  |
|                  | [ **Certificate For Encryption REQUIRED** ]                                                                      |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Options**      | [ **true** = The outgoing normal/payload ebMS message MUST be encrypted. ],                                      |
|                  |                                                                                                                  |
|                  | [ **false** = The outgoing ebMS message does not require to encrypt. ]                                           |
+------------------+------------------------------------------------------------------------------------------------------------------+

Certificate For Encryption
^^^^^^^^^^^^^^^^^^^^^^^^^^

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | The certificate file for encrypting the outgoing ebMS message through SMTP protocol by using the public key      |
|                  | generated by recipient.                                                                                          |
|                  |                                                                                                                  |
|                  | For recipient, it should use the keystore in ebMS plugin to export the public certificate for sender.            |
|                  | ebMS default keystore location: :samp:`{<HERMES2 HOME>}/plugins/hk.hku.cecid.ebms/security`                      |
|                  |                                                                                                                  |
|                  | The certificate **MUST** be in X.509 format. See Encryption Required for details.                                |
+------------------+------------------------------------------------------------------------------------------------------------------+

Maximum Retries
^^^^^^^^^^^^^^^

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | The maximum number of retry that the sender can attempt to deliver the ebMS Message.                             |
|                  |                                                                                                                  |
|                  | Hermes 2 tries to deliver the ebMS Message again under the features of reliable messaging until meeting the      |
|                  | maximum number of retries.                                                                                       |
|                  |                                                                                                                  |
|                  | Each retry will be executed after a interval defined in Retry Interval from the last delivery attempt.           |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Param(s)       | [ **Acknowledgment Requested** = always ]                                                                        |
| dependencies**   |                                                                                                                  |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Options**      | [ recommended range = 1-10 ]                                                                                     |
+------------------+------------------------------------------------------------------------------------------------------------------+

Retry Interval (ms)
^^^^^^^^^^^^^^^^^^^

+-----------------------+--------------------------------------------------------------------+
| **Description**       | The interval in millesecond between consecutive retry in delivery. |
+-----------------------+--------------------------------------------------------------------+
| Param(s) dependencies | [ Acknowledgment Requested = always ]                              |
+-----------------------+--------------------------------------------------------------------+
| **Options**           | [ recommended range = 30000 - 300000 ]                             |
+-----------------------+--------------------------------------------------------------------+

Certificate For Verification
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | The certificate (.cer) file for verifying the incoming digitally signed ebMS message by using the public key     |
|                  | generated by sender.                                                                                             |
|                  |                                                                                                                  |
|                  | For sender, it should use the keystore in ebMS plugin to export the public certificate for recipient.            |
|                  | ebMS default keystore location: :samp:`{<HERMES2 HOME>}/plugins/hk.hku.cecid.ebms/security`                      |
|                  |                                                                                                                  |
|                  | The keystore **MUST** be in PKCS12 format.                                                                       |
|                  |                                                                                                                  |
|                  | See Signing Required for details.                                                                                |
+------------------+------------------------------------------------------------------------------------------------------------------+
