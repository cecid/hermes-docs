.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.module Module

.. java:import:: hk.hku.cecid.piazza.commons.module ModuleGroup

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.corvus.admin.listener AdminPageletAdaptor

.. java:import:: java.util Collection

.. java:import:: java.util Iterator

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.transform Source

ModuleInfoPageletAdaptor
========================

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.admin.listener
   :noindex:

.. java:type:: public class ModuleInfoPageletAdaptor extends AdminPageletAdaptor

   ModuleInfoPageletAdaptor is an admin pagelet adaptor which provides an admin function of the system modules.

   :author: Hugo Y. K. Lam

Methods
-------
getCenterSource
^^^^^^^^^^^^^^^

.. java:method:: protected Source getCenterSource(HttpServletRequest request)
   :outertype: ModuleInfoPageletAdaptor

   Generates the transformation source of the system modules.

   **See also:** :java:ref:`hk.hku.cecid.piazza.corvus.admin.listener.AdminPageletAdaptor.getCenterSource(javax.servlet.http.HttpServletRequest)`

