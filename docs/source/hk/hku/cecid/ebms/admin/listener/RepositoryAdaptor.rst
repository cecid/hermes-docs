.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao RepositoryDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao RepositoryDVO

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: hk.hku.cecid.piazza.commons.servlet.http HttpRequestAdaptor

.. java:import:: java.io ByteArrayInputStream

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.servlet.http HttpServletResponse

RepositoryAdaptor
=================

.. java:package:: hk.hku.cecid.ebms.admin.listener
   :noindex:

.. java:type:: public class RepositoryAdaptor extends HttpRequestAdaptor

   :author: Donahue Sze

Methods
-------
processRequest
^^^^^^^^^^^^^^

.. java:method:: public String processRequest(HttpServletRequest request, HttpServletResponse response) throws RequestListenerException
   :outertype: RepositoryAdaptor

