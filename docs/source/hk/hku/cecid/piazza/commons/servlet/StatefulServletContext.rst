.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.util Instance

.. java:import:: java.util Collection

.. java:import:: java.util Iterator

.. java:import:: java.util Vector

.. java:import:: javax.servlet UnavailableException

StatefulServletContext
======================

.. java:package:: hk.hku.cecid.piazza.commons.servlet
   :noindex:

.. java:type:: public class StatefulServletContext

   A StatefulServletContext represents a context of a stateful servlet. A stateful servlet has two states, a halted state and a running state.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`StatefulServletContextListener`

Constructors
------------
StatefulServletContext
^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public StatefulServletContext()
   :outertype: StatefulServletContext

   Creates a new instance of StatefulServletContext.

Methods
-------
acquire
^^^^^^^

.. java:method:: public synchronized void acquire() throws UnavailableException
   :outertype: StatefulServletContext

   Acquires a permission from this context. Any servlet which employs this stateful context must call this method before processing any requests.

   :throws UnavailableException: if the context is currently halted.

addContextListener
^^^^^^^^^^^^^^^^^^

.. java:method:: public boolean addContextListener(Object contextListener)
   :outertype: StatefulServletContext

   Adds a context listener for receiving events from this context.

   :param contextListener: the stateful servlet context listener.
   :return: true if the operation is successful, false otherwise.

getContextListeners
^^^^^^^^^^^^^^^^^^^

.. java:method:: public Collection getContextListeners()
   :outertype: StatefulServletContext

   Gets all the stateful servlet context listeners in this context.

   :return: all the stateful servlet context listeners in this context.

getCurrentThreadCount
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public int getCurrentThreadCount()
   :outertype: StatefulServletContext

   Gets the current count of threads running under this context.

   :return: the current count of threads running under this context.

getRequestEncoding
^^^^^^^^^^^^^^^^^^

.. java:method:: public String getRequestEncoding()
   :outertype: StatefulServletContext

   Gets the request encoding that the servlet should use.

   :return: the request encoding.

getResponseEncoding
^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getResponseEncoding()
   :outertype: StatefulServletContext

   Gets the response encoding that the servlet should use.

   :return: the response encoding.

halt
^^^^

.. java:method:: public synchronized boolean halt()
   :outertype: StatefulServletContext

   Halts this context. The calling thread will be blocked until a lock on the context has been acquired and no more threads are running under this context. Nothing will be done if the servlet is already halted.

   :return: true if and only if this context is not halted or being halted.

isHalted
^^^^^^^^

.. java:method:: public boolean isHalted()
   :outertype: StatefulServletContext

   Checks if the context is currently halted.

   :return: true if the servlet is currently halted.

isHalting
^^^^^^^^^

.. java:method:: public boolean isHalting()
   :outertype: StatefulServletContext

   Checks if the context is currently being halted.

   :return: true if the servlet is currently being halted.

release
^^^^^^^

.. java:method:: public synchronized void release()
   :outertype: StatefulServletContext

   Releases a permission to this context. Any servlet which employs this stateful context must call this method after processing any requests.

resume
^^^^^^

.. java:method:: public synchronized boolean resume()
   :outertype: StatefulServletContext

   Resumes this context. The calling thread will be blocked until a lock on the context has been acquired. Nothing will be done if the servlet is not halted.

   :return: true if and only if this context is halted and not being halted.

setRequestEncoding
^^^^^^^^^^^^^^^^^^

.. java:method:: public void setRequestEncoding(String requestEncoding)
   :outertype: StatefulServletContext

   Sets the request encoding that the servlet should use.

   :param requestEncoding: the request encoding.

setResponseEncoding
^^^^^^^^^^^^^^^^^^^

.. java:method:: public void setResponseEncoding(String responseEncoding)
   :outertype: StatefulServletContext

   Sets the response encoding that the servlet should use.

   :param responseEncoding: the response encoding.

