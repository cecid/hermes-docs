.. java:import:: hk.hku.cecid.piazza.commons.dao DAO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

InboxDAO
========

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public interface InboxDAO extends DAO

   :author: Donahue Sze

Methods
-------
addInbox
^^^^^^^^

.. java:method:: public void addInbox(InboxDVO data) throws DAOException
   :outertype: InboxDAO

deleteInbox
^^^^^^^^^^^

.. java:method:: public void deleteInbox(InboxDVO data) throws DAOException
   :outertype: InboxDAO

findInbox
^^^^^^^^^

.. java:method:: public boolean findInbox(InboxDVO data) throws DAOException
   :outertype: InboxDAO

findInboxNextOrderNo
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public long findInboxNextOrderNo() throws DAOException
   :outertype: InboxDAO

   Returns next value of inbox order no. from DB sequence. it determines message order being retrieved by client.

   :return: the value of next inbox order no.

updateInbox
^^^^^^^^^^^

.. java:method:: public boolean updateInbox(InboxDVO data) throws DAOException
   :outertype: InboxDAO

