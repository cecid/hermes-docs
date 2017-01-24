.. _as2_partnership:

Reference of AS2 Partnership Configuration
==========================================

AS2 Partnership parameter
-------------------------

Here is the summary of the AS2 Partnership parameter.

1. `Partnership ID`_
#. `AS2 From`_
#. `AS2 To`_
#. `Disabled`_
#. `Subject`_
#. `Recipient Address`_
#. `Hostname Verified in SSL?`_
#. `Request Receipt`_
#. `Signed Receipt`_
#. `Asynchronous Receipt`_
#. `Receipt Return URL`_
#. `Message Compression Required`_
#. `Message Signing Required`_
#. `Signing Algorithm`_
#. `Message Encryption Required`_
#. `Encryption Algorithm`_
#. `Certificate For Encryption`_
#. `MIC Algorithm`_
#. `Maximum Retries`_
#. `Retry Interval (ms)`_
#. `Message Signature Enforced`_
#. `Message Encryption Enforced`_
#. `Certificate For Verification`_


Partnership ID
^^^^^^^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | The unique identifier of an AS2 2.0 partnership in local Hermes 2.                                               |
|                 |                                                                                                                  |
|                 | The value of this field has no restriction but **RECOMMENDED** to be an identifier between sender and recipient. |
|                 |                                                                                                                  |
|                 | It is **mandatory** and its maximum length of this field is 255.                                                 |
+-----------------+------------------------------------------------------------------------------------------------------------------+



AS2 From
^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | It identifies the sender party of a data exchange. The values may be company specific, such as Data Universal    |
|                 | Numbering System (DUNS) numbers, or they may be simply identification strings agreed upon between the trading    |
|                 | partners. [AS2 RFC4130 6.2]                                                                                      |
|                 |                                                                                                                  |
|                 | The parameter is used as the one of property called AS2-From in the AS2 message header which applied this        |
|                 | partnership.                                                                                                     |
|                 |                                                                                                                  |
|                 | AS2 From and AS2 To form a pair for identifying the **Sender** and **Recipient** Partnership. I.e. They form     |
|                 | composite key for identifying the parties involved in the data exchange.                                         |
|                 |                                                                                                                  |
|                 | It is **mandatory** and **RECOMMENDED** the length of this value should be less than 255.                        |
|                 |                                                                                                                  |
|                 | **NOTE**: The value of [**AS2 From**, **AS2 To**] pair is reversed in the **Recipient** partnership respect to   |
|                 | the **Sender** partnership. For example:                                                                         |
|                 |                                                                                                                  |
|                 | If the value of [AS2 From, AS2 To] of **Sender** partnership is [CompanyA, CompanyB],                            |
|                 |                                                                                                                  |
|                 | then the value of [AS2 From, AS2 To] of **Recipient** partnership should be [CompanyB, CompanyA].                |
+-----------------+------------------------------------------------------------------------------------------------------------------+

AS2 To
^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | It identifies the receiver party of a data exchange. The values may be company specific, such as Data Universal  |
|                 | Numbering System (DUNS) numbers, or they may be simply identification strings agreed upon between the trading    |
|                 | partners. [AS2 RFC4130 6.2]                                                                                      |
|                 |                                                                                                                  |
|                 | The parameter is used as the one of property called AS2-To in the AS2 message header which applied this          |
|                 | partnership. AS2 From and AS2 To form a pair for identifying the **Sender** and **Recipient** Partnership. I.e.  |
|                 | They form composite key for identifying the parties involved in the data exchange.                               |
|                 |                                                                                                                  |
|                 | It is mandatory and RECOMMENDED the length of this value should be less than 255.                                |
|                 |                                                                                                                  |
|                 | **NOTE**: The value of [**AS2 From**, **AS2 To**] pair is reversed in the **Recipient** partnership respect to   |
|                 | the **Sender** partnership. For example:                                                                         |
|                 |                                                                                                                  |
|                 | If the value of [AS2 From, AS2 To] of **Sender** partnership is [CompanyA, CompanyB],                            |
|                 |                                                                                                                  |
|                 | then the value of [AS2 From, AS2 To] of **Recipient** partnership should has [CompanyB, CompanyA].               |
+-----------------+------------------------------------------------------------------------------------------------------------------+

Disabled
^^^^^^^^

