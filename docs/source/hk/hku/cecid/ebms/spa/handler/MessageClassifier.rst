.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

MessageClassifier
=================

.. java:package:: hk.hku.cecid.ebms.spa.handler
   :noindex:

.. java:type:: public class MessageClassifier

   :author: Donahue Sze

Fields
------
ACTION_ACKNOWLEDGMENT
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String ACTION_ACKNOWLEDGMENT
   :outertype: MessageClassifier

ACTION_MESSAGE_ERROR
^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String ACTION_MESSAGE_ERROR
   :outertype: MessageClassifier

ACTION_PING
^^^^^^^^^^^

.. java:field:: public static String ACTION_PING
   :outertype: MessageClassifier

ACTION_PONG
^^^^^^^^^^^

.. java:field:: public static String ACTION_PONG
   :outertype: MessageClassifier

ACTION_STATUS_REQUEST
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String ACTION_STATUS_REQUEST
   :outertype: MessageClassifier

ACTION_STATUS_RESPONSE
^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String ACTION_STATUS_RESPONSE
   :outertype: MessageClassifier

INTERNAL_STATUS_DELIVERED
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String INTERNAL_STATUS_DELIVERED
   :outertype: MessageClassifier

INTERNAL_STATUS_DELIVERY_FAILURE
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String INTERNAL_STATUS_DELIVERY_FAILURE
   :outertype: MessageClassifier

INTERNAL_STATUS_PENDING
^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String INTERNAL_STATUS_PENDING
   :outertype: MessageClassifier

INTERNAL_STATUS_PROCESSED
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String INTERNAL_STATUS_PROCESSED
   :outertype: MessageClassifier

INTERNAL_STATUS_PROCESSED_ERROR
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String INTERNAL_STATUS_PROCESSED_ERROR
   :outertype: MessageClassifier

INTERNAL_STATUS_PROCESSING
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String INTERNAL_STATUS_PROCESSING
   :outertype: MessageClassifier

INTERNAL_STATUS_RECEIVED
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String INTERNAL_STATUS_RECEIVED
   :outertype: MessageClassifier

MESSAGE_BOX_INBOX
^^^^^^^^^^^^^^^^^

.. java:field:: public static String MESSAGE_BOX_INBOX
   :outertype: MessageClassifier

MESSAGE_BOX_OUTBOX
^^^^^^^^^^^^^^^^^^

.. java:field:: public static String MESSAGE_BOX_OUTBOX
   :outertype: MessageClassifier

MESSAGE_TYPE_ACKNOWLEDGEMENT
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String MESSAGE_TYPE_ACKNOWLEDGEMENT
   :outertype: MessageClassifier

MESSAGE_TYPE_ERROR
^^^^^^^^^^^^^^^^^^

.. java:field:: public static String MESSAGE_TYPE_ERROR
   :outertype: MessageClassifier

MESSAGE_TYPE_ORDER
^^^^^^^^^^^^^^^^^^

.. java:field:: public static String MESSAGE_TYPE_ORDER
   :outertype: MessageClassifier

MESSAGE_TYPE_PING
^^^^^^^^^^^^^^^^^

.. java:field:: public static String MESSAGE_TYPE_PING
   :outertype: MessageClassifier

MESSAGE_TYPE_PONG
^^^^^^^^^^^^^^^^^

.. java:field:: public static String MESSAGE_TYPE_PONG
   :outertype: MessageClassifier

MESSAGE_TYPE_PROCESSED_ERROR
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String MESSAGE_TYPE_PROCESSED_ERROR
   :outertype: MessageClassifier

MESSAGE_TYPE_STATUS_REQUEST
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String MESSAGE_TYPE_STATUS_REQUEST
   :outertype: MessageClassifier

MESSAGE_TYPE_STATUS_RESPONSE
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String MESSAGE_TYPE_STATUS_RESPONSE
   :outertype: MessageClassifier

SERVICE
^^^^^^^

.. java:field:: public static String SERVICE
   :outertype: MessageClassifier

STATUS_FORWARDED
^^^^^^^^^^^^^^^^

.. java:field:: public static String STATUS_FORWARDED
   :outertype: MessageClassifier

STATUS_NOT_RECOGNIZED
^^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String STATUS_NOT_RECOGNIZED
   :outertype: MessageClassifier

STATUS_PROCESSED
^^^^^^^^^^^^^^^^

.. java:field:: public static String STATUS_PROCESSED
   :outertype: MessageClassifier

STATUS_RECEIVED
^^^^^^^^^^^^^^^

.. java:field:: public static String STATUS_RECEIVED
   :outertype: MessageClassifier

STATUS_UN_AUTHORIZED
^^^^^^^^^^^^^^^^^^^^

.. java:field:: public static String STATUS_UN_AUTHORIZED
   :outertype: MessageClassifier

Constructors
------------
MessageClassifier
^^^^^^^^^^^^^^^^^

.. java:constructor:: public MessageClassifier(EbxmlMessage ebxmlMessage)
   :outertype: MessageClassifier

Methods
-------
getMessageType
^^^^^^^^^^^^^^

.. java:method:: public String getMessageType()
   :outertype: MessageClassifier

   :return: Returns the messageType.

isAckRequested
^^^^^^^^^^^^^^

.. java:method:: public boolean isAckRequested()
   :outertype: MessageClassifier

   :return: Returns the isAckRequested.

isDupElimination
^^^^^^^^^^^^^^^^

.. java:method:: public boolean isDupElimination()
   :outertype: MessageClassifier

   :return: Returns the isDupElimination.

isMessageOrder
^^^^^^^^^^^^^^

.. java:method:: public boolean isMessageOrder()
   :outertype: MessageClassifier

   :return: Returns the isMessageOrder.

isSeqeunceStatusReset
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean isSeqeunceStatusReset()
   :outertype: MessageClassifier

   :return: Returns the isSeqeunceStatusReset.

isSync
^^^^^^

.. java:method:: public boolean isSync()
   :outertype: MessageClassifier

   :return: Returns the isSync.

