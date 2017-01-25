.. java:import:: java.io File

.. java:import:: java.util ArrayList

.. java:import:: java.util Collection

.. java:import:: java.util Collections

FileSystem
==========

.. java:package:: hk.hku.cecid.piazza.commons.io
   :noindex:

.. java:type:: public class FileSystem

   FileSystem encapsulates a root directory and provides accessors for querying and modifying this root.

   :author: Hugo Y. K. Lam

Fields
------
TYPE_ALL
^^^^^^^^

.. java:field:: public static int TYPE_ALL
   :outertype: FileSystem

   Type All.

TYPE_DIR
^^^^^^^^

.. java:field:: public static int TYPE_DIR
   :outertype: FileSystem

   Type Directory.

TYPE_FILE
^^^^^^^^^

.. java:field:: public static int TYPE_FILE
   :outertype: FileSystem

   Type File.

Constructors
------------
FileSystem
^^^^^^^^^^

.. java:constructor:: public FileSystem(File root)
   :outertype: FileSystem

   Creates a new instance of FileSystem.

   :param root: the root of this file system. If root is null, it will be set to the current user directory.

Methods
-------
exists
^^^^^^

.. java:method:: public boolean exists()
   :outertype: FileSystem

   Checks if the root of this file system exists.

   :return: true if the root of this file system exists.

getDirectories
^^^^^^^^^^^^^^

.. java:method:: public Collection getDirectories(boolean isRecursive)
   :outertype: FileSystem

   Retrieves a collection of directory-only File objects from the root of this file system.

   :param isRecursive: true if the search should be recursive.
   :return: a collection of File objects resulted from the search.

getDirectories
^^^^^^^^^^^^^^

.. java:method:: public Collection getDirectories(boolean isRecursive, String pattern)
   :outertype: FileSystem

   Retrieves a collection of directory-only File objects from the root of this file system.

   :param isRecursive: true if the search should be recursive.
   :param pattern: the filename's pattern for filtering the result. null if no filtering should be applied.
   :return: a collection of File objects resulted from the search.

getFiles
^^^^^^^^

.. java:method:: public Collection getFiles(boolean isRecursive)
   :outertype: FileSystem

   Retrieves a collection of file-only File objects from the root of this file system.

   :param isRecursive: true if the search should be recursive.
   :return: a collection of File objects resulted from the search.

getFiles
^^^^^^^^

.. java:method:: public Collection getFiles(boolean isRecursive, String pattern)
   :outertype: FileSystem

   Retrieves a collection of file-only File objects from the root of this file system.

   :param isRecursive: true if the search should be recursive.
   :param pattern: the filename's pattern for filtering the result. null if no filtering should be applied.
   :return: a collection of File objects resulted from the search.

getFiles
^^^^^^^^

.. java:method:: public Collection getFiles(boolean isRecursive, int type, String pattern)
   :outertype: FileSystem

   Retrieves a collection of File objects from the root of this file system.

   :param isRecursive: true if the search should be recursive.
   :param type: the file type to be searched.
   :param pattern: the filename's pattern for filtering the result. null if no filtering should be applied.
   :return: a collection of File objects resulted from the search.

getFiles
^^^^^^^^

.. java:method:: public Collection getFiles(Collection c, boolean isRecursive, int type, String pattern)
   :outertype: FileSystem

   Retrieves a collection of File objects from the root of this file system.

   :param c: the collection into which the result will be stored.
   :param isRecursive: true if the search should be recursive.
   :param type: the file type to be searched.
   :param pattern: the filename's pattern for filtering the result. null if no filtering should be applied.
   :return: a collection of File objects resulted from the search.

getRoot
^^^^^^^

.. java:method:: public File getRoot()
   :outertype: FileSystem

   Gets the root of this file system.

   :return: the root of this file system.

purge
^^^^^

.. java:method:: public void purge()
   :outertype: FileSystem

   Removes the files, including the directories, under the root directory of this file system recursively. If there are files that cannot be removed immediately, the files will be deleted on exit. This method will also remove the root directory itself.

purge
^^^^^

.. java:method:: public void purge(boolean isSelfRemoved)
   :outertype: FileSystem

   Removes the files, including the directories, under the root directory of this file system recursively. If there are files that cannot be removed immediately, the files will be deleted on exit.

   :param isSelfRemoved: true if the root directory itself should be removed.

remove
^^^^^^

.. java:method:: public boolean remove()
   :outertype: FileSystem

   Removes the files, including the directories, under the root directory of this file system recursively. The operation ceases when it encounters any error in removing any file. If the operation is successful, the root directory itself will be removed as well.

   :return: true if and only if all the files are removed successfully.

remove
^^^^^^

.. java:method:: public boolean remove(boolean isSelfRemoved)
   :outertype: FileSystem

   Removes the files, including the directories, under the root of this file system recursively. The operation ceases when it encounters any error in removing any file.

   :param isSelfRemoved: true if the root directory itself should be removed.
   :return: true if and only if all the files are removed successfully.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: FileSystem

   Returns the absolute path of the root of this file system.

   :return: the absolute path of the root of this file system.

   **See also:** :java:ref:`java.lang.Object.toString()`

