.. java:import:: hk.hku.cecid.piazza.commons.dao DVO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao.ds DataSourceDAO

.. java:import:: java.util List

PartnershipDataSourceDAO
========================

.. java:package:: hk.hku.cecid.edi.as2.dao
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

findByParty
^^^^^^^^^^^

.. java:method:: public PartnershipDVO findByParty(String fromParty, String toParty) throws DAOException
   :outertype: PartnershipDataSourceDAO

findPartnershipsByPartyID
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findPartnershipsByPartyID(String fromParty, String toParty) throws DAOException
   :outertype: PartnershipDataSourceDAO

