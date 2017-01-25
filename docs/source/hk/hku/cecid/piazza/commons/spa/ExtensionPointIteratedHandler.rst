.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: java.util Collection

.. java:import:: java.util Iterator

ExtensionPointIteratedHandler
=============================

.. java:package:: hk.hku.cecid.piazza.commons.spa
   :noindex:

.. java:type:: public abstract class ExtensionPointIteratedHandler implements ExtensionPointHandler

   An ExtensionPointIteratedHandler handles all the extensions of the extension point it represents one by one.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`ExtensionPoint`

Methods
-------
isFaultTolerated
^^^^^^^^^^^^^^^^

.. java:method:: protected boolean isFaultTolerated()
   :outertype: ExtensionPointIteratedHandler

   Checks if fault tolerance is enabled.

   :return: true if fault tolerance is enabled.

processExtension
^^^^^^^^^^^^^^^^

.. java:method:: public abstract void processExtension(Extension extension) throws PluginException
   :outertype: ExtensionPointIteratedHandler

   Invoked by processExtensions() for processing each extension.

   :param extension: the extension to be processed.

processExtensions
^^^^^^^^^^^^^^^^^

.. java:method:: public void processExtensions(Collection extensions) throws PluginException
   :outertype: ExtensionPointIteratedHandler

   Processes the extensions one by one. If fault tolerance is enabled, no exception will be thrown and processes will be carried on even if there are any exceptions.

   :param extensions: the extensions of the extension point it represents.
   :throws PluginException: if failed in processing the extensions.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.ExtensionPointHandler.processExtensions(java.util.Collection)`

