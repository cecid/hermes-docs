.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.util SOAPUtilities

.. java:import:: hk.hku.cecid.corvus.ws.data AS2MessageData

.. java:import:: hk.hku.cecid.corvus.ws.data AS2MessageHistoryRequestData

.. java:import:: hk.hku.cecid.corvus.ws.data AS2StatusQueryData

.. java:import:: hk.hku.cecid.corvus.ws.data AS2StatusQueryResponseData

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: java.io BufferedReader

.. java:import:: java.io File

.. java:import:: java.io InputStreamReader

.. java:import:: java.util ArrayList

.. java:import:: java.util Date

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPException

AS2MessageHistoryQuerySender
============================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class AS2MessageHistoryQuerySender extends SOAPSender

Fields
------
NAMESPACE
^^^^^^^^^

.. java:field:: public static String NAMESPACE
   :outertype: AS2MessageHistoryQuerySender

Constructors
------------
AS2MessageHistoryQuerySender
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AS2MessageHistoryQuerySender(FileLogger l, AS2MessageHistoryRequestData m)
   :outertype: AS2MessageHistoryQuerySender

Methods
-------
getAvailableMessages
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List getAvailableMessages()
   :outertype: AS2MessageHistoryQuerySender

getResponseElementList
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List getResponseElementList(String tagname, String nsURI, int whichOne) throws SOAPException
   :outertype: AS2MessageHistoryQuerySender

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: AS2MessageHistoryQuerySender

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: AS2MessageHistoryQuerySender

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: AS2MessageHistoryQuerySender

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: AS2MessageHistoryQuerySender

