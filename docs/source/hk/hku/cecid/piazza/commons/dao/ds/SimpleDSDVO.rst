.. java:import:: java.util Hashtable

SimpleDSDVO
===========

.. java:package:: hk.hku.cecid.piazza.commons.dao.ds
   :noindex:

.. java:type:: public class SimpleDSDVO extends DataSourceDVO

   SimpleDSDVO is just a concrete subclass of DataSourceDVO. It should not be used directly when the underlying persistent storage would be changed to any kind that does not support Java DataSource.

   :author: Hugo Y. K. Lam

Constructors
------------
SimpleDSDVO
^^^^^^^^^^^

.. java:constructor:: public SimpleDSDVO()
   :outertype: SimpleDSDVO

   Creates a new instance of SimpleDSDVO.

SimpleDSDVO
^^^^^^^^^^^

.. java:constructor:: public SimpleDSDVO(Hashtable data)
   :outertype: SimpleDSDVO

   Creates a new instance of SimpleDSDVO.

   :param data: the source data of this DVO.

