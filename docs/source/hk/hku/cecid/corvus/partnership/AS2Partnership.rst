.. java:import:: java.io FileInputStream

.. java:import:: java.io FileNotFoundException

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.util ArrayList

.. java:import:: java.util List

.. java:import:: hk.hku.cecid.edi.as2.dao PartnershipDAO

.. java:import:: hk.hku.cecid.edi.as2.dao PartnershipDVO

.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOFactory

.. java:import:: org.dom4j Document

.. java:import:: org.dom4j DocumentException

.. java:import:: org.dom4j Element

.. java:import:: org.dom4j.io SAXReader

.. java:import:: org.xml.sax SAXException

AS2Partnership
==============

.. java:package:: hk.hku.cecid.corvus.partnership
   :noindex:

.. java:type:: public class AS2Partnership

   The \ ``AS2Partnership``\  is the utilities for maintaining the partnership of AS2. In current version, it support addition or deletion of the partnership.

   :author: kochiu, Twinsen Tsang (modifiers)

   **See also:** :java:ref:`.createAS2Partnership(String)`, :java:ref:`.removeAS2Partnership(String)`

Methods
-------
createAS2Partnership
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static boolean createAS2Partnership(String xmlFile) throws DAOException, DocumentException, SAXException, IOException
   :outertype: AS2Partnership

   Create a AS2 partnership with the configuration defined in the \ ``XMLFile``\ .

   :param xmlFile: The partnership XML instance file. It is located at "/data/as2.xml".
   :throws DAOException: Error in persistence connectivity.
   :throws DocumentException: Error in reading the parameter in the \ ``xmlFile``\ .
   :throws SAXException: Error in parsing the \ ``xmlFile``\ .
   :throws IOException:
   :return: true if the removal operation ran successfully.

main
^^^^

.. java:method:: public static void main(String[] args)
   :outertype: AS2Partnership

   The entry point for CLI.

   :param args: The arguments have two parametes. The first one is the partnership maintenance which is either "-a" (add) or "-d" (delete). The second one is the xml file containing the partnership information. They are located at the "conf/as2.xml" relative to the program folders.

removeAS2Partnership
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static boolean removeAS2Partnership(String xmlFile) throws DAOException, DocumentException, FileNotFoundException, SAXException
   :outertype: AS2Partnership

   Remove a particular partnership defined in the \ ``xmlFile``\ . Only the attributes <id> in the \ ``xmlFile``\  will be used for removing partnership.

   :param xmlFile: The partnership XML instance file. It is located at "/data/ebms.xml".
   :throws DAOException: Error in persistence connectivity.
   :throws DocumentException: Error in reading the parameter in the \ ``xmlFile``\ .
   :throws SAXException: Error in parsing the \ ``xmlFile``\ .
   :throws IOException:
   :return: true if the removal operation ran successfully.

