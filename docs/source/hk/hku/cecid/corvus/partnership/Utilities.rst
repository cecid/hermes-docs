.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io FileInputStream

.. java:import:: java.io IOException

.. java:import:: java.security.cert CertificateFactory

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: org.dom4j Element

Utilities
=========

.. java:package:: hk.hku.cecid.corvus.partnership
   :noindex:

.. java:type:: public class Utilities

   Comment for Utilities.java.

   :author: kochiu

Methods
-------
getBooleanValue
^^^^^^^^^^^^^^^

.. java:method:: public static boolean getBooleanValue(Element params, String paramName)
   :outertype: Utilities

isValidCert
^^^^^^^^^^^

.. java:method:: public static boolean isValidCert(byte[] cert)
   :outertype: Utilities

loadCert
^^^^^^^^

.. java:method:: public static byte[] loadCert(String filepath) throws IOException
   :outertype: Utilities

