.. java:import:: java.net MalformedURLException

.. java:import:: java.util Date

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPException

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.util SOAPUtilities

.. java:import:: hk.hku.cecid.corvus.ws.data AS2MessageData

.. java:import:: hk.hku.cecid.corvus.ws.data Data

.. java:import:: hk.hku.cecid.corvus.ws.data PermitRedownloadData

PermitRedownloadServiceSender
=============================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public abstract class PermitRedownloadServiceSender extends SOAPSender

Constructors
------------
PermitRedownloadServiceSender
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public PermitRedownloadServiceSender(FileLogger l, Data m)
   :outertype: PermitRedownloadServiceSender

   Explicit Constructor.

   :param l: The logger used for log message and exception.
   :param m: The message properties including how many message need to be sent and some performance parameter.

Methods
-------
getElapsedTime
^^^^^^^^^^^^^^

.. java:method:: public long getElapsedTime()
   :outertype: PermitRedownloadServiceSender

   Get how long it tasks for the sender to do it's tasks.

   :return: The times for the task from start to end in milleseconds.

getEndTime
^^^^^^^^^^

.. java:method:: public long getEndTime()
   :outertype: PermitRedownloadServiceSender

   :return: Return the end time of the sender process.

getNSURI
^^^^^^^^

.. java:method:: protected abstract String getNSURI()
   :outertype: PermitRedownloadServiceSender

getResponseElementText
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getResponseElementText(String tagname, String nsURI, int whichOne) throws SOAPException
   :outertype: PermitRedownloadServiceSender

   This method should only be called inside \ :java:ref:`onResponse()`\ . because the response object will be deleted upon each ws call.

   :param tagname: The tag name of element to be retrieved.
   :param nsURI: The namespace URI.
   :param whichOne: The nth child element to be returned.
   :return: The element text in the tagname specified.

getStartTime
^^^^^^^^^^^^

.. java:method:: public long getStartTime()
   :outertype: PermitRedownloadServiceSender

   :return: Return the start time of the sending process.

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws SOAPException
   :outertype: PermitRedownloadServiceSender

   Initialize Sender and Construct Message Request

onEnd
^^^^^

.. java:method:: public void onEnd()
   :outertype: PermitRedownloadServiceSender

   [@EVENT] This method is invoked when the sending execution is ended.

onError
^^^^^^^

.. java:method:: public void onError(Throwable t)
   :outertype: PermitRedownloadServiceSender

   [@EVENT] Log all known exceptions and stack trace.

   :param t: The exception encountered.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: PermitRedownloadServiceSender

   Record the message id.

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: PermitRedownloadServiceSender

   [@EVENT] This method is invoked when the sender begins to execute the run method.

