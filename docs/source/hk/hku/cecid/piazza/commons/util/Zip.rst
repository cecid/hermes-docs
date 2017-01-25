.. java:import:: hk.hku.cecid.piazza.commons.io FileSystem

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: java.io File

.. java:import:: java.io FileInputStream

.. java:import:: java.io FileOutputStream

.. java:import:: java.io InputStream

.. java:import:: java.util ArrayList

.. java:import:: java.util Enumeration

.. java:import:: java.util Iterator

.. java:import:: java.util.zip ZipEntry

.. java:import:: java.util.zip ZipFile

.. java:import:: java.util.zip ZipOutputStream

Zip
===

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public final class Zip

   Zip is a tool which can compress a set of files contained in a directory into a zip file. Likewise, it can also extract a set of files compressed in a zip file to a directory.

   :author: Hugo Y. K. Lam

Methods
-------
compress
^^^^^^^^

.. java:method:: public static void compress(File toFile, File dir) throws UtilitiesException
   :outertype: Zip

   Compresses a set of files contained in a directory into a zip file.

   :param toFile: the zip file.
   :param dir: the directory which contains the files to be compressed.
   :throws UtilitiesException: if there is any error in the compression.

extract
^^^^^^^

.. java:method:: public static void extract(File fromFile, File dir) throws UtilitiesException
   :outertype: Zip

   Extracts a set of files compressed in a zip file to a directory.

   :param fromFile: the zip file.
   :param dir: the directory to which the files to be extracted. Current user directory will be chosen if it is null.
   :throws UtilitiesException: if there is any error in the extraction.

