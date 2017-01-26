Setting Up AS2 Partnerships
===========================

AS2 Partnership Parameters
--------------------------

Here is a summary of the AS2 partnership parameters.

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
| **Description** | The unique identifier of an AS2 partnership in Hermes 2.                                                         |
|                 |                                                                                                                  |
|                 | The value of this field has no restrictions but it is **RECOMMENDED** to be unique between sender and recipient. |
|                 |                                                                                                                  |
|                 | This field is **mandatory** and its maximum length is 255 characters.                                            |
+-----------------+------------------------------------------------------------------------------------------------------------------+



AS2 From
^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | Identifier of the sending party in a data exchange. The values may be company specific, such as Data Universal   |
|                 | Numbering System (DUNS) numbers, or they may simply be identification strings agreed upon between trading        |
|                 | partners. [`AS2 RFC4130 6.2 <https://tools.ietf.org/html/rfc4130#section-6.2>`_]                                 |
|                 |                                                                                                                  |
|                 | This parameter is used as the ``AS2-From`` property in AS2 message headers in this partnership.                  |
|                 |                                                                                                                  |
|                 | This field is **mandatory** and it is **RECOMMENDED** that the length of this value be less than 255 characters. |
|                 |                                                                                                                  |
|                 | See :ref:`note <note>` below.                                                                                    |
+-----------------+------------------------------------------------------------------------------------------------------------------+

AS2 To
^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | Identifier of the receiving party in a data exchange. The values may be company specific, such as Data Universal |
|                 | Numbering System (DUNS) numbers, or they may simply be identification strings agreed upon between trading        |
|                 | partners. [`AS2 RFC4130 6.2 <https://tools.ietf.org/html/rfc4130#section-6.2>`_]                                 |
|                 |                                                                                                                  |
|                 | This parameter is used as the ``AS2-To`` property in AS2 message headers in this partnership.                    |
|                 |                                                                                                                  |
|                 | This field is **mandatory** and it is **RECOMMENDED** that the length of this value be less than 255 characters. |
|                 |                                                                                                                  |
|                 | See :ref:`note <note>` below.                                                                                    |
+-----------------+------------------------------------------------------------------------------------------------------------------+

.. _note:

| **NOTE**:
| `AS2 From`_ and `AS2 To`_ form a pair that identify the **send** and **recieve** partnerships (i.e. they form a composite key that identifies the parties involved in the data exchange).

The values of [``AS2 From``, ``AS2 To``] are reversed in the **receive** partnership with respect to the **send** partnership. For example:
  
  **Send**: [``CompanyA``, ``CompanyB``] --> **Receive**: [``CompanyB``, ``CompanyA``].

Disabled
^^^^^^^^

+-----------------+-----------------------------------------------------------------------------------------------+
| **Description** | This boolean option indicates whether the partnership is disabled or not.                     |
|                 |                                                                                               |
|                 | Disabled partnerships do not deliver/receive any outgoing/incoming messages.                  |
+-----------------+-----------------------------------------------------------------------------------------------+
| **Options**     | [ ``true`` = disabled ], [ ``false`` = enabled ]                                              |
+-----------------+-----------------------------------------------------------------------------------------------+



Subject
^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | The subject of the partnership.                                                                                  |
|                 |                                                                                                                  |
|                 | This parameter is used as the ``Subject`` property in AS2 message headers in this partnership.                   |
|                 |                                                                                                                  |
|                 | This field is only applicable to **send** partnerships.                                                          |
+-----------------+------------------------------------------------------------------------------------------------------------------+



Recipient Address
^^^^^^^^^^^^^^^^^

+-----------------+--------------------------------------------------------------------------------------+
| **Description** | The endpoint URL of the receiving messaging gateway.                                 |
|                 |                                                                                      |
|                 | If the receiving messaging gateway is Hermes 2, the endpoint URL is                  |
|                 | :samp:`http://{<RECIPIENT_HOST>}:{<PORT>}/corvus/httpd/as2/inbound`.                 |
|                 |                                                                                      |
|                 | This field is **mandatory** and it must be an **HTTP/HTTPS URL**.                    |
+-----------------+--------------------------------------------------------------------------------------+



