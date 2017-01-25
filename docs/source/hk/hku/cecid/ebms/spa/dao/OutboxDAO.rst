.. java:import:: hk.hku.cecid.piazza.commons.dao DAO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: java.util List

OutboxDAO
=========

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public interface OutboxDAO extends DAO

   :author: Donahue Sze

Methods
-------
addOutbox
^^^^^^^^^

.. java:method:: public void addOutbox(OutboxDVO data) throws DAOException
   :outertype: OutboxDAO

deleteOutbox
^^^^^^^^^^^^

.. java:method:: public void deleteOutbox(OutboxDVO data) throws DAOException
   :outertype: OutboxDAO

findOutbox
^^^^^^^^^^

.. java:method:: public boolean findOutbox(OutboxDVO data) throws DAOException
   :outertype: OutboxDAO

selectOutbox
^^^^^^^^^^^^

.. java:method:: public List selectOutbox() throws DAOException
   :outertype: OutboxDAO

updateOutbox
^^^^^^^^^^^^

.. java:method:: public boolean updateOutbox(OutboxDVO data) throws DAOException
   :outertype: OutboxDAO

