.. java:import:: java.util HashMap

.. java:import:: java.util Map

.. java:import:: hk.hku.cecid.piazza.commons.rest RestRequest

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: hk.hku.cecid.hermes.api Constants

.. java:import:: hk.hku.cecid.hermes.api.spa ApiPlugin

HermesApiListener
=================

.. java:package:: hk.hku.cecid.hermes.api.listener
   :noindex:

.. java:type:: public class HermesApiListener extends HermesAbstractApiListener

   HermesApiListener

   :author: Patrick Yee

Methods
-------
createStatusObject
^^^^^^^^^^^^^^^^^^

.. java:method:: protected Map<String, Object> createStatusObject()
   :outertype: HermesApiListener

processGetRequest
^^^^^^^^^^^^^^^^^

.. java:method:: protected Map<String, Object> processGetRequest(RestRequest request) throws RequestListenerException
   :outertype: HermesApiListener

