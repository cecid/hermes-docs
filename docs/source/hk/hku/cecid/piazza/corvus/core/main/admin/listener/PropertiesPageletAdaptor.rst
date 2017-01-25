.. java:import:: hk.hku.cecid.piazza.commons.module PersistentComponent

.. java:import:: hk.hku.cecid.piazza.commons.util ArrayUtilities

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyMap

.. java:import:: hk.hku.cecid.piazza.commons.util PropertySheet

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.corvus.admin.listener AdminPageletAdaptor

.. java:import:: java.util Arrays

.. java:import:: java.util Enumeration

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.transform Source

PropertiesPageletAdaptor
========================

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.admin.listener
   :noindex:

.. java:type:: public class PropertiesPageletAdaptor extends AdminPageletAdaptor

   PropertiesPageletAdaptor is an admin pagelet adaptor which provides an admin function of the JVM properties. Subclasses can override the getProperties() method and return a compatible properties object for sharing the same admin function.

   :author: Hugo Y. K. Lam

Methods
-------
getCenterSource
^^^^^^^^^^^^^^^

.. java:method:: protected Source getCenterSource(HttpServletRequest request)
   :outertype: PropertiesPageletAdaptor

   Generates the transformation source of the properties.

   **See also:** :java:ref:`hk.hku.cecid.piazza.corvus.admin.listener.AdminPageletAdaptor.getCenterSource(javax.servlet.http.HttpServletRequest)`

getProperties
^^^^^^^^^^^^^

.. java:method:: protected PropertySheet getProperties()
   :outertype: PropertiesPageletAdaptor

   Gets the properties that this adaptor administrates.

   :return: the JVM properties.

getPropertiesForDisplayAndUpdate
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. java:method:: protected PropertyTree getPropertiesForDisplayAndUpdate(HttpServletRequest request, PropertyTree dom)
   :outertype: PropertiesPageletAdaptor

