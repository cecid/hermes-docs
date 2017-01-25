.. java:import:: java.util Properties

RequestListener
===============

.. java:package:: hk.hku.cecid.piazza.commons.servlet
   :noindex:

.. java:type:: public interface RequestListener

   RequestListener is a listener for handling servlet requests.

   :author: Hugo Y. K. Lam

Methods
-------
getParameters
^^^^^^^^^^^^^

.. java:method:: public Properties getParameters()
   :outertype: RequestListener

   Gets the parameters of this listener.

   :return: the parameters of this listener.

listenerCreated
^^^^^^^^^^^^^^^

.. java:method:: public void listenerCreated() throws RequestListenerException
   :outertype: RequestListener

   Invoked after the listener has been created and before it can handle any request.

   :throws RequestListenerException: if the invoked process has errors.

listenerDestroyed
^^^^^^^^^^^^^^^^^

.. java:method:: public void listenerDestroyed() throws RequestListenerException
   :outertype: RequestListener

   Invoked after the listener has been taken out from service and before disposal.

   :throws RequestListenerException: if the invoked process has errors.