Hostname Verified in SSL?
^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | This boolean flag indicates whether HTTP SSL/TLS protocol is used to verify the recipient hostname.              |
|                 |                                                                                                                  |
|                 | This is relevant only if **HTTPS** transport protocol is used in `Recipient Address`_.                           |
|                 |                                                                                                                  |
|                 | This field is only applicable to **send** partnerships.                                                          |
+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ ``true`` = hostname verified using SSL ], [ ``false`` = no verification using SSL ]                            |
+-----------------+------------------------------------------------------------------------------------------------------------------+



Request Receipt
^^^^^^^^^^^^^^^

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the sender has requested the recipient to reply with an AS2 receipt (acknowledgement).         |
|                 | How the receipt is sent depends on the value of `Asynchronous Receipt`_. If it is disabled, the receipt will be  |
|                 | sent immediately using the same HTTP connection as the received message. Otherwise, if the recipient is using    |
|                 | Hermes 2, the receipt will be placed in an outgoing queue until it is delivered to the sender.                   |
|                 |                                                                                                                  |
|                 | It is **RECOMMENDED** to set this parameter to ``true`` for reliable messaging.                                  |
|                 |                                                                                                                  |
|                 | This field is only applicable to **send** partnerships.                                                          |
+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ ``true`` = receipt requested ], [ ``false`` = receipt is not requested ]                                       |
+-----------------+------------------------------------------------------------------------------------------------------------------+



Signed Receipt
^^^^^^^^^^^^^^

+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the sender has requested the recipient to digitally sign the AS2 receipt with their private   |
|                  | key before delivering it.                                                                                       |
|                  |                                                                                                                 |
|                  | The format of the private key should be in PKCS12 and the created signatures should conform to IETF S/MIME.     |
|                  |                                                                                                                 |
|                  | The send partnership must enable Request Receipt for this feature to function properly.                         |
|                  |                                                                                                                 |
|                  | The recipient is required to provide a Certificate for Verification so the source of the receipt can            |
|                  | be verified.                                                                                                    |
|                  |                                                                                                                 |
|                  | This field is only applicable to **send** partnerships.                                                         |
+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Dependencies** | [ `Request Receipt`_ = true ] , [ `Certificate for Verification`_ **REQUIRED** ]                                |
+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Options**      | [ ``true`` = receipt must be digitally signed ],                                                                |
|                  |                                                                                                                 |
|                  | [ ``false`` = receipt must not be digitally signed ]                                                            |
+------------------+-----------------------------------------------------------------------------------------------------------------+



Asynchronous Receipt
^^^^^^^^^^^^^^^^^^^^^

+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the recipient should reply to incoming AS2 messages using the same HTTP/HTTPS connection      |
|                  | that the sender is using for delivery.                                                                          |
|                  |                                                                                                                 |
|                  | This field is only applicable to **send** partnerships.                                                         |
+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Dependencies** | [ `Request Receipt`_ = ``true`` ]                                                                               |
+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Options**      | [ ``true`` = asynchronous reply ], [ ``false`` = synchronous reply ]                                            |
+------------------+-----------------------------------------------------------------------------------------------------------------+

Synchronous reply
~~~~~~~~~~~~~~~~~~~~~~
AS2 message receipts are encapsulated in the HTTP response.

.. image:: /_static/images/first_step/as2-send-sync.png
     
Asynchronous reply
~~~~~~~~~~~~~~~~~~
AS2 message receipts will be delivered through another HTTP connection from recipient to sender.

.. image:: /_static/images/first_step/as2-send-async.png

Receipt Return URL
^^^^^^^^^^^^^^^^^^

