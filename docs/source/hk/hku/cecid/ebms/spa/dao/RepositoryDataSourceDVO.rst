.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDVO

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds NullableObject

.. java:import:: java.io InputStream

.. java:import:: java.sql SQLException

.. java:import:: java.sql Timestamp

.. java:import:: java.sql Types

RepositoryDataSourceDVO
=======================

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public class RepositoryDataSourceDVO extends DataSourceDVO implements RepositoryDVO

   :author: Donahue Sze Window - Preferences - Java - Code Style - Code Templates

Constructors
------------
RepositoryDataSourceDVO
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public RepositoryDataSourceDVO()
   :outertype: RepositoryDataSourceDVO

Methods
-------
getContent
^^^^^^^^^^

.. java:method:: public byte[] getContent()
   :outertype: RepositoryDataSourceDVO

getContentType
^^^^^^^^^^^^^^

.. java:method:: public String getContentType()
   :outertype: RepositoryDataSourceDVO

getMessageBox
^^^^^^^^^^^^^

.. java:method:: public String getMessageBox()
   :outertype: RepositoryDataSourceDVO

   :return: Returns the messageBox.

getMessageId
^^^^^^^^^^^^

.. java:method:: public String getMessageId()
   :outertype: RepositoryDataSourceDVO

getTimeStamp
^^^^^^^^^^^^

.. java:method:: public Timestamp getTimeStamp()
   :outertype: RepositoryDataSourceDVO

   :return: Returns the timeStamp.

setContent
^^^^^^^^^^

.. java:method:: public void setContent(byte[] content)
   :outertype: RepositoryDataSourceDVO

setContent
^^^^^^^^^^

.. java:method:: public void setContent(InputStream is)
   :outertype: RepositoryDataSourceDVO

setContentType
^^^^^^^^^^^^^^

.. java:method:: public void setContentType(String contentType)
   :outertype: RepositoryDataSourceDVO

setMessageBox
^^^^^^^^^^^^^

.. java:method:: public void setMessageBox(String messageBox)
   :outertype: RepositoryDataSourceDVO

   :param messageBox: The messageBox to set.

setMessageId
^^^^^^^^^^^^

.. java:method:: public void setMessageId(String messageId)
   :outertype: RepositoryDataSourceDVO

setTimeStamp
^^^^^^^^^^^^

.. java:method:: public void setTimeStamp(Timestamp timeStamp)
   :outertype: RepositoryDataSourceDVO

   :param timeStamp: The timeStamp to set.

