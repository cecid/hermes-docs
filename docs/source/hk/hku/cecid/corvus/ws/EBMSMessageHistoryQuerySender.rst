.. java:import:: java.io BufferedReader

.. java:import:: java.io File

.. java:import:: java.io InputStreamReader

.. java:import:: java.util ArrayList

.. java:import:: java.util Date

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: javax.xml.soap SOAPElement

.. java:import:: javax.xml.soap SOAPException

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.util SOAPUtilities

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSMessageData

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSStatusQueryData

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSStatusQueryResponseData

.. java:import:: hk.hku.cecid.corvus.ws.data EBMSMessageHistoryRequestData

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

EBMSMessageHistoryQuerySender
=============================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class EBMSMessageHistoryQuerySender extends SOAPSender

Fields
------
NAMESPACE
^^^^^^^^^

.. java:field:: public static String NAMESPACE
   :outertype: EBMSMessageHistoryQuerySender

Constructors
------------
EBMSMessageHistoryQuerySender
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EBMSMessageHistoryQuerySender(FileLogger l, EBMSMessageHistoryRequestData m)
   :outertype: EBMSMessageHistoryQuerySender

Methods
-------
getAvailableMessages
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List getAvailableMessages()
   :outertype: EBMSMessageHistoryQuerySender

getResponseElementList
^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public List getResponseElementList(String tagname, String nsURI, int whichOne) throws SOAPException
   :outertype: EBMSMessageHistoryQuerySender

initializeMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void initializeMessage() throws Exception
   :outertype: EBMSMessageHistoryQuerySender

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: EBMSMessageHistoryQuerySender

   The main method is for CLI mode.

onResponse
^^^^^^^^^^

.. java:method:: public void onResponse() throws Exception
   :outertype: EBMSMessageHistoryQuerySender

onStart
^^^^^^^

.. java:method:: public void onStart()
   :outertype: EBMSMessageHistoryQuerySender

