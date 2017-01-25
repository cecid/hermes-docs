StatefulServletContextListener
==============================

.. java:package:: hk.hku.cecid.piazza.commons.servlet
   :noindex:

.. java:type:: public interface StatefulServletContextListener

   StatefulServletContextListener is a listener for listening the events from a stateful servlet context.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`StatefulServletContext`

Methods
-------
servletContextHalted
^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void servletContextHalted()
   :outertype: StatefulServletContextListener

   Invoked when the context it is listening has been halted.

servletContextResumed
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public void servletContextResumed()
   :outertype: StatefulServletContextListener

   Invoked when the context it is listening has been resumed.