+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Description**  | This is the endpoint URL of Hermes 2 or another compatible messaging gateway for receiving receipts. It is      |
|                  | always the inbound endpoint URL of the **send** partnership. For example:                                       |
|                  |                                                                                                                 |
|                  |   | **Sender (A)** IP address: ``1.1.1.1:8080``                                                                 |
|                  |   | **Recipient (B)** IP address: ``1.1.1.2:8080``                                                              |
|                  |   | AS2 inbound endpoint : ``/corvus/httpd/as2/inbound``                                                        |
|                  |                                                                                                                 |
|                  |   Then the Receipt Return URL for an AS2 message from **sender (A)** is the inbound                             |
|                  |   endpoint of **sender (A)**, which is ``http://1.1.1.1:8080/corvus/httpd/as2/inbound/``                        |
|                  |                                                                                                                 |
|                  | This field is only applicable to **send** partnerships.                                                         |
+------------------+-----------------------------------------------------------------------------------------------------------------+
| **Dependencies** | [ `Request Receipt`_ = ``true`` ],                                                                              |
|                  | [ `Asynchronous Receipt`_ = ``true`` ]                                                                          |
+------------------+-----------------------------------------------------------------------------------------------------------------+



Message Compression Required
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+---------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the sender must compress outgoing AS2 messages in this partnership.                   |
|                 |                                                                                                         |
|                 | This field is only applicable for **send** partnerships.                                                |
+-----------------+---------------------------------------------------------------------------------------------------------+
| **Options**     | [ ``true`` = outgoing AS2 messages must be compressed ],                                                |
|                 |                                                                                                         |
|                 | [ ``false`` = outgoing AS2 messages must not be compressed ]                                            |
+-----------------+---------------------------------------------------------------------------------------------------------+



Message Signing Required
^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+---------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the sender must digitally sign AS2 messages using their private key.      |
|                 |                                                                                             |
|                 | This field is only applicable for **send** partnerships.                                    |
+-----------------+---------------------------------------------------------------------------------------------+
| **Options**     | [ ``true`` = outgoing AS2 messages must be digitally signed ],                              |
|                 |                                                                                             |
|                 | [ ``false`` = outgoing AS2 messages must not be digitally signed ]                          |
+-----------------+---------------------------------------------------------------------------------------------+

Signing Algorithm
^^^^^^^^^^^^^^^^^

+-----------------+-----------------------------------------------------------------------------------------------+
| **Description** | The algorithm used to digitally sign outgoing AS2 messages in this partnership.               |
+-----------------+-----------------------------------------------------------------------------------------------+
| **Options**     | [ ``SHA1`` ], [ ``MD5`` ]                                                                     |
+-----------------+-----------------------------------------------------------------------------------------------+



Message Encryption Required
^^^^^^^^^^^^^^^^^^^^^^^^^^^

+------------------+----------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the sender must encrypt AS2 messages using the recipient's public    |
|                  | certificate defined in Certificate for Encryption.                                     |
|                  |                                                                                        |
|                  | The encryption method is based on the S/MIME standard.                                 |
|                  |                                                                                        |
|                  | This field is only applicable for **send** partnerships.                               |
+------------------+----------------------------------------------------------------------------------------+
| **Dependencies** | [ `Certificate for Encryption`_ **REQUIRED** ]                                         |
+------------------+----------------------------------------------------------------------------------------+
| **Options**      | [ ``true`` = outgoing AS2 messages must be encrypted ],                                |
|                  |                                                                                        |
|                  | [ ``false`` = outgoing AS2 messages must not be encrypted ]                            |
+------------------+----------------------------------------------------------------------------------------+



Encryption Algorithm
^^^^^^^^^^^^^^^^^^^^

+-----------------+----------------------------------------------------------------------------------------+
| **Description** | The algorithm used to encrypt outgoing AS2 messages in this partnership.               |
+-----------------+----------------------------------------------------------------------------------------+
| **Options**     | [ ``3DES`` ], [ ``RC2`` ]                                                              |
+-----------------+----------------------------------------------------------------------------------------+



Certificate for Encryption
^^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+---------------------------------------------------------------------------------------------------------------------+
| **Description** | The certificate (``.cer``) file for encrypting outgoing AS2 messages using the public key exported by the recipient.|
|                 |                                                                                                                     |
|                 | The recipient should use the keystore in the AS2 plugin to export the public certificate for the sender.            |
|                 |                                                                                                                     |
|                 | AS2 default keystore location: :file:`{<HERMES2_HOME>}/plugins/hk.hku.cecid.edi.as2/security`                       |
|                 |                                                                                                                     |
|                 | The keystore must be in PKCS12 format.                                                                              |
|                 |                                                                                                                     |
|                 | See `Message Encryption Required`_ for details.                                                                     |
+-----------------+---------------------------------------------------------------------------------------------------------------------+



