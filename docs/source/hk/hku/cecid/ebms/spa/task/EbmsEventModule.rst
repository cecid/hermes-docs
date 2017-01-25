.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.piazza.commons.module EventModule

EbmsEventModule
===============

.. java:package:: hk.hku.cecid.ebms.spa.task
   :noindex:

.. java:type:: public class EbmsEventModule extends EventModule<EbmsEventListener>

Constructors
------------
EbmsEventModule
^^^^^^^^^^^^^^^

.. java:constructor:: public EbmsEventModule(String descriptorLocation, ClassLoader loader)
   :outertype: EbmsEventModule

EbmsEventModule
^^^^^^^^^^^^^^^

.. java:constructor:: public EbmsEventModule(String descriptorLocation, boolean shouldInitialize)
   :outertype: EbmsEventModule

EbmsEventModule
^^^^^^^^^^^^^^^

.. java:constructor:: public EbmsEventModule(String descriptorLocation, ClassLoader loader, boolean shouldInitialize)
   :outertype: EbmsEventModule

EbmsEventModule
^^^^^^^^^^^^^^^

.. java:constructor:: public EbmsEventModule(String descriptorLocation)
   :outertype: EbmsEventModule

Methods
-------
fireErrorOccurred
^^^^^^^^^^^^^^^^^

.. java:method:: public void fireErrorOccurred(EbxmlMessage errorMessage)
   :outertype: EbmsEventModule

fireMessageReceived
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void fireMessageReceived(EbxmlMessage requestMessage)
   :outertype: EbmsEventModule

fireMessageSent
^^^^^^^^^^^^^^^

.. java:method:: public void fireMessageSent(EbxmlMessage requestMessage)
   :outertype: EbmsEventModule

fireResponseReceived
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void fireResponseReceived(EbxmlMessage acknowledgement)
   :outertype: EbmsEventModule

