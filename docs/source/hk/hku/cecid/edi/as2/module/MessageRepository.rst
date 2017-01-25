.. java:import:: hk.hku.cecid.edi.as2.dao MessageDVO

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: java.io FileOutputStream

.. java:import:: java.io InputStream

MessageRepository
=================

.. java:package:: hk.hku.cecid.edi.as2.module
   :noindex:

.. java:type:: public class MessageRepository extends PayloadRepository

   MessageRepository

   :author: Hugo Y. K. Lam

Constructors
------------
MessageRepository
^^^^^^^^^^^^^^^^^

.. java:constructor:: public MessageRepository()
   :outertype: MessageRepository

Methods
-------
init
^^^^

.. java:method:: protected void init() throws Exception
   :outertype: MessageRepository

persistMessage
^^^^^^^^^^^^^^

.. java:method:: public void persistMessage(AS2Message message)
   :outertype: MessageRepository

persistMessage
^^^^^^^^^^^^^^

.. java:method:: public void persistMessage(MessageDVO message, InputStream content)
   :outertype: MessageRepository

