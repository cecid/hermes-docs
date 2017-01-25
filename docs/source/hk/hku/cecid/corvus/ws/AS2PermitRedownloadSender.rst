.. java:import:: javax.xml.soap SOAPElement

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.util SOAPUtilities

.. java:import:: hk.hku.cecid.corvus.ws.data Data

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data PermitRedownloadData

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

AS2PermitRedownloadSender
=========================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class AS2PermitRedownloadSender extends PermitRedownloadServiceSender

Constructors
------------
AS2PermitRedownloadSender
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public AS2PermitRedownloadSender(FileLogger l, Data m)
   :outertype: AS2PermitRedownloadSender

Methods
-------
getNSURI
^^^^^^^^

.. java:method:: @Override protected String getNSURI()
   :outertype: AS2PermitRedownloadSender

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: AS2PermitRedownloadSender

   The main method is for CLI mode.

onError
^^^^^^^

.. java:method:: @Override public void onError(Throwable t)
   :outertype: AS2PermitRedownloadSender

onResponse
^^^^^^^^^^

.. java:method:: @Override public void onResponse() throws Exception
   :outertype: AS2PermitRedownloadSender

