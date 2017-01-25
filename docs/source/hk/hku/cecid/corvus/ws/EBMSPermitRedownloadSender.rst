.. java:import:: javax.xml.soap SOAPElement

.. java:import:: hk.hku.cecid.corvus.util FileLogger

.. java:import:: hk.hku.cecid.corvus.util SOAPUtilities

.. java:import:: hk.hku.cecid.corvus.ws.data Data

.. java:import:: hk.hku.cecid.corvus.ws.data DataFactory

.. java:import:: hk.hku.cecid.corvus.ws.data PermitRedownloadData

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

EBMSPermitRedownloadSender
==========================

.. java:package:: hk.hku.cecid.corvus.ws
   :noindex:

.. java:type:: public class EBMSPermitRedownloadSender extends PermitRedownloadServiceSender

Constructors
------------
EBMSPermitRedownloadSender
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public EBMSPermitRedownloadSender(FileLogger l, Data m)
   :outertype: EBMSPermitRedownloadSender

Methods
-------
getNSURI
^^^^^^^^

.. java:method:: @Override protected String getNSURI()
   :outertype: EBMSPermitRedownloadSender

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: EBMSPermitRedownloadSender

   The main method is for CLI mode.

onError
^^^^^^^

.. java:method:: @Override public void onError(Throwable t)
   :outertype: EBMSPermitRedownloadSender

onResponse
^^^^^^^^^^

.. java:method:: @Override public void onResponse() throws Exception
   :outertype: EBMSPermitRedownloadSender

