.. java:import:: hk.hku.cecid.piazza.commons.module ComponentException

.. java:import:: hk.hku.cecid.piazza.commons.module PersistentComponent

.. java:import:: java.net URL

MessagesTree
============

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public class MessagesTree extends PersistentComponent implements Messages

   MessagesTree is an implementation of a Messenger. It represents a messenger with a tree structure and is actually backed by a PropertiesTree object.

   :author: Hugo Y. K. Lam

Constructors
------------
MessagesTree
^^^^^^^^^^^^

.. java:constructor:: public MessagesTree()
   :outertype: MessagesTree

   Creates a new instance of MessagesTree.

MessagesTree
^^^^^^^^^^^^

.. java:constructor:: public MessagesTree(URL url) throws ComponentException
   :outertype: MessagesTree

   Creates a new instance of MessagesTree.

   :param url: the url of the messenger properties source.
   :throws ComponentException: if the properties could not be loaded from the specified url.

Methods
-------
getDefaultLocale
^^^^^^^^^^^^^^^^

.. java:method:: public String getDefaultLocale()
   :outertype: MessagesTree

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Messages.getDefaultLocale()`

getDefaultMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public String getDefaultMessage()
   :outertype: MessagesTree

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Messages.getDefaultMessage()`

getErrorMessage
^^^^^^^^^^^^^^^

.. java:method:: public String getErrorMessage(String name)
   :outertype: MessagesTree

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Messages.getErrorMessage(java.lang.String)`

getErrorMessage
^^^^^^^^^^^^^^^

.. java:method:: public String getErrorMessage(String name, String def)
   :outertype: MessagesTree

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Messages.getErrorMessage(java.lang.String,java.lang.String)`

getMessage
^^^^^^^^^^

.. java:method:: public String getMessage(String name)
   :outertype: MessagesTree

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Messages.getMessage(java.lang.String)`

getMessage
^^^^^^^^^^

.. java:method:: public String getMessage(String name, String def)
   :outertype: MessagesTree

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Messages.getMessage(java.lang.String,java.lang.String)`

getMessage
^^^^^^^^^^

.. java:method:: public String getMessage(String name, String def, String type)
   :outertype: MessagesTree

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Messages.getMessage(java.lang.String,java.lang.String,java.lang.String)`

getMessage
^^^^^^^^^^

.. java:method:: public String getMessage(String name, String def, String type, String locale)
   :outertype: MessagesTree

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Messages.getMessage(java.lang.String,java.lang.String,java.lang.String,java.lang.String)`

getWarningMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public String getWarningMessage(String name)
   :outertype: MessagesTree

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Messages.getWarningMessage(java.lang.String)`

getWarningMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public String getWarningMessage(String name, String def)
   :outertype: MessagesTree

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Messages.getWarningMessage(java.lang.String,java.lang.String)`

loading
^^^^^^^

.. java:method:: protected void loading(URL url) throws Exception
   :outertype: MessagesTree

   Loads the messenger properties from the specified url location.

   :param url: the url of the messenger properties source.
   :throws Exception: if the operation is unsuccessful.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.PersistentComponent.loading(java.net.URL)`

setDefaultLocale
^^^^^^^^^^^^^^^^

.. java:method:: public void setDefaultLocale(String locale)
   :outertype: MessagesTree

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Messages.setDefaultLocale(java.lang.String)`

setDefaultMessage
^^^^^^^^^^^^^^^^^

.. java:method:: public void setDefaultMessage(String string)
   :outertype: MessagesTree

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.util.Messages.setDefaultMessage(java.lang.String)`

