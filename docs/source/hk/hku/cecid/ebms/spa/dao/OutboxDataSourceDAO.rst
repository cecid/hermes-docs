.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDAO

.. java:import:: java.util List

OutboxDataSourceDAO
===================

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public class OutboxDataSourceDAO extends DataSourceDAO implements OutboxDAO

   :author: Donahue Sze Window - Preferences - Java - Code Style - Code Templates

Methods
-------
addOutbox
^^^^^^^^^

.. java:method:: public void addOutbox(OutboxDVO data) throws DAOException
   :outertype: OutboxDataSourceDAO

createDVO
^^^^^^^^^

.. java:method:: public DVO createDVO()
   :outertype: OutboxDataSourceDAO

deleteOutbox
^^^^^^^^^^^^

.. java:method:: public void deleteOutbox(OutboxDVO data) throws DAOException
   :outertype: OutboxDataSourceDAO

findOutbox
^^^^^^^^^^

.. java:method:: public boolean findOutbox(OutboxDVO data) throws DAOException
   :outertype: OutboxDataSourceDAO

selectOutbox
^^^^^^^^^^^^

.. java:method:: public List selectOutbox() throws DAOException
   :outertype: OutboxDataSourceDAO

updateOutbox
^^^^^^^^^^^^

.. java:method:: public boolean updateOutbox(OutboxDVO data) throws DAOException
   :outertype: OutboxDataSourceDAO

