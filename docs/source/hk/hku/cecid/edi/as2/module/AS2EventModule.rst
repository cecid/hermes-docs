.. java:import:: hk.hku.cecid.edi.as2 AS2PlusProcessor

.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: hk.hku.cecid.piazza.commons.module EventModule

AS2EventModule
==============

.. java:package:: hk.hku.cecid.edi.as2.module
   :noindex:

.. java:type:: public class AS2EventModule extends EventModule<AS2EventListener>

Constructors
------------
AS2EventModule
^^^^^^^^^^^^^^

.. java:constructor:: public AS2EventModule(String descriptorLocation, ClassLoader loader)
   :outertype: AS2EventModule

AS2EventModule
^^^^^^^^^^^^^^

.. java:constructor:: public AS2EventModule(String descriptorLocation, boolean shouldInitialize)
   :outertype: AS2EventModule

AS2EventModule
^^^^^^^^^^^^^^

.. java:constructor:: public AS2EventModule(String descriptorLocation, ClassLoader loader, boolean shouldInitialize)
   :outertype: AS2EventModule

AS2EventModule
^^^^^^^^^^^^^^

.. java:constructor:: public AS2EventModule(String descriptorLocation)
   :outertype: AS2EventModule

Methods
-------
fireErrorOccurred
^^^^^^^^^^^^^^^^^

.. java:method:: public void fireErrorOccurred(AS2Message errorResponse)
   :outertype: AS2EventModule

fireMessageReceived
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void fireMessageReceived(AS2Message requestMessage)
   :outertype: AS2EventModule

fireMessageSent
^^^^^^^^^^^^^^^

.. java:method:: public void fireMessageSent(AS2Message requestMessage)
   :outertype: AS2EventModule

fireResponseReceived
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void fireResponseReceived(AS2Message receipt)
   :outertype: AS2EventModule

