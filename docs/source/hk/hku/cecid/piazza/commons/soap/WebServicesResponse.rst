.. java:import:: org.w3c.dom Element

WebServicesResponse
===================

.. java:package:: hk.hku.cecid.piazza.commons.soap
   :noindex:

.. java:type:: public class WebServicesResponse

   The WebServicesResponse class represents a Web Services response. It is independent of which access protocol it is using and contains the bodies of the response message.

   :author: Hugo Y. K. Lam

Constructors
------------
WebServicesResponse
^^^^^^^^^^^^^^^^^^^

.. java:constructor::  WebServicesResponse()
   :outertype: WebServicesResponse

   Creates a new instance of WebServicesResponse.

WebServicesResponse
^^^^^^^^^^^^^^^^^^^

.. java:constructor::  WebServicesResponse(Object target)
   :outertype: WebServicesResponse

   Creates a new instance of WebServicesResponse.

   :param target: the target that this response should be committed to.

Methods
-------
getBodies
^^^^^^^^^

.. java:method:: public Element[] getBodies()
   :outertype: WebServicesResponse

   Gets the body elements of the Web Services response message.

   :return: the bodies of the Web Services response message.

getTarget
^^^^^^^^^

.. java:method:: public Object getTarget()
   :outertype: WebServicesResponse

   Gets the target that this response should be committed to.

   :return: the target that this response should be committed to.

setBodies
^^^^^^^^^

.. java:method:: public void setBodies(Element[] bs)
   :outertype: WebServicesResponse

   Sets the body elements of the Web Services response message.

   :param bs: the bodies of the Web Services response message.

setTarget
^^^^^^^^^

.. java:method::  void setTarget(Object target)
   :outertype: WebServicesResponse

   Sets the target that this response should be committed to.

   :param target: the target that this response should be committed to.

