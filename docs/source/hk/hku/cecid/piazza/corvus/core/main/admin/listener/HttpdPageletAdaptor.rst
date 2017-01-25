.. java:import:: hk.hku.cecid.piazza.commons.servlet.http HttpDispatcherContext

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

.. java:import:: hk.hku.cecid.piazza.corvus.admin.listener AdminPageletAdaptor

.. java:import:: java.util Enumeration

.. java:import:: java.util Iterator

.. java:import:: java.util Properties

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.transform Source

HttpdPageletAdaptor
===================

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.admin.listener
   :noindex:

.. java:type:: public class HttpdPageletAdaptor extends AdminPageletAdaptor

   HttpdPageletAdaptor is an admin pagelet adaptor which provides an admin function of the default HTTP dispatcher.

   :author: Hugo Y. K. Lam

Methods
-------
getCenterSource
^^^^^^^^^^^^^^^

.. java:method:: protected Source getCenterSource(HttpServletRequest request)
   :outertype: HttpdPageletAdaptor

   Generates the transformation source of the default HTTP dispatcher.

   **See also:** :java:ref:`hk.hku.cecid.piazza.corvus.admin.listener.AdminPageletAdaptor.getCenterSource(javax.servlet.http.HttpServletRequest)`

