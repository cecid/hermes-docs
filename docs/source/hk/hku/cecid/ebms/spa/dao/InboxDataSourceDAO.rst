.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDAO

.. java:import:: java.util Iterator

.. java:import:: java.util List

InboxDataSourceDAO
==================

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public class InboxDataSourceDAO extends DataSourceDAO implements InboxDAO

   :author: Donahue Sze Window - Preferences - Java - Code Style - Code Templates

Methods
-------
addInbox
^^^^^^^^

.. java:method:: public void addInbox(InboxDVO data) throws DAOException
   :outertype: InboxDataSourceDAO

createDVO
^^^^^^^^^

.. java:method:: public DVO createDVO()
   :outertype: InboxDataSourceDAO

deleteInbox
^^^^^^^^^^^

.. java:method:: public void deleteInbox(InboxDVO data) throws DAOException
   :outertype: InboxDataSourceDAO

findInbox
^^^^^^^^^

.. java:method:: public boolean findInbox(InboxDVO data) throws DAOException
   :outertype: InboxDataSourceDAO

findInboxNextOrderNo
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public long findInboxNextOrderNo() throws DAOException
   :outertype: InboxDataSourceDAO

   Returns next value of inbox order no. from DB sequence. it determines message order being retrieved by client. For DB, PostgreSQL & Oracle built-in auto number (sequence) will be used. Otherwise for mySQL, max(order_no) + 1 will be returned. Default starting order no is 1.

   :return: the value of next inbox order no.

updateInbox
^^^^^^^^^^^

.. java:method:: public boolean updateInbox(InboxDVO data) throws DAOException
   :outertype: InboxDataSourceDAO

