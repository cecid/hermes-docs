.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

.. java:import:: java.io InputStream

.. java:import:: java.sql Timestamp

RepositoryDVO
=============

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public interface RepositoryDVO extends DVO

   :author: Donahue Sze

Methods
-------
getContent
^^^^^^^^^^

.. java:method:: public byte[] getContent()
   :outertype: RepositoryDVO

   :return: Returns the content.

getContentType
^^^^^^^^^^^^^^

.. java:method:: public String getContentType()
   :outertype: RepositoryDVO

getMessageBox
^^^^^^^^^^^^^

.. java:method:: public String getMessageBox()
   :outertype: RepositoryDVO

   :return: Returns the messageBox.

getMessageId
^^^^^^^^^^^^

.. java:method:: public String getMessageId()
   :outertype: RepositoryDVO

   :return: Returns the messageId.

getTimeStamp
^^^^^^^^^^^^

.. java:method:: public Timestamp getTimeStamp()
   :outertype: RepositoryDVO

   :return: Returns the timeStamp.

setContent
^^^^^^^^^^

.. java:method:: public void setContent(byte[] content)
   :outertype: RepositoryDVO

   :param content: The content to set.

setContent
^^^^^^^^^^

.. java:method:: public void setContent(InputStream is)
   :outertype: RepositoryDVO

setContentType
^^^^^^^^^^^^^^

.. java:method:: public void setContentType(String contentType)
   :outertype: RepositoryDVO

setMessageBox
^^^^^^^^^^^^^

.. java:method:: public void setMessageBox(String messageBox)
   :outertype: RepositoryDVO

   :param messageBox: The messageBox to set.

setMessageId
^^^^^^^^^^^^

.. java:method:: public void setMessageId(String messageId)
   :outertype: RepositoryDVO

   :param messageId: The messageId to set.

setTimeStamp
^^^^^^^^^^^^

.. java:method:: public void setTimeStamp(Timestamp timeStamp)
   :outertype: RepositoryDVO

   :param timeStamp: The timeStamp to set.

