HttpRequestFilter
=================

.. java:package:: hk.hku.cecid.piazza.commons.servlet.http
   :noindex:

.. java:type:: public interface HttpRequestFilter

   HttpRequestFilter

   :author: Hugo Y. K. Lam

Methods
-------
requestAccepted
^^^^^^^^^^^^^^^

.. java:method:: public boolean requestAccepted(HttpRequestEvent event)
   :outertype: HttpRequestFilter

   Invoked when the an HTTP request is accepted.

   :param event: the HTTP request event.

requestProcessed
^^^^^^^^^^^^^^^^

.. java:method:: public void requestProcessed(HttpRequestEvent event)
   :outertype: HttpRequestFilter

   Invoked when the an HTTP request has been processed.

   :param event: the HTTP request event.

