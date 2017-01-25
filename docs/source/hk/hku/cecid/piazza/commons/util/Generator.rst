.. java:import:: java.net InetAddress

.. java:import:: java.util Date

.. java:import:: java.util UUID

Generator
=========

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public class Generator

   Generator is a convenient class for generating various standard objects. For instance, a message ID which conforms to RFC2822.

   :author: Hugo Y. K. Lam

Methods
-------
generateMessageID
^^^^^^^^^^^^^^^^^

.. java:method:: public static String generateMessageID()
   :outertype: Generator

   Generates a message ID which conforms to \ `RFC2822 <http://www.ietf.org/rfc/rfc2822.txt>`_\

   :return: the message ID.

generateUUID
^^^^^^^^^^^^

.. java:method:: public static String generateUUID()
   :outertype: Generator

   Generates a UUID which conforms to \ `ISO/IEC 11578:1996 <http://www.iso.ch/cate/d2229.html>`_\

   :return: the UUID.

