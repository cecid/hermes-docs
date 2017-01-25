.. java:import:: java.util ArrayList

HermesProtocolApiListener
=========================

.. java:package:: hk.hku.cecid.hermes.api.listener
   :noindex:

.. java:type:: public class HermesProtocolApiListener extends HermesAbstractApiListener

   HermesProtocolApiListener

   :author: Patrick Yee

Methods
-------
parseFromPathInfo
^^^^^^^^^^^^^^^^^

.. java:method:: protected ArrayList<String> parseFromPathInfo(String pathInfo)
   :outertype: HermesProtocolApiListener

parseFromPathInfo
^^^^^^^^^^^^^^^^^

.. java:method:: protected ArrayList<String> parseFromPathInfo(String pathInfo, int numActionParts)
   :outertype: HermesProtocolApiListener

   Returns a list of three strings: [ action, protocol, parameter ]

