.. java:import:: hk.hku.cecid.piazza.commons.dao DAO

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

RepositoryDAO
=============

.. java:package:: hk.hku.cecid.ebms.spa.dao
   :noindex:

.. java:type:: public interface RepositoryDAO extends DAO

   :author: Donahue Sze

Methods
-------
addRepository
^^^^^^^^^^^^^

.. java:method:: public void addRepository(RepositoryDVO data) throws DAOException
   :outertype: RepositoryDAO

deleteRepository
^^^^^^^^^^^^^^^^

.. java:method:: public void deleteRepository(RepositoryDVO data) throws DAOException
   :outertype: RepositoryDAO

findRepository
^^^^^^^^^^^^^^

.. java:method:: public boolean findRepository(RepositoryDVO data) throws DAOException
   :outertype: RepositoryDAO

updateRepository
^^^^^^^^^^^^^^^^

.. java:method:: public boolean updateRepository(RepositoryDVO data) throws DAOException
   :outertype: RepositoryDAO

