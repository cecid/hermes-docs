RestRequest
===========

.. java:package:: hk.hku.cecid.piazza.commons.rest
   :noindex:

.. java:type:: public class RestRequest

   The RestRequest class represents a Restful service request. It is independent of which access protocol it is using and contains the bodies of the request message.

   :author: Patrick Yee

Constructors
------------
RestRequest
^^^^^^^^^^^

.. java:constructor:: public RestRequest()
   :outertype: RestRequest

   Creates a new instance of RestRequest.

RestRequest
^^^^^^^^^^^

.. java:constructor:: public RestRequest(Object source)
   :outertype: RestRequest

   Creates a new instance of RestRequest.

   :param source: the source which initiated this request.

Methods
-------
getSource
^^^^^^^^^

.. java:method:: public Object getSource()
   :outertype: RestRequest

   Gets the source which initiated this request.

   :return: the source which initiated this request.

setSource
^^^^^^^^^

.. java:method:: public void setSource(Object source)
   :outertype: RestRequest

   Sets the source which initiated this request.

   :param source: the source which initiated this request.

