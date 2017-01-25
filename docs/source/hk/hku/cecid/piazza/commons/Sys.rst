.. java:import:: hk.hku.cecid.piazza.commons.module ModuleException

.. java:import:: hk.hku.cecid.piazza.commons.module ModuleGroup

.. java:import:: hk.hku.cecid.piazza.commons.module SystemModule

.. java:import:: java.io InputStream

.. java:import:: java.net URL

Sys
===

.. java:package:: hk.hku.cecid.piazza.commons
   :noindex:

.. java:type:: public final class Sys

   Sys represents a system in an application and contains one system module, which is described by a module descriptor. The descriptor location and the system module class will be looked up from a module group descriptor which is located by the following logic:

   ..

   #. Search for the Sys properties (sys.properties) in the classpaths of the classloader used to load the Sys class.
   #. If the properties was not found, use the Java System Properties.
   #. Look for a property 'sys.module.group' for the system module group descriptor location.
   #. If the property is not found, the location will be default to 'hk/hku/cecid/piazza/commons/conf/sys.module-group.xml'

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`hk.hku.cecid.piazza.commons.module.Module`, :java:ref:`hk.hku.cecid.piazza.commons.module.ModuleGroup`

Fields
------
main
^^^^

.. java:field:: public static final SystemModule main
   :outertype: Sys

   The main system module.

Methods
-------
getModuleGroup
^^^^^^^^^^^^^^

.. java:method:: public static ModuleGroup getModuleGroup()
   :outertype: Sys

   Gets the system module group.

   :return: the system module group.