+-----------------+-----------------------------------------------------------------------------------------------+
| **Description** | The boolean option indicates whether the partnership is disabled or not.                      |
|                 |                                                                                               |
|                 | Disabled partnership does not deliver / receive any outgoing message / incoming respectively. |
+-----------------+-----------------------------------------------------------------------------------------------+
| **Options**     | [ **true** = disabled ], [ **false** = enabled ]                                              |
+-----------------+-----------------------------------------------------------------------------------------------+



Subject
^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | The subject of the partnership.                                                                                  |
|                 |                                                                                                                  |
|                 | The parameter is used as the one of property called Subject in those AS2 message header which applied this       |
|                 | partnership.                                                                                                     |
|                 |                                                                                                                  |
|                 | It is applicable only for **Sender** partnership.                                                                |
+-----------------+------------------------------------------------------------------------------------------------------------------+



Recipient Address
^^^^^^^^^^^^^^^^^

+-----------------+--------------------------------------------------------------------------------------+
| **Description** | The endpoint URL of the receiving message gateway.                                   |
|                 |                                                                                      |
|                 | If the receiving message gateway is Hermes 2, the endpoint URL is formatted as this. |
|                 |                                                                                      |
|                 | :samp:`http://{<RECIPIENT HOST>}:{<PORT>}/corvus/httpd/as2/inbound`.                 |
|                 |                                                                                      |
|                 | It is **mandatory** and it MUST be a **HTTP/HTTPS URL**.                             |
+-----------------+--------------------------------------------------------------------------------------+



Hostname Verified in SSL?
^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | The boolean flag indicates whether HTTP SSL/TLS protocol is used and required to verify the receipient hostname. |
|                 |                                                                                                                  |
|                 | It is relevant if **HTTPS** transport protocol is set under the Receipient Address                               |
|                 |                                                                                                                  |
|                 | It is applicable only for **Sender** partnership.                                                                |
|                 |                                                                                                                  |
| **Options**     | [ **true** = hostname verified using SSL , **false** = none ]                                                    |
+-----------------+------------------------------------------------------------------------------------------------------------------+



Request Receipt
^^^^^^^^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the recipient is requested to send an AS2 receipt (acknowledgement) back to the sender.        |
|                 | The mode of receipt sending back depends on the value Asynchronous Receipt, if `Asynchronous Receipt`_ is        |
|                 | disabled, the receipt will return immediately in the same HTTP connection. If the recipient is using Hermes 2,   |
|                 | the receipt will be put into an outgoing queue and keep waiting until it is delivered to the sender.             |
|                 |                                                                                                                  |
|                 | It is **RECOMMENDED** to set this parameter to **true** for reliable messaging.                                  |
|                 |                                                                                                                  |
|                 | It is applicable only for **Sender** partnership.                                                                |
+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ **true** = receipt requested ], [ **false** = receipt does not request ]                                       |
+-----------------+------------------------------------------------------------------------------------------------------------------+



Signed Receipt
^^^^^^^^^^^^^^

+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the recipient **MUST** sign the AS2 receipt digitally using its private key before delivering |
|                  | back to the sender.                                                                                             |
|                  |                                                                                                                 |
|                  | The format of the private key **SHOULD BE** in PKCS12 and the signatures created is conformed to IETF S/MIME.   |
|                  |                                                                                                                 |
|                  | The sender partnership MUST enable `Request Receipt`_ from recipient for running this features properly.        |
|                  |                                                                                                                 |
|                  | Recipient is required to provide its public certificate to sender for verifying the source of the receipt.      |
|                  |                                                                                                                 |
|                  | It is applicable only for **Sender** partnership.                                                               |
+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Dependencies** | [ Request Receipt = true ] , [ Certificate for Verification **REQUIRED** ]                                      |
+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Options**      | [ **true** = receipt MUST be digitally signed ],                                                                |
|                  |                                                                                                                 |
|                  | [ **false** = receipt MUST not be digitally signed ]                                                            |
+------------------+-----------------------------------------------------------------------------------------------------------------+



Asynchronous Receipt
^^^^^^^^^^^^^^^^^^^^^

+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the recipient should reply the incoming AS2 message in same HTTP/HTTPS connection the sender  |
|                  | uses for delivery.                                                                                              |
|                  |                                                                                                                 |
|                  | It is applicable only for **Sender** partnership.                                                               |
+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Dependencies** | [ Request Receipt = true ]                                                                                      |
+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Options**      | [ **true** = asynchronous reply ], [ **false** = synchronous reply ]                                            |
+------------------+-----------------------------------------------------------------------------------------------------------------+


An example of synchronous reply from the recipient:
AS2 message receipt is encapsulated in the HTTP response when synchronous reply is applied.

