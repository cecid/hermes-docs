Setting Up ebMS 2.0 Partnerships
================================

Partnership ID
--------------

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | The unique identifier of an ebMS 2.0 partnership in local Hermes 2.                                              |
|                 |                                                                                                                  |
|                 | The value of this field has no restriction but it is **RECOMMENDED** to be unique between sender and recipient.  |
|                 |                                                                                                                  |
|                 | This field is **mandatory** and its maximum length is 255.                                                       |
|                 |                                                                                                                  |
+-----------------+------------------------------------------------------------------------------------------------------------------+


CPA ID
------

+-----------------+-------------------------------------------------------------------------------------------------------------------------------------+
| **Description** | The Collaboration Protocol Agreement (CPA) ID is a string that identifies the parameters governing the                              |
|                 | exchange of messages between the parties. The recipient of a message must be able to resolve the CPA ID to                          |
|                 | an individual set of parameters, taking into account the sender of the message.                                                     |
|                 |                                                                                                                                     |
|                 | Simply put, it is an arbitary and **mandatory** string that can be used to identify both sender and recipient.                      |
|                 |                                                                                                                                     |
|                 | See [`OASIS ebXML Messaging Service Spec v2.0 <https://www.oasis-open.org/committees/download.php/272/ebMS_v2_0.pdf>`_] for details.|
+-----------------+-------------------------------------------------------------------------------------------------------------------------------------+


Service
-------

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | In Hermes 2, this **mandatory** parameter is used for mapping a partnership between **sender** and **recipient**.|
|                 | It should follow Uniform Resource Naming (URN) format.                                                           |
+-----------------+------------------------------------------------------------------------------------------------------------------+


Action
------

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | This identifies a process within a `Service`_ that processes the ebMS message. Action must be unique within the  |
|                 | Service in which it is defined. The value of the Action element is specified by the designer of the Service.     |
|                 | This field is **mandatory** and its maximum length is 255 characters.                                            |
+-----------------+------------------------------------------------------------------------------------------------------------------+


Disabled
--------

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | Theis boolean option indicates whether the partnership is disabled or not.                                       |
|                 |                                                                                                                  |
|                 | Disabled partnership do not deliver/receive any outgoing/incoming messages.                                      |
+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ ``true`` = disabled ], [ ``false`` = enabled ]                                                                 |
+-----------------+------------------------------------------------------------------------------------------------------------------+


Transport Endpoint
------------------

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | The endpoint URL of the recieving messaging gateway.                                                             |
|                 |                                                                                                                  |
|                 | If the recieving messaging gateway is Hermes 2 and HTTP/HTTPS is the transport protocol, the endpoint URL is     |
|                 | formatted as :samp:`http://{<RECIPIENT HOST>}:{<PORT>}/corvus/httpd/ebms/inbound`.                               |
|                 |                                                                                                                  |
|                 | Otherwise, if the recipient host is an SMTP gateway, the endpoint URL is formatted as                            |
|                 | :samp:`mailto:{<EMAIL ADDRESS>}`.                                                                                |
|                 |                                                                                                                  |
|                 | This field is **mandatory** and the format must be an **HTTP/HTTPS URL** or **EMAIL ADDRESS**.                   |
+-----------------+------------------------------------------------------------------------------------------------------------------+


Hostname Verified in SSL?
-------------------------

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | This boolean flag indicates whether HTTP SSL/TLS protocol is used to verify the recipient hostname.              |
|                 |                                                                                                                  |
|                 | This is relevant only if **HTTPS** transport protocol is used in `Transport Endpoint`_                           |
+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ ``true`` = hostname verified using SSL , ``false`` = no verification using SSL ]                               |
+-----------------+------------------------------------------------------------------------------------------------------------------+


Sync Reply Mode
---------------

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the receiver should reply to incoming ebMS messages using the same HTTP/HTTPS connection that  |
|                 | the sender is using for delivery.                                                                                |
|                 |                                                                                                                  |
|                 | This parameter is only applicable to send partnerships using HTTP/HTTPS transport protocol.                      |
|                 |                                                                                                                  |
+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ ``mshSignalsOnly`` = synchronous reply ], [ ``none`` = asynchronous reply ]                                    |
+-----------------+------------------------------------------------------------------------------------------------------------------+

**Synchronous reply**

ebMS message acknowledgement is included in the HTTP/SOAP response.

.. image:: /_static/images/first_step/ebms-send-sync.png


**Asynchronous reply**

ebMS message acknowledgement will be delivered through another HTTP/SOAP connection from the recipient to the sender.