MIC Algorithm
^^^^^^^^^^^^^

+-----------------+----------------------------------------------------------------------------------------------------------+
| **Description** | The algorithm used to create message digests/hashes for outgoing AS2 messages in this partnership.       |
+-----------------+----------------------------------------------------------------------------------------------------------+
| **Options**     | [ ``SHA1`` ], [ ``MD5`` ]                                                                                |
+-----------------+----------------------------------------------------------------------------------------------------------+



Maximum Retries
^^^^^^^^^^^^^^^

+-----------------+-------------------------------------------------------------------------------------------------------------------+
| **Description** | The maximum number of retries allowed for the sender to attempt delivering an AS2 message.                        |
|                 |                                                                                                                   |
|                 | Hermes 2 tries to deliver the AS2 message under the specification of reliable messaging until exceeding           |
|                 | the maximum number of retries.                                                                                    |
|                 |                                                                                                                   |
|                 | There will be a time interval between each attempt, which is defined in `Retry Interval (ms)`_.                   |
|                 |                                                                                                                   |
|                 | It is **RECOMMENDED** that the value of this field be between ``1-10``.                                           |
+-----------------+-------------------------------------------------------------------------------------------------------------------+



Retry Interval (ms)
^^^^^^^^^^^^^^^^^^^

+-----------------+----------------------------------------------------------------------------------------------+
| **Description** | The time interval (milleseconds) between each consecutive attempt to deliver an AS2 message. |
|                 |                                                                                              |
|                 | It is **RECOMMENDED** that the value of this field be between ``30000-300000``.              |
+-----------------+----------------------------------------------------------------------------------------------+



Message Signature Enforced
^^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+--------------------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether incoming AS2 messages must be digitally signed.                                                  |
|                 |                                                                                                                    |
|                 | If enabled, AS2 messages in this partnership must be digitally signed by the sender before the message is          |
|                 | received by the recipient.                                                                                         |
|                 |                                                                                                                    |
|                 | This field is only applicable to **recieve** partnerships.                                                         |
+-----------------+--------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ ``true`` = incoming AS2 messages must be digitally signed ],                                                     |
|                 |                                                                                                                    |
|                 | [ ``false`` = incoming As2 messages may not be digitally signed ]                                                  |
+-----------------+--------------------------------------------------------------------------------------------------------------------+



Message Encryption Enforced
^^^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+-------------------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether incoming AS2 messages must be encrypted.                                                        |
|                 |                                                                                                                   |
|                 | It enforced, AS2 message in this partnership must be encrypted by the sender before the message is                |
|                 | received by the recipient.                                                                                        |
|                 |                                                                                                                   |
|                 | This field is only applicable to **recieve** partnerships.                                                        |
|                 |                                                                                                                   |
+-----------------+-------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ ``true`` = incoming AS2 messages must be encrypted ],                                                           |
|                 |                                                                                                                   |
|                 | [ ``false`` = incoming AS2 messages may not be encrypted ]                                                        |
+-----------------+-------------------------------------------------------------------------------------------------------------------+



Certificate for Verification
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------------+-------------------------------------------------------------------------------------------------------------------+
| **Description** | The certificate (``.cer``) file for verifying incoming digitally signed AS2 messages using the public key         |
|                 | generated by the sender.                                                                                          |
|                 |                                                                                                                   |
|                 | The sender should use the keystore in the AS2 plugin to export the public certificate for the recipient.          |
|                 |                                                                                                                   |
|                 | AS2 default keystore location: :file:`{<HERMES2_HOME>}/plugins/hk.hku.cecid.edi.as2/security`                     |
|                 |                                                                                                                   |
|                 | The keystore must be in PKCS12 format.                                                                            |
|                 |                                                                                                                   |
|                 | See `Message Signing Required`_ for details.                                                                      |
+-----------------+-------------------------------------------------------------------------------------------------------------------+