.. image:: /_static/images/first_step/as2-send-sync.png

An example of asynchronous reply from the recipient:
AS2 message receipt will be delivered through another HTTP connection from recipient to sender.

.. image:: /_static/images/first_step/as2-send-async.png

Receipt Return URL
^^^^^^^^^^^^^^^^^^

+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Description**  | It is the endpoint URL of Hermes 2 or any compatible messaging gateway for receiving receipts. It **SHOULD**    |
|                  | always be the inbound endpoint URL of the **Sender**.                                                           |
|                  |                                                                                                                 |
|                  | For example:                                                                                                    |
|                  |                                                                                                                 |
|                  | **Sender (A)** IP address: 1.1.1.1:8080                                                                         |
|                  |                                                                                                                 |
|                  | **Recipient (B)** IP address: 1.1.1.2:8080                                                                      |
|                  |                                                                                                                 |
|                  | AS2 inbound endpoint : /corvus/httpd/as2/inbound                                                                |
|                  |                                                                                                                 |
|                  | Then the Receipt Return URL for sending an AS2 message from **sender (A)** to **recipient (B)** is the inbound  |
|                  | endpoint of **sender (A)**, which is *http://1.1.1.1:8080/corvus/httpd/as2/inbound/*                            |
|                  |                                                                                                                 |
|                  | It is applicable only for **Sender** partnership.                                                               |
+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Dependencies** | [ Request Receipt = true ],                                                                                     |
|                  |                                                                                                                 |
|                  | [ Asynchronous Receipt = true ]                                                                                 |
+------------------+-----------------------------------------------------------------------------------------------------------------+



Message Compression Required
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+---------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the sender **MUST** compress the outgoing AS2 message which applied this partnership. |
|                 |                                                                                                         |
|                 | It is applicable only for **Sender** partnership.                                                       |
+-----------------+---------------------------------------------------------------------------------------------------------+
| **Options**     | [ **true** = The outgoing normal/payload AS2 message MUST be compressed first. ],                       |
|                 |                                                                                                         |
|                 | [ **false** = The outgoing normal/payload AS2 message MUST not be compressed. ]                         |
+-----------------+---------------------------------------------------------------------------------------------------------+



Message Signing Required
^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+---------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the sender **MUST** sign digitally the AS2 message using its private key. |
|                 |                                                                                             |
|                 | It is applicable only for **Sender** partnership.                                           |
+-----------------+---------------------------------------------------------------------------------------------+
| **Options**     | [ **true** = The outgoing AS2 message MUST be digitally signed. ],                          |
|                 |                                                                                             |
|                 | [ **false** = The outgoing AS2 message MUST not sign digitally. ]                           |
+-----------------+---------------------------------------------------------------------------------------------+

Signing Algorithm
^^^^^^^^^^^^^^^^^

+-----------------+-----------------------------------------------------------------------------------------------+
| **Description** | The algorithm used to sign digitally the outgoing AS2 message which applied this partnership. |
+-----------------+-----------------------------------------------------------------------------------------------+
| **Options**     | [ SHA1],[ MD5 ]                                                                               |
+-----------------+-----------------------------------------------------------------------------------------------+



Message Encryption Required
^^^^^^^^^^^^^^^^^^^^^^^^^^^

+------------------+----------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the sender **MUST** encrypt the AS2 message using recipient's public |
|                  | certificate defined in Certificate for Encryption.                                     |
|                  |                                                                                        |
|                  | The encryption method is based on S/MIME standard.                                     |
|                  |                                                                                        |
|                  | It is applicable only for **Sender** partnership.                                      |
+------------------+----------------------------------------------------------------------------------------+
| **Dependencies** | [ Certificate for Encryption **REQUIRED** ] ,                                          |
+------------------+----------------------------------------------------------------------------------------+
| **Options**      | [ **true** = The outgoing normal/payload AS2 message MUST be encrypted. ],             |
|                  |                                                                                        |
|                  | [ **false** = The outgoing AS2 message does not require to encrypt. ]                  |
+------------------+----------------------------------------------------------------------------------------+



Encryption Algorithm
^^^^^^^^^^^^^^^^^^^^

+-----------------+----------------------------------------------------------------------------------------+
| **Description** | The algorithm used to encrypt the outgoing AS2 message which applied this partnership. |
+-----------------+----------------------------------------------------------------------------------------+
| **Options**     | [ **3DES** ],[ **RC2** ]                                                               |
+-----------------+----------------------------------------------------------------------------------------+