.. image:: /_static/images/first_step/ebms-send-async.png


Acknowledgement Requested
-------------------------

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the sender has requested the recipient to reply with an ebMS acknowledgement.                  |
|                 | An acknowledgement is a type of ebMS message which has an ``<acknowledgement>`` element.                         |
|                 |                                                                                                                  |
|                 | For interoperability of this feature, both sender and recipient must enable it.                                  |
|                 | Otherwise, the recipient will return a negative acknowledgement.                                                 |
|                 |                                                                                                                  |
|                 | How the acknowledgement is sent depends on the value of `Sync Reply Mode`_. If it is enabled, the                |
|                 | acknowledgement will be sent immediately using the same HTTP connection as the received message. Otherwise, if   |
|                 | the recipient is using Hermes 2, the acknowledgement will be placed in an outgoing queue                         |
|                 | until it is delivered to the sender.                                                                             |
|                 |                                                                                                                  |
|                 | It is **RECOMMENDED** to set this parameter to **always** for reliable messaging.                                |
+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ ``always`` = acknowledgement requested ],                                                                      |
|                 | [ ``none`` = acknowledgement is not requested ]                                                                  |
+-----------------+------------------------------------------------------------------------------------------------------------------+


Acknowledgement Signed Requested
--------------------------------

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the recipient must sign the ebMS acknowledgement digitally using their private key before      |
|                  | delivering it to the sender.                                                                                     |
|                  |                                                                                                                  |
|                  | For interoperability of this feature, both sender and recipient must enable it.                                  |
|                  | Otherwise, the recipient will return a negative acknowledgement.                                                 |
|                  |                                                                                                                  |
|                  | The format of the private key should be in PKCS12 and the created signatures should conform to W3C XML           |
|                  | Signatures Specification [`XMLDsig <https://www.w3.org/TR/xmldsig-core/>`_].                                     |
|                  |                                                                                                                  |
|                  | The send partnership must set `Acknowledgement Requested`_ to  ``always`` for this feature to run                |
|                  | properly.                                                                                                        |
|                  |                                                                                                                  |
|                  | The recipient is required to provide a Certificate for Verification so the signature in the                      |
|                  | acknowledgement can be verified.                                                                                 |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Dependencies** | [ `Acknowledgement Requested`_ = ``always`` ],                                                                   |
|                  |                                                                                                                  |
|                  | [ `Certificate For Verification`_ **REQUIRED** ]                                                                 |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Options**      | [ ``true`` = acknowledgement must be digitally signed ],                                                         |
|                  |                                                                                                                  |
|                  | [ ``false`` = acknolwedgment must not be digitally signed ]                                                      |
+------------------+------------------------------------------------------------------------------------------------------------------+


Duplicate Elimination
---------------------

+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Description** | Indicates whether the recipient will ignore duplicate messages.                                                  |
|                 |                                                                                                                  |
|                 | For interoperability of this feature, both sender and recipient must enable it.                                  |
|                 | Otherwise, the recipient will return a negative acknowledgement.                                                 |
+-----------------+------------------------------------------------------------------------------------------------------------------+
| **Options**     | [ ``always`` = ignores duplicate messages ],                                                                     |
|                 |                                                                                                                  |
|                 | [ ``never`` = receives duplicate messages ]                                                                      |
+-----------------+------------------------------------------------------------------------------------------------------------------+


Message Order
-------------

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the recipient must receive ebMS messages in the same sequence that they were sent.             |
|                  |                                                                                                                  |
|                  | For interoperability of this feature, both sender and recipient must enable it.                                  |
|                  | Otherwise, the recipient will return a negative acknowledgement.                                                 |
|                  |                                                                                                                  |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Dependencies** | [ `Sync Reply Mode`_ = ``none`` ],                                                                               |
|                  |                                                                                                                  |
|                  | [ `Acknowledgement Requested`_ = ``always`` ],                                                                   |
|                  |                                                                                                                  |
|                  | [ `Duplicate Elimination`_ = ``always`` ]                                                                        |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Options**      | [ ``Guaranteed`` = recipient receives ebMS messages in sending order ],                                          |
|                  |                                                                                                                  |
|                  | [ ``NotGuaranteed`` = recipient receives ebMS message with best effort behavior ]                                |
+------------------+------------------------------------------------------------------------------------------------------------------+


