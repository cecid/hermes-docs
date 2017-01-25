.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: hk.hku.cecid.piazza.commons.module Component

AS2EventListener
================

.. java:package:: hk.hku.cecid.edi.as2.module
   :noindex:

.. java:type:: public abstract class AS2EventListener extends Component

Methods
-------
errorOccurred
^^^^^^^^^^^^^

.. java:method:: public abstract void errorOccurred(AS2Message errorResponse)
   :outertype: AS2EventListener

messageReceived
^^^^^^^^^^^^^^^

.. java:method:: public abstract void messageReceived(AS2Message requestMessage)
   :outertype: AS2EventListener

messageSent
^^^^^^^^^^^

.. java:method:: public abstract void messageSent(AS2Message requestMessage)
   :outertype: AS2EventListener

responseReceived
^^^^^^^^^^^^^^^^

.. java:method:: public abstract void responseReceived(AS2Message response)
   :outertype: AS2EventListener