Certificate for Encryption
^^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+--------------------------------------------------------------------------------------------------------------------+
| **Description** | The certificate (.cer) file for encrypting the outgoing AS2 message by using the public key exported by recipient. |
|                 |                                                                                                                    |
|                 | For recipient, it should use the keystore in AS2 plugin to export the public certificate for sender.               |
|                 |                                                                                                                    |
|                 | AS2 default keystore location: :file:`{<HERMES2 HOME>}/plugins/hk.hku.cecid.edi.as2/security`                      |
|                 |                                                                                                                    |
|                 | The keystore **MUST** be in PKCS12 format.                                                                         |
|                 |                                                                                                                    |
|                 | See Message Encryption Required for details.                                                                       |
+-----------------+--------------------------------------------------------------------------------------------------------------------+



MIC Algorithm
^^^^^^^^^^^^^

+-----------------+----------------------------------------------------------------------------------------------------------+
| **Description** | The algorithm to create message digest/hash for the outgoing AS2 message which applied this partnership. |
+-----------------+----------------------------------------------------------------------------------------------------------+
| **Options**     | [ **SHA1** ],[ **MD5** ]                                                                                 |
+-----------------+----------------------------------------------------------------------------------------------------------+



Maximum Retries
^^^^^^^^^^^^^^^

+-----------------+-------------------------------------------------------------------------------------------------------------------+
| **Description** | The maximum number of retry that the sender can attempt to deliver the AS2 message.                               |
|                 |                                                                                                                   |
|                 | Hermes 2 tries to deliver the AS2 message again under the specification of reliable messaging until exceeding     |
|                 | the maximum number of retries.                                                                                    |
|                 |                                                                                                                   |
|                 | Each retry will be executed after a interval defined in Retry Interval from the last delivery attempt.            |
+-----------------+-------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ recommended range = 1-10 ]                                                                                      |
+-----------------+-------------------------------------------------------------------------------------------------------------------+



Retry Interval (ms)
^^^^^^^^^^^^^^^^^^^

+-----------------+--------------------------------------------------------------------+
| **Description** | The interval in millesecond between consecutive retry in delivery. |
+-----------------+--------------------------------------------------------------------+
| **Options**     | [ recommended range = 30000 - 300000 ]                             |
+-----------------+--------------------------------------------------------------------+



Message Signature Enforced
^^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+--------------------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the incoming AS2 message **MUST** be digitally signed.                                           |
|                 |                                                                                                                    |
|                 | It enforced, AS2 message applied this partnership **MUST** be digitally signed by **Sender** before the message is |
|                 | received by **Recipient**.                                                                                         |
|                 |                                                                                                                    |
|                 | It is applicable only for **Recipient** partnership.                                                               |
+-----------------+--------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ **true** = incoming AS2 messages must be digitally signed ],                                                     |
|                 |                                                                                                                    |
|                 | [ **false** = incoming As2 messages may or may not be digitally signed ]                                           |
+-----------------+--------------------------------------------------------------------------------------------------------------------+



Message Encryption Enforced
^^^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+-------------------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the incoming AS2 message **MUST** be encrypted.                                                 |
|                 |                                                                                                                   |
|                 | It enforced, AS2 message applied this partnership **MUST** be encrypted by **Sender** before the message is       |
|                 | received by **Recipient**.                                                                                        |
|                 |                                                                                                                   |
|                 | It is applicable only for **Recipient** partnership.                                                              |
|                 |                                                                                                                   |
| **Options**     | [ **true** = incoming AS2 messages must be encrypted ],                                                           |
+-----------------+-------------------------------------------------------------------------------------------------------------------+
|                 | [ **false** = incoming AS2 messages may or may not be encrypted ]                                                 |
+-----------------+-------------------------------------------------------------------------------------------------------------------+



Certificate for Verification
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+-------------------------------------------------------------------------------------------------------------------+
| **Description** | The certificate (.cer) file for verifying the incoming digitally signed AS2 message by using the public key       |
|                 | generated by sender.                                                                                              |
|                 |                                                                                                                   |
|                 | For sender, it should use the keystore in AS2 plugin to export the public certificate for recipient.              |
|                 |                                                                                                                   |
|                 | AS2 default keystore location: *<HERMES2 HOME>/plugins/hk.hku.cecid.edi.as2/security*                             |
|                 |                                                                                                                   |
|                 | The keystore **MUST** be in PKCS12 format.                                                                        |
|                 |                                                                                                                   |
|                 | See Message Signing Required for details.                                                                         |
+-----------------+-------------------------------------------------------------------------------------------------------------------+