Signing Required?
-----------------

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the sender must sign ebMS messages digitally using their private key.                          |
|                  |                                                                                                                  |
|                  | For interoperability of this feature, both sender and recipient must enable this.                                |
|                  | Otherwise, the recipient will return a negative acknowledgement.                                                 | 
|                  |                                                                                                                  |
|                  | The format of the private key should be in PKCS12 and the created signature should conform to W3C XML            |
|                  | Signatures Specification [`XMLDsig <https://www.w3.org/TR/xmldsig-core/>`_].                                     |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Options**      | [ ``true`` = outgoing ebMS messages must be digitally signed ],                                                  |
|                  |                                                                                                                  |
|                  | [ ``false`` = outgoing ebMS messages are not required to be digitally signed ]                                   |
+------------------+------------------------------------------------------------------------------------------------------------------+


Encryption Required? (Mail Only)
--------------------------------

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | Indicates whether the sender must encrypt ebMS messages using the recipient's public certificate defined in      |
|                  | Certificate For Encryption.                                                                                      |
|                  |                                                                                                                  |
|                  | This is only applicable when using **SMTP** protocol for Transport Endpoint.                                     |
|                  |                                                                                                                  |
|                  | The encryption method is based on S/MIME standard.                                                               |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Dependencies** | [ `Transport Endpoint`_ = using SMTP protocol ],                                                                 |
|                  |                                                                                                                  |
|                  | [ `Sync Reply Mode`_ = ``none`` ],                                                                               |
|                  |                                                                                                                  |
|                  | [ `Certificate For Encryption`_ **REQUIRED** ]                                                                   |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Options**      | [ ``true`` = outgoing ebMS messages must be encrypted ],                                                         |
|                  |                                                                                                                  |
|                  | [ ``false`` = outgoing ebMS messages are not required to be encrypted ]                                          |
+------------------+------------------------------------------------------------------------------------------------------------------+


Certificate For Encryption
--------------------------

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | The certificate file for encrypting outgoing ebMS messages using SMTP protocol by using the public key           |
|                  | generated by the recipient.                                                                                      |
|                  |                                                                                                                  |
|                  | The recipient should use the keystore in the ebMS plugin to export the public certificate for the sender.        |
|                  | ebMS default keystore location: :file:`{<HERMES2_HOME>}/plugins/hk.hku.cecid.ebms/security`                      |
|                  |                                                                                                                  |
|                  | The certificate must be in X.509 format. See `Encryption Required? (Mail Only)`_ for details.                    |
+------------------+------------------------------------------------------------------------------------------------------------------+


Maximum Retries
---------------

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | The maximum number of retries allowed for the sender to attempt delivering an ebMS message.                      |
|                  |                                                                                                                  |
|                  | Hermes 2 tries to deliver the ebMS message under the features of reliable messaging until exceeding the          |
|                  | maximum number of retries.                                                                                       |
|                  |                                                                                                                  |
|                  | There will be a time interval between each attempt, which is defined in `Retry Interval (ms)`_.                  |
|                  |                                                                                                                  |
|                  | It is **recommended** that the value of this field be between ``1-10``.                                          |
+------------------+------------------------------------------------------------------------------------------------------------------+
| **Dependencies** | [ `Acknowledgement Requested`_ = ``always`` ]                                                                    |
|                  |                                                                                                                  |
+------------------+------------------------------------------------------------------------------------------------------------------+


Retry Interval (ms)
-------------------

+-----------------------+-----------------------------------------------------------------------------------------------+
| **Description**       | The time interval (milleseconds) between each consecutive attempt to deliver an ebMS message. |
|                       |                                                                                               |
|                       | It is **recommended** that the value of this field be between ``30000-300000``.               |
+-----------------------+-----------------------------------------------------------------------------------------------+
| **Dependencies**      | [ `Acknowledgement Requested`_ = ``always`` ]                                                 |
+-----------------------+-----------------------------------------------------------------------------------------------+


Certificate For Verification
----------------------------

+------------------+------------------------------------------------------------------------------------------------------------------+
| **Description**  | The certificate (``.cer``) file for verifying incoming digitally signed ebMS message by using the public key     |
|                  | generated by sender.                                                                                             |
|                  |                                                                                                                  |
|                  | The sender should use the keystore in the ebMS plugin to export the public certificate for the recipient.        |
|                  | ebMS default keystore location: :file:`{<HERMES2_HOME>}/plugins/hk.hku.cecid.ebms/security`                      |
|                  |                                                                                                                  |
|                  | The keystore must be in PKCS12 format.                                                                           |
|                  |                                                                                                                  |
|                  | See `Signing Required?`_ for details.                                                                            |
+------------------+------------------------------------------------------------------------------------------------------------------+
