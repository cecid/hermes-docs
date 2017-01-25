.. java:import:: hk.hku.cecid.piazza.commons.dao DAO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: java.util List

PartnershipDAO
==============

.. java:package:: hk.hku.cecid.edi.as2.dao
   :noindex:

.. java:type:: public interface PartnershipDAO extends DAO

   :author: Donahue Sze

Methods
-------
findAllPartnerships
^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findAllPartnerships() throws DAOException
   :outertype: PartnershipDAO

findByParty
^^^^^^^^^^^

.. java:method:: public PartnershipDVO findByParty(String fromParty, String toParty) throws DAOException
   :outertype: PartnershipDAO

findPartnershipsByPartyID
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findPartnershipsByPartyID(String fromParty, String toParty) throws DAOException
   :outertype: PartnershipDAO

