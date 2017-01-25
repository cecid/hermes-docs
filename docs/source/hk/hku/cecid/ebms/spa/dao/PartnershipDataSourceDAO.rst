.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDAO

.. java:import:: java.util Iterator

.. java:import:: java.util List

PartnershipDataSourceDAO
========================

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public class PartnershipDataSourceDAO extends DataSourceDAO implements PartnershipDAO

   :author: Donahue Sze

Methods
-------
createDVO
^^^^^^^^^

.. java:method:: public DVO createDVO()
   :outertype: PartnershipDataSourceDAO

findAllPartnerships
^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findAllPartnerships() throws DAOException
   :outertype: PartnershipDataSourceDAO

findPartnershipByCPA
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean findPartnershipByCPA(PartnershipDVO data) throws DAOException
   :outertype: PartnershipDataSourceDAO

findPartnershipsByCPA
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findPartnershipsByCPA(PartnershipDVO data) throws DAOException
   :outertype: PartnershipDataSourceDAO

