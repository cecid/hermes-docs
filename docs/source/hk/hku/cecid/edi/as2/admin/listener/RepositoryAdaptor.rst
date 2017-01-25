.. java:import:: hk.hku.cecid.edi.as2 AS2PlusProcessor

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDAO

.. java:import:: hk.hku.cecid.edi.as2.dao MessageDVO

.. java:import:: hk.hku.cecid.edi.as2.dao RepositoryDAO

.. java:import:: hk.hku.cecid.edi.as2.dao RepositoryDVO

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: hk.hku.cecid.piazza.commons.servlet RequestListenerException

.. java:import:: hk.hku.cecid.piazza.commons.servlet.http HttpRequestAdaptor

.. java:import:: java.io ByteArrayInputStream

.. java:import:: java.util Iterator

.. java:import:: javax.servlet.http HttpServletRequest

.. java:import:: javax.servlet.http HttpServletResponse

RepositoryAdaptor
=================

.. java:package:: hk.hku.cecid.edi.as2.admin.listener
   :noindex:

.. java:type:: public class RepositoryAdaptor extends HttpRequestAdaptor

   :author: Donahue Sze

Methods
-------
processRequest
^^^^^^^^^^^^^^

.. java:method:: public String processRequest(HttpServletRequest request, HttpServletResponse response) throws RequestListenerException
   :outertype: RepositoryAdaptor

