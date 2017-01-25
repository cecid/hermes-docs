DispositionException
====================

.. java:package:: hk.hku.cecid.edi.as2.pkg
   :noindex:

.. java:type:: public class DispositionException extends RuntimeException

   DispositionException is a runtime exception representing an error-level disposition.

   :author: Hugo Y. K. Lam

Constructors
------------
DispositionException
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public DispositionException(Disposition disposition, String text, Throwable cause)
   :outertype: DispositionException

DispositionException
^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public DispositionException(Disposition disposition, String text)
   :outertype: DispositionException

Methods
-------
getDisposition
^^^^^^^^^^^^^^

.. java:method:: public Disposition getDisposition()
   :outertype: DispositionException

getText
^^^^^^^

.. java:method:: public String getText()
   :outertype: DispositionException

setDisposition
^^^^^^^^^^^^^^

.. java:method:: public void setDisposition(Disposition disposition)
   :outertype: DispositionException

setText
^^^^^^^

.. java:method:: public void setText(String string)
   :outertype: DispositionException

