.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io InputStream

.. java:import:: java.io IOException

.. java:import:: java.io OutputStreamWriter

.. java:import:: java.util Date

.. java:import:: java.util HashMap

.. java:import:: java.util Map

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.servlet.http HttpServletResponse

.. java:import:: hk.hku.cecid.piazza.commons.json JsonParseException

.. java:import:: hk.hku.cecid.piazza.commons.json JsonUtil

.. java:import:: hk.hku.cecid.piazza.commons.rest RestRequest

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: hk.hku.cecid.piazza.commons.servlet.http HttpRequestAdaptor

.. java:import:: hk.hku.cecid.hermes.api Constants

HermesAbstractApiListener
=========================

.. java:package:: hk.hku.cecid.hermes.api.listener
   :noindex:

.. java:type:: public class HermesAbstractApiListener extends HttpRequestAdaptor

   HermesAbstractApiListener

   :author: Patrick Yee

Constructors
------------
HermesAbstractApiListener
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public HermesAbstractApiListener()
   :outertype: HermesAbstractApiListener

Methods
-------
createActionResult
^^^^^^^^^^^^^^^^^^

.. java:method:: protected Map<String, Object> createActionResult(String id, boolean success)
   :outertype: HermesAbstractApiListener

createError
^^^^^^^^^^^

.. java:method:: protected Map<String, Object> createError(int code, String message)
   :outertype: HermesAbstractApiListener

fillDate
^^^^^^^^

.. java:method:: protected void fillDate(Map<String, Object> dictionary)
   :outertype: HermesAbstractApiListener

getDictionaryFromRequest
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected Map<String, Object> getDictionaryFromRequest(HttpServletRequest request) throws IOException, JsonParseException
   :outertype: HermesAbstractApiListener

processApi
^^^^^^^^^^

.. java:method:: protected Map<String, Object> processApi(RestRequest request) throws RequestListenerException
   :outertype: HermesAbstractApiListener

processDeleteRequest
^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected Map<String, Object> processDeleteRequest(RestRequest request) throws RequestListenerException
   :outertype: HermesAbstractApiListener

processGetRequest
^^^^^^^^^^^^^^^^^

.. java:method:: protected Map<String, Object> processGetRequest(RestRequest request) throws RequestListenerException
   :outertype: HermesAbstractApiListener

processPostRequest
^^^^^^^^^^^^^^^^^^

.. java:method:: protected Map<String, Object> processPostRequest(RestRequest request) throws RequestListenerException
   :outertype: HermesAbstractApiListener

processRequest
^^^^^^^^^^^^^^

.. java:method:: public String processRequest(HttpServletRequest request, HttpServletResponse response) throws RequestListenerException
   :outertype: HermesAbstractApiListener

   processRequest

   :param request:
   :param response:
   :throws RequestListenerException:
   :return: String

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.servlet.http.HttpRequestListener.processRequest(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse)`

