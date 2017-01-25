.. java:import:: java.util Properties

.. java:import:: hk.hku.cecid.piazza.commons.ejb.util RemoteCommandHandler

.. java:import:: hk.hku.cecid.piazza.commons.spa Extension

.. java:import:: hk.hku.cecid.piazza.commons.spa ExtensionPointIteratedHandler

.. java:import:: hk.hku.cecid.piazza.commons.spa PluginException

RemoteCommandRegistrar
======================

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.handler
   :noindex:

.. java:type:: public class RemoteCommandRegistrar extends ExtensionPointIteratedHandler

   RemoteCommandRegistrar handles the registration of any remote command with the central remote command handler.

   :author: Hugo Y. K. Lam

Methods
-------
processExtension
^^^^^^^^^^^^^^^^

.. java:method:: public void processExtension(Extension extension) throws PluginException
   :outertype: RemoteCommandRegistrar

   Adds a remote command to the central remote command handler.

   :param extension: the extension which represents the remote command.
   :throws PluginException: if unable to add the remote command.

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.spa.ExtensionPointHandler.processExtensions(java.util.Collection)`

