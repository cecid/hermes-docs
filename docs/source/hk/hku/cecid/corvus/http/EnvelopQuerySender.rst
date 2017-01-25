.. java:import:: java.util Date

.. java:import:: java.util Map

.. java:import:: java.util List

.. java:import:: java.util ArrayList

.. java:import:: java.io InputStream

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io BufferedInputStream

.. java:import:: java.io IOException

.. java:import:: java.io File

.. java:import:: java.io FileInputStream

.. java:import:: java.nio.channels FileChannel

.. java:import:: java.nio.channels Channels

.. java:import:: org.apache.http.client.methods HttpRequestBase

.. java:import:: org.apache.http.client.methods HttpPost

.. java:import:: org.apache.http.client.methods CloseableHttpResponse

.. java:import:: org.apache.http NameValuePair

.. java:import:: org.apache.http.message BasicNameValuePair

.. java:import:: org.apache.http.client.entity UrlEncodedFormEntity

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data Data

.. java:import:: hk.hku.cecid.corvus.ws.data KVPairData

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

EnvelopQuerySender
==================

.. java:package:: hk.hku.cecid.corvus.http
   :noindex:

.. java:type:: public class EnvelopQuerySender extends HttpSender

   The \ ``EnvelopSender``\  is abstract base class for sending HTTP remote request to H2O for querying the message envelop through the administration page.

   :author: Twinsen Tsang

Fields
------
MSGBOX_FORM_PARAM
^^^^^^^^^^^^^^^^^

.. java:field:: protected static final String MSGBOX_FORM_PARAM
   :outertype: EnvelopQuerySender

   The constant field representing the HTTP request parameter name for Message box.

MSGBOX_IN
^^^^^^^^^

.. java:field:: public static final String MSGBOX_IN
   :outertype: EnvelopQuerySender

   The constant field representing the standardized incoming message box representation

MSGBOX_OUT
^^^^^^^^^^

.. java:field:: public static final String MSGBOX_OUT
   :outertype: EnvelopQuerySender

   The constant field representing the standardized outgoing message box representation

MSGID_FORM_PARAM
^^^^^^^^^^^^^^^^

.. java:field:: protected static final String MSGID_FORM_PARAM
   :outertype: EnvelopQuerySender

   The constant field representing the HTTP request parameter name for Message id.

Constructors
------------
EnvelopQuerySender
^^^^^^^^^^^^^^^^^^

.. java:constructor:: protected EnvelopQuerySender(FileLogger logger, Data d)
   :outertype: EnvelopQuerySender

   Explicit Constructor. Create an instance of \ ``EnvelopQuerySender``\

   :param logger: The logger for log the sending process.
   :param d: The data used for generate Envelop query request. It must be a kind of Admin data.

EnvelopQuerySender
^^^^^^^^^^^^^^^^^^

.. java:constructor:: protected EnvelopQuerySender(FileLogger logger, Data d, String username, String password)
   :outertype: EnvelopQuerySender

   Explicit Constructor. Create an instance of \ ``EnvelopQuerySender``\

   :param logger: The logger for log the sending process.
   :param d: The data used for generate Envelop query request. It must be a kind of Admin data.
   :param username: The username for authentication
   :param password: The password for authentication

Methods
-------
getEnvelopStream
^^^^^^^^^^^^^^^^

.. java:method:: public final InputStream getEnvelopStream() throws IOException
   :outertype: EnvelopQuerySender

   This method should be called after executed \ :java:ref:`run()`\  successfully.

   :return: The message envelop stream.

getMessageBoxMapping
^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected Map getMessageBoxMapping()
   :outertype: EnvelopQuerySender

   Get the message box mapping from standardized representation to proprietary representation.  It should return a HashMap like this:

   .. parsed-literal::

      HashMap m = new HashMap();
      m.put(MSGBOX_IN , "Your Inbox representation");
      m.put(MSGBOX_OUT, "Your outbox representation");

   :return: the message box mapping.

   **See also:** :java:ref:`EnvelopQuerySender.MSGBOX_IN`, :java:ref:`EnvelopQuerySender.MSGBOX_OUT`

getMessageBoxToDownload
^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public final String getMessageBoxToDownload()
   :outertype: EnvelopQuerySender

   :return: The message box to donw-load the message envelop. either INBOX or OUTBOX.

getMessageIdToDownload
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public final String getMessageIdToDownload()
   :outertype: EnvelopQuerySender

   :return: The message id to down-load the message envelop.

onCreateRequest
^^^^^^^^^^^^^^^

.. java:method:: protected HttpRequestBase onCreateRequest() throws Exception
   :outertype: EnvelopQuerySender

   [@EVENT] This method is invoked when the sender is required to create a HTTP Request from configuration.  It generates a form-url-encoded content embedded in the HTTP POST request. It contains two parameters, message_id and message_box. The value of these parameters are extracted from \ :java:ref:`getMessageIdToDownload()`\  and \ :java:ref:`getMessageBoxToDownload()`\  respectively.  \ **NOTE**\ : The values of message_box parameter may differ to what you see because it may transform \ :java:ref:`getMessageBoxMapping()`\ .

   :throws NullPointerException: When \ :java:ref:`getMessageIdToDownload()`\  return null. When \ :java:ref:`getMessageBoxToDownload()`\  return empty or null.
   :throws IllegalArgumentException: When \ :java:ref:`getMessageBoxToDownload()`\  return string not equal to 'INBOX' and 'OUTBOX'

onResponse
^^^^^^^^^^

.. java:method:: protected void onResponse() throws Exception
   :outertype: EnvelopQuerySender

   [@EVENT] This method is invoked when received the reply HTTP response from the server.  It saves the response body stream and then available to get through by \ :java:ref:`getEnvelopStream()`\

onStart
^^^^^^^

.. java:method:: protected void onStart()
   :outertype: EnvelopQuerySender

   [@EVENT] The method \ ``onStart``\  log all new configuration.

setMessageCriteriaToDownload
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public final void setMessageCriteriaToDownload(String messageId, String messageBox)
   :outertype: EnvelopQuerySender

   Set the message criteria for down-load the message envelop (and payload).

   :param messageId: The message id to down-load the message envelop.
   :param messageBox: The message box to down-load the message envelop. either INBOX or OUTBOX.
   :throws NullPointerException: When \ :java:ref:`getMessageIdToDownload()`\  return null. When \ :java:ref:`getMessageBoxToDownload()`\  return empty or null.
   :throws IllegalArgumentException: When \ :java:ref:`getMessageBoxToDownload()`\  return string not equal to 'INBOX' and 'OUTBOX'

