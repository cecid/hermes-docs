PartnershipOp
=============

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public interface PartnershipOp

   The \ ``PartnershipOperation``\  is the signature interface for providing a clue that the implemented class should able to handle add/delete/update operation one or more kind of partnerships.

   :author: Twinsen Tsang

Fields
------
ADD
^^^

.. java:field::  int ADD
   :outertype: PartnershipOp

   The constant field indicate the adding partnership operation *

DELETE
^^^^^^

.. java:field::  int DELETE
   :outertype: PartnershipOp

   The constant field indicate the deleting partnership operation *

OP_LEN
^^^^^^

.. java:field::  int OP_LEN
   :outertype: PartnershipOp

   The constant field indicate the total number of partnership operation enumeration. DO NOT USE. *

UPDATE
^^^^^^

.. java:field::  int UPDATE
   :outertype: PartnershipOp

   The constant field indicate the update partnership operation *

Methods
-------
getExecuteOperation
^^^^^^^^^^^^^^^^^^^

.. java:method::  int getExecuteOperation()
   :outertype: PartnershipOp

   :return: Get the partnership operation type for execution.

setExecuteOperation
^^^^^^^^^^^^^^^^^^^

.. java:method::  void setExecuteOperation(int op)
   :outertype: PartnershipOp

   The interface contract indicate the partnership operation you want to execute to the realizing class. The \ ``op``\  should be greater than zero and less than {@value #OP_LEN}.

   :param op: The partnership operation type.

