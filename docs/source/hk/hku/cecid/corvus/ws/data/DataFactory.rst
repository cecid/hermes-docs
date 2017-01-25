.. java:import:: java.util Map

.. java:import:: java.util HashMap

.. java:import:: java.math BigInteger

.. java:import:: java.io File

.. java:import:: java.io IOException

.. java:import:: java.net URL

.. java:import:: hk.hku.cecid.corvus.util DateUtil

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.commons.util UtilitiesException

.. java:import:: hk.hku.cecid.piazza.commons.module ComponentException

DataFactory
===========

.. java:package:: hk.hku.cecid.corvus.ws.data
   :noindex:

.. java:type:: public class DataFactory

   A \ ``DataFactory``\  imports data from the XML property tree to create different data object used for sending web service request.  Creation Date: 19/3/2007

   :author: Twinsen Tsang

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.PropertyTree`

Fields
------
XML_SEPARATOR
^^^^^^^^^^^^^

.. java:field:: public static final char XML_SEPARATOR
   :outertype: DataFactory

   The constants representing the XML Separator *

instance
^^^^^^^^

.. java:field:: public static final DataFactory instance
   :outertype: DataFactory

   Singleton.

Methods
-------
createAS2AdminDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public AS2AdminData createAS2AdminDataFromXML(PropertyTree t)
   :outertype: DataFactory

   Create an instance of \ ``AS2AdminData``\  from the XML property tree.

   :param t: The property tree to import the data.
   :return: A new instance of \ ``AS2AdminData``\  with data imported from the property tree.

createAS2ConfigDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public AS2ConfigData createAS2ConfigDataFromXML(PropertyTree t)
   :outertype: DataFactory

   Create an instance of \ ``AS2ConfigData``\  From the XML property tree.

   :param t: The property tree to import the data.
   :return: A new instance of \ ``AS2ConfigData``\  with data imported from the property tree.

createAS2MessageDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public AS2MessageData createAS2MessageDataFromXML(PropertyTree t)
   :outertype: DataFactory

   Create an instance of \ ``AS2MessageData``\  from the XML property tree.

   :param t: The property tree to import the data.
   :return: A new instance of \ ``AS2MessageData``\  with data imported from the property tree.

createAS2PartnershipFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public AS2PartnershipData createAS2PartnershipFromXML(PropertyTree t)
   :outertype: DataFactory

   Create an instance of \ ``AS2PartnershipData``\  From the XML property tree.

   :param t: The property tree to import the data.
   :return: A new instance of \ ``AS2PartnershipData``\  with data imported from the property tree.

createAS2PermitRedownloadDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public PermitRedownloadData createAS2PermitRedownloadDataFromXML(PropertyTree t)
   :outertype: DataFactory

createAS2StatusQueryDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public AS2StatusQueryData createAS2StatusQueryDataFromXML(PropertyTree t)
   :outertype: DataFactory

   Create an instance of \ ``AS2StatusQueryData``\  From the XML property tree.

   :param t: The property tree to import the data.
   :return: A new instance of \ ``AS2StatusQueryData``\  with data imported from the property tree.

createAs2MessageHistoryQueryDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public AS2MessageHistoryRequestData createAs2MessageHistoryQueryDataFromXML(PropertyTree t)
   :outertype: DataFactory

   Create an instance of \ ``AS2MessageHistoryRequestData``\  from the XML property tree.

   :param t: The property tree to import the data.
   :return: A new instance of \ ``AS2MessageHistoryRequestData``\  with data imported from the property tree.

createEBMSAdminDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public EBMSAdminData createEBMSAdminDataFromXML(PropertyTree t)
   :outertype: DataFactory

   Create an instance of \ ``EBMSAdminData``\  from the XML property tree.

   :param t: The property tree to import the data.
   :return: A new instance of \ ``EBMSAdminData``\  with data imported from the property tree.

createEBMSConfigDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public EBMSConfigData createEBMSConfigDataFromXML(PropertyTree t)
   :outertype: DataFactory

   Create an instance of \ ``EBMSConfigData``\  From the XML property tree.

   :param t: The property tree to import the data.
   :return: A new instance of \ ``EBMSConfigData``\  with data imported from the property tree.

createEBMSMessageDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public EBMSMessageData createEBMSMessageDataFromXML(PropertyTree t)
   :outertype: DataFactory

   Create an instance of \ ``EBMSMessageData``\  from the XML property tree.

   :param t: The property tree to import the data.
   :return: A new instance of \ ``EBMSMessageData``\  with data imported from the property tree.

createEBMSPartnershipFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public EBMSPartnershipData createEBMSPartnershipFromXML(PropertyTree t)
   :outertype: DataFactory

   Create an instance of \ ``EBMSPartnershipData``\  From the XML property tree.

   :param t: The property tree to import the data.
   :return: A new instance of \ ``EBMSPartnershipData``\  with data imported from the property tree.

createEBMSPermitRedownloadDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public PermitRedownloadData createEBMSPermitRedownloadDataFromXML(PropertyTree t)
   :outertype: DataFactory

createEBMSStatusQueryDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public EBMSStatusQueryData createEBMSStatusQueryDataFromXML(PropertyTree t)
   :outertype: DataFactory

   Create an instance of \ ``EBMSStatusQueryData``\  From the XML property tree.

   :param t: The property tree to import the data.
   :return: A new instance of \ ``EBMSStatusQueryData``\  with data imported from the property tree.

createEbmsMessageHistoryQueryDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public EBMSMessageHistoryRequestData createEbmsMessageHistoryQueryDataFromXML(PropertyTree t)
   :outertype: DataFactory

   Create an instance of \ ``EBMSMessageHistoryRequestData``\  from the XML property tree.

   :param t: The property tree to import the data.
   :return: A new instance of \ ``EBMSMessageHistoryRequestData``\  with data imported from the property tree.

createMessageRequestStatusDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static MessageStatusRequestData createMessageRequestStatusDataFromXML(PropertyTree t) throws UtilitiesException
   :outertype: DataFactory

   Create an instance of \ ``MessageStatusRequestData``\  From the XML property tree.

   :param t: The property tree to import the data.
   :throws UtilitiesException: When the data factory is unable to import the data from the property tree.
   :return: A new instance of \ ``MessageStatusRequestData``\  with data imported from the property tree.

createMessageStatusDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public static MessageStatusRequestData createMessageStatusDataFromXML(String filename) throws ComponentException
   :outertype: DataFactory

   Create an instance of \ ``MessageStatusRequestData``\  From a file written in XML format.

   :param filename: The file to load the message status request data.
   :throws ComponentException: When unable to load the file or invalid file format.
   :return: A new instance of \ ``MessageStatusRequestData``\  with data imported from the file with name \ ``filename``\

createSFRMStatusQueryDataFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public SFRMStatusQueryData createSFRMStatusQueryDataFromXML(PropertyTree t)
   :outertype: DataFactory

   Create an instance of \ ``SFRMStatusQueryData``\  From the XML property tree.

   :param t: The property tree to import the data.
   :return: A new instance of \ ``SFRMStatusQueryData``\  with data imported from the property tree.

getInstance
^^^^^^^^^^^

.. java:method:: public static DataFactory getInstance()
   :outertype: DataFactory

   Singleton instance.

storeAS2MessageDataToXML
^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void storeAS2MessageDataToXML(AS2MessageData d, URL path) throws IOException
   :outertype: DataFactory

   Store an instance of \ ``AS2Message to XML.``\

   :param d: The \ ``AS2MessageData to store.``\
   :param path: The URL specified the location for storing the data.
   :throws IOException: when storing the data fails.

storeAS2PartnershipFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void storeAS2PartnershipFromXML(AS2PartnershipData d, URL path) throws IOException
   :outertype: DataFactory

   Store the instance of \ ``AS2PartnershipData``\  to the XML specified at \ ``path.``\

   :param d: The \ ``AS2PartnershipData``\  you want to store.
   :param path: The URL specified the location for storing the data.
   :throws IOException: when storing the data fails.

storeEBMSMessageDataToXML
^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void storeEBMSMessageDataToXML(EBMSMessageData d, URL path) throws IOException
   :outertype: DataFactory

   Store an instance of \ ``EBMSMessage to XML.``\

   :param d: The \ ``AS2MessageData to store.``\
   :param path: The URL specified the location for storing the data.
   :throws IOException: when storing the data fails.

storeEBMSPartnershipFromXML
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void storeEBMSPartnershipFromXML(EBMSPartnershipData d, URL path) throws IOException
   :outertype: DataFactory

   Store the instance of \ ``EBMSPartnershipData``\  to the XML specified at \ ``path.``\

   :param d: The \ ``EBMSPartnershipData``\  you want to store.
   :param path: The URL specified the location for storing the data.
   :throws IOException: when storing the data fails.

