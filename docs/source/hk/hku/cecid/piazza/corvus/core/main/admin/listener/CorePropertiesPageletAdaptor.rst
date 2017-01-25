.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.util PropertySheet

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: hk.hku.cecid.piazza.corvus.core.main.admin AdminMainProcessor

.. java:import:: hk.hku.cecid.piazza.corvus.core.main.admin.hc.module SchedulerTask

.. java:import:: hk.hku.cecid.piazza.corvus.core.main.admin.hc.util AdminProperties

.. java:import:: hk.hku.cecid.piazza.corvus.core.main.admin.hc.util AdminPropertiesException

.. java:import:: java.text SimpleDateFormat

.. java:import:: java.util Calendar

.. java:import:: java.util Enumeration

.. java:import:: java.util GregorianCalendar

.. java:import:: java.util.regex Pattern

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.transform Source

CorePropertiesPageletAdaptor
============================

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.admin.listener
   :noindex:

.. java:type:: public class CorePropertiesPageletAdaptor extends PropertiesPageletAdaptor

   CorePropertiesPageletAdaptor is a properties pagelet adaptor which provides an admin function of the core system properties.

   :author: Hugo Y. K. Lam

Methods
-------
addHouseCleaning
^^^^^^^^^^^^^^^^

.. java:method:: protected PropertyTree addHouseCleaning(HttpServletRequest request, PropertyTree dom)
   :outertype: CorePropertiesPageletAdaptor

   Add the housecleaning data to the XSL tranformation.

   :param request:
   :param dom:
   :return: PropertyTree

getCenterSource
^^^^^^^^^^^^^^^

.. java:method:: protected Source getCenterSource(HttpServletRequest request)
   :outertype: CorePropertiesPageletAdaptor

getProperties
^^^^^^^^^^^^^

.. java:method:: protected PropertySheet getProperties()
   :outertype: CorePropertiesPageletAdaptor

   Gets the core system properties.

   :return: the core system properties.

   **See also:** :java:ref:`hk.hku.cecid.piazza.corvus.core.main.admin.listener.PropertiesPageletAdaptor.getProperties()`

