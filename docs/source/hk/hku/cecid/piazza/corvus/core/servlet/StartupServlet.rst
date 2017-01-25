.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.corvus.core Kernel

.. java:import:: javax.servlet ServletConfig

.. java:import:: javax.servlet ServletException

.. java:import:: javax.servlet.http HttpServlet

StartupServlet
==============

.. java:package:: hk.hku.cecid.piazza.corvus.core.servlet
   :noindex:

.. java:type:: public class StartupServlet extends HttpServlet

   StartupServlet is the main startup servlet of Corvus. It will initialize the Corvus kernel once the servlet is being initialized.

   :author: Hugo Y. K. Lam

Methods
-------
destroy
^^^^^^^

.. java:method:: public void destroy()
   :outertype: StartupServlet

   Invoked when the servlet is out of service.

   **See also:** :java:ref:`javax.servlet.Servlet.destroy()`

init
^^^^

.. java:method:: public void init(ServletConfig config) throws ServletException
   :outertype: StartupServlet

   Initializes the servlet.

   **See also:** :java:ref:`javax.servlet.Servlet.init(javax.servlet.ServletConfig)`

