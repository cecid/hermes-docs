.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.lang.ref SoftReference

.. java:import:: java.net URL

Pagelet
=======

.. java:package:: hk.hku.cecid.piazza.commons.pagelet
   :noindex:

.. java:type:: public class Pagelet

   A Pagelet contains a URL representing a page or a fragment of a page. By default, it caches the content of the pagelet softly. Therefore, each invocation of openStream() may or may not cause an actual access to the pagelet URL, depending on the memory status and whether caching is enabled.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`PageletStore`

Constructors
------------
Pagelet
^^^^^^^

.. java:constructor:: public Pagelet(String id, URL pagelet)
   :outertype: Pagelet

   Creates a new instance of Pagelet.

   :param id: the pagelet ID.
   :param pagelet: the pagelet URL.

Methods
-------
getId
^^^^^

.. java:method:: public String getId()
   :outertype: Pagelet

   Gets the pagelet ID.

   :return: the pagelet ID.

getURL
^^^^^^

.. java:method:: public URL getURL()
   :outertype: Pagelet

   Gets the URL of the pagelet.

   :return: the URL of the pagelet.

isCacheEnabled
^^^^^^^^^^^^^^

.. java:method:: public boolean isCacheEnabled()
   :outertype: Pagelet

   Checks if caching is enabled.

   :return: true if caching is enabled.

openStream
^^^^^^^^^^

.. java:method:: public InputStream openStream() throws IOException
   :outertype: Pagelet

   Opens an input stream for reading the content of the pagelet.

   :throws IOException: if unable to create a new input stream.
   :return: the input stream of the pagelet.

setCacheEnabled
^^^^^^^^^^^^^^^

.. java:method:: public void setCacheEnabled(boolean isCacheEnabled)
   :outertype: Pagelet

   Sets whether caching should be enabled.

   :param isCacheEnabled: true if caching should be enabled.

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: Pagelet

   Returns a string representation of this pagelet.

   :return: a string representation of this pagelet.

   **See also:** :java:ref:`java.lang.Object.toString()`

