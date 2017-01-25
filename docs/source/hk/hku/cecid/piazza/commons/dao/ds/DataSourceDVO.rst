.. java:import:: hk.hku.cecid.piazza.commons.dao AbstractDVO

.. java:import:: java.util Hashtable

DataSourceDVO
=============

.. java:package:: hk.hku.cecid.piazza.commons.dao.ds
   :noindex:

.. java:type:: public abstract class DataSourceDVO extends AbstractDVO

   The DataSourceDVO, which implements the DVO interface, is simply a subclass of the AbstractDVO. It is expected to be used by a DataSourceDAOFactory.

   :author: Hugo Y. K. Lam

Constructors
------------
DataSourceDVO
^^^^^^^^^^^^^

.. java:constructor:: protected DataSourceDVO()
   :outertype: DataSourceDVO

   Creates a new instance of DataSourceDVO.

DataSourceDVO
^^^^^^^^^^^^^

.. java:constructor:: protected DataSourceDVO(Hashtable data)
   :outertype: DataSourceDVO

   Creates a new instance of DataSourceDVO.

   :param data: the source data of this DVO.

