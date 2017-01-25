.. java:import:: java.io IOException

.. java:import:: java.io StringReader

.. java:import:: java.util ArrayList

.. java:import:: java.util HashMap

.. java:import:: java.util List

.. java:import:: java.util Map

.. java:import:: javax.json Json

.. java:import:: javax.json JsonArray

.. java:import:: javax.json JsonArrayBuilder

.. java:import:: javax.json JsonBuilderFactory

.. java:import:: javax.json JsonObject

.. java:import:: javax.json JsonObjectBuilder

.. java:import:: javax.json JsonReader

.. java:import:: javax.json JsonReaderFactory

.. java:import:: javax.json JsonValue

JsonUtil
========

.. java:package:: hk.hku.cecid.piazza.commons.json
   :noindex:

.. java:type:: public class JsonUtil

Methods
-------
fromDictionary
^^^^^^^^^^^^^^

.. java:method:: public static String fromDictionary(Map<String, Object> dictionary)
   :outertype: JsonUtil

toDictionary
^^^^^^^^^^^^

.. java:method:: public static Map<String, Object> toDictionary(String source) throws JsonParseException
   :outertype: JsonUtil

