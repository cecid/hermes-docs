.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io ByteArrayOutputStream

.. java:import:: java.io File

.. java:import:: java.io FileInputStream

.. java:import:: java.io InputStream

.. java:import:: java.util.zip ZipEntry

.. java:import:: java.util.zip ZipInputStream

PluginFile
==========

.. java:package:: hk.hku.cecid.piazza.commons.spa
   :noindex:

.. java:type:: public class PluginFile

   A PluginFile represents an archive file containing all the plugin required files, including the plugin descriptor.

   :author: Hugo Y. K. Lam

Fields
------
DEFAULT_FILE_EXT
^^^^^^^^^^^^^^^^

.. java:field:: public static final String DEFAULT_FILE_EXT
   :outertype: PluginFile

   The default file extension (spa) of the plugin file.

Constructors
------------
PluginFile
^^^^^^^^^^

.. java:constructor:: public PluginFile(File pluginFile) throws PluginException
   :outertype: PluginFile

   Create a new instance of PluginFile.

   :param pluginFile: the plugin file.
   :throws PluginException: if unable to create the plugin file instance.

PluginFile
^^^^^^^^^^

.. java:constructor:: public PluginFile(File pluginFile, String descriptorName) throws PluginException
   :outertype: PluginFile

   Create a new instance of PluginFile.

   :param pluginFile: the plugin file.
   :param descriptorName: the plugin descriptor name.
   :throws PluginException: if unable to create the plugin file instance.

PluginFile
^^^^^^^^^^

.. java:constructor:: public PluginFile(InputStream pluginStream) throws PluginException
   :outertype: PluginFile

   Create a new instance of PluginFile.

   :param pluginStream: the plugin stream.
   :throws PluginException: if unable to create the plugin file instance.

PluginFile
^^^^^^^^^^

.. java:constructor:: public PluginFile(InputStream pluginStream, String descriptorName) throws PluginException
   :outertype: PluginFile

   Create a new instance of PluginFile.

   :param pluginStream: the plugin stream.
   :param descriptorName: the plugin descriptor name.
   :throws PluginException: if unable to create the plugin file instance.

Methods
-------
getDescriptor
^^^^^^^^^^^^^

.. java:method:: public PluginDescriptor getDescriptor()
   :outertype: PluginFile

   Gets the plugin descriptor.

   :return: the plugin descriptor.

getPluginContent
^^^^^^^^^^^^^^^^

.. java:method:: public byte[] getPluginContent()
   :outertype: PluginFile

   Gets the plugin content.

   :return: the plugin content.

