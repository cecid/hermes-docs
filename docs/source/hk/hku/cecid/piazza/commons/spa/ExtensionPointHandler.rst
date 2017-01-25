.. java:import:: java.util Collection

ExtensionPointHandler
=====================

.. java:package:: hk.hku.cecid.piazza.commons.spa
   :noindex:

.. java:type:: public interface ExtensionPointHandler

   An ExtensionPointHandler handles all the extensions of the extension point it represents.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`ExtensionPoint`

Methods
-------
processExtensions
^^^^^^^^^^^^^^^^^

.. java:method:: public void processExtensions(Collection extensions) throws PluginException
   :outertype: ExtensionPointHandler

   Processes the extensions of the extension point it represents. It is invoked when the plugin registry is being activated.

   :param extensions: the extensions of the extension point it represents.
   :throws PluginException: if failed in the processing extensions.

