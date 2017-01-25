.. java:import:: org.w3c.dom Element

WebServicesRequest
==================

.. java:package:: hk.hku.cecid.piazza.commons.soap
   :noindex:

.. java:type:: public class WebServicesRequest

   The WebServicesRequest class represents a Web Services request. It is independent of which access protocol it is using and contains the bodies of the request message.

   :author: Hugo Y. K. Lam

Constructors
------------
WebServicesRequest
^^^^^^^^^^^^^^^^^^

.. java:constructor::  WebServicesRequest()
   :outertype: WebServicesRequest

   Creates a new instance of WebServicesRequest.

WebServicesRequest
^^^^^^^^^^^^^^^^^^

.. java:constructor::  WebServicesRequest(Object source)
   :outertype: WebServicesRequest

   Creates a new instance of WebServicesRequest.

   :param source: the source which initiated this request.

Methods
-------
getBodies
^^^^^^^^^

.. java:method:: public Element[] getBodies()
   :outertype: WebServicesRequest

   Gets the body elements of the Web Services request message.

   :return: the bodies of the Web Services request message.

getSource
^^^^^^^^^

.. java:method:: public Object getSource()
   :outertype: WebServicesRequest

   Gets the source which initiated this request.

   :return: the source which initiated this request.

setBodies
^^^^^^^^^

.. java:method::  void setBodies(Element[] bs)
   :outertype: WebServicesRequest

   Sets the body elements of the Web Services request message.

   :param bs: the bodies of the Web Services request message.

setSource
^^^^^^^^^

.. java:method::  void setSource(Object source)
   :outertype: WebServicesRequest

   Sets the source which initiated this request.

   :param source: the source which initiated this request.

