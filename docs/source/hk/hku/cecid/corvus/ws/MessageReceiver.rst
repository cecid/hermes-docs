.. java:import:: java.io IOException

.. java:import:: java.net MalformedURLException

.. java:import:: java.util Date

.. java:import:: java.util Iterator

.. java:import:: javax.xml.soap AttachmentPart

.. java:import:: javax.xml.soap SOAPException

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.ws.data Data

.. java:import:: hk.hku.cecid.corvus.ws.data Payload

MessageReceiver
===============

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class MessageReceiver extends SOAPSender

   The \ ``MessageReceiver``\  is the abstract class which is used to send SOAP messsage request to B2B Collector series product.

   :author: Jumbo Cheung

Constructors
------------
MessageReceiver
^^^^^^^^^^^^^^^

.. java:constructor:: public MessageReceiver(FileLogger l, Data m)
   :outertype: MessageReceiver

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param m: The message properties including how many message need to be sent and some performance parameter.

Methods
-------
clearRequestPayload
^^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean clearRequestPayload() throws SOAPException
   :outertype: MessageReceiver

   Clear all payload in the request.

getContentType
^^^^^^^^^^^^^^

.. java:method:: public String getContentType()
   :outertype: MessageReceiver

   Return the content type of the message.

   :return: The content type of message to bes sent.

getElapsedTime
^^^^^^^^^^^^^^

.. java:method:: public long getElapsedTime()
   :outertype: MessageReceiver

   Get how long it tasks for the sender to do it's tasks.

   :return: The times for the task from start to end in milleseconds.

getEndTime
^^^^^^^^^^

.. java:method:: public long getEndTime()
   :outertype: MessageReceiver

   :return: Return the end time of the sender process.

getResponsePayloads
^^^^^^^^^^^^^^^^^^^

.. java:method:: public Payload[] getResponsePayloads() throws SOAPException, IOException
   :outertype: MessageReceiver

   Get the payload from the SOAP response. This should be called during \ :java:ref:`onResponse()`\ .

   :throws SOAPException: When unable to extract the payload in the SOAP Response.
   :throws IOException: When unable to open the input stream for the payload.
   :return: A set of payload in SOAP message.

getStartTime
^^^^^^^^^^^^

.. java:method:: public long getStartTime()
   :outertype: MessageReceiver

   :return: Return the start time of the sending process.

onEnd
^^^^^

.. java:method:: public void onEnd()
   :outertype: MessageReceiver

   [@EVENT] This method is invoked when the sending execution is ended.

onError
^^^^^^^

.. java:method:: public void onError(Throwable t)
   :outertype: MessageReceiver

   [@EVENT] Log all known exceptions and stack trace.

   :param t: The exception encountered.

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: MessageReceiver

   [@EVENT] This method is invoked when the sender begins to execute the run method.

setContentType
^^^^^^^^^^^^^^

.. java:method:: public void setContentType(String contentType)
   :outertype: MessageReceiver

   Set the content type of the message to be sent.

   :param contentType: The content type of message to be sent.

