.. java:import:: hk.hku.cecid.piazza.commons.dao DAO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: java.util List

PartnershipDAO
==============

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public interface PartnershipDAO extends DAO

   :author: Donahue Sze

Methods
-------
findAllPartnerships
^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findAllPartnerships() throws DAOException
   :outertype: PartnershipDAO

findPartnershipByCPA
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean findPartnershipByCPA(PartnershipDVO data) throws DAOException
   :outertype: PartnershipDAO

findPartnershipsByCPA
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List findPartnershipsByCPA(PartnershipDVO data) throws DAOException
   :outertype: PartnershipDAO

