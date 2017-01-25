.. java:import:: hk.hku.cecid.piazza.commons.pagelet Pagelet

.. java:import:: hk.hku.cecid.piazza.commons.pagelet TemplateElement

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.xml.transform Source

BorderLayoutPageletAdaptor
==========================

.. java:package:: hk.hku.cecid.piazza.commons.pagelet.xslt
   :noindex:

.. java:type:: public abstract class BorderLayoutPageletAdaptor extends HttpXsltPageletAdaptor

   BorderLayoutPageletAdaptor is an HTTP-XSLT pagelet adaptor which supports a border layout of pagelets.

   A border layout can be divided into five regions:

   ..

   #. north
   #. east
   #. west
   #. south
   #. center

   Each region maps to a pagelet which has an ID same as the region's name.

   :author: Hugo Y. K. Lam

Methods
-------
getCenterSource
^^^^^^^^^^^^^^^

.. java:method:: protected Source getCenterSource(HttpServletRequest request)
   :outertype: BorderLayoutPageletAdaptor

   Gets the transformation source for the center region.

   :param request: the servlet request.
   :return: the transformation source or null by default.

getEastSource
^^^^^^^^^^^^^

.. java:method:: protected Source getEastSource(HttpServletRequest request)
   :outertype: BorderLayoutPageletAdaptor

   Gets the transformation source for the east region.

   :param request: the servlet request.
   :return: the transformation source or null by default.

getNorthSource
^^^^^^^^^^^^^^

.. java:method:: protected Source getNorthSource(HttpServletRequest request)
   :outertype: BorderLayoutPageletAdaptor

   Gets the transformation source for the north region.

   :param request: the servlet request.
   :return: the transformation source or null by default.

getPageletSource
^^^^^^^^^^^^^^^^

.. java:method:: protected Source getPageletSource(TemplateElement element, Pagelet pagelet, HttpServletRequest request) throws RequestListenerException
   :outertype: BorderLayoutPageletAdaptor

   Determines the border layout region that the given template element refers to and invokes the corresponding method for retrieving the transformation source.

   **See also:** :java:ref:`.getNorthSource(HttpServletRequest)`, :java:ref:`.getEastSource(HttpServletRequest)`, :java:ref:`.getWestSource(HttpServletRequest)`, :java:ref:`.getSouthSource(HttpServletRequest)`, :java:ref:`hk.hku.cecid.piazza.commons.pagelet.xslt.HttpXsltPageletAdaptor.getPageletSource(hk.hku.cecid.piazza.commons.pagelet.TemplateElement,hk.hku.cecid.piazza.commons.pagelet.Pagelet,javax.servlet.http.HttpServletRequest)`

getSouthSource
^^^^^^^^^^^^^^

.. java:method:: protected Source getSouthSource(HttpServletRequest request)
   :outertype: BorderLayoutPageletAdaptor

   Gets the transformation source for the south region.

   :param request: the servlet request.
   :return: the transformation source or null by default.

getWestSource
^^^^^^^^^^^^^

.. java:method:: protected Source getWestSource(HttpServletRequest request)
   :outertype: BorderLayoutPageletAdaptor

   Gets the transformation source for the west region.

   :param request: the servlet request.
   :return: the transformation source or null by default.

