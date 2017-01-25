.. java:import:: hk.hku.cecid.ebms.pkg EbxmlMessage

.. java:import:: hk.hku.cecid.piazza.commons.module Component

EbmsEventListener
=================

.. java:package:: hk.hku.cecid.ebms.spa.task
   :noindex:

.. java:type:: public abstract class EbmsEventListener extends Component

Methods
-------
errorOccurred
^^^^^^^^^^^^^

.. java:method:: public abstract void errorOccurred(EbxmlMessage errorMessage)
   :outertype: EbmsEventListener

messageReceived
^^^^^^^^^^^^^^^

.. java:method:: public abstract void messageReceived(EbxmlMessage requestMessage)
   :outertype: EbmsEventListener

messageSent
^^^^^^^^^^^

.. java:method:: public abstract void messageSent(EbxmlMessage requestMessage)
   :outertype: EbmsEventListener

responseReceived
^^^^^^^^^^^^^^^^

.. java:method:: public abstract void responseReceived(EbxmlMessage acknowledgement)
   :outertype: EbmsEventListener

