.. java:import:: hk.hku.cecid.piazza.commons.module SystemComponent

OSManager
=========

.. java:package:: hk.hku.cecid.piazza.commons.os
   :noindex:

.. java:type:: public class OSManager extends SystemComponent

   The OSManager acts as a bridge between OSCommander and Piazza Commons framework. It provides convenient way for components to execute system command.  Creation Date: 04/05/2009

   :author: Philip Wong

Fields
------
osCommander
^^^^^^^^^^^

.. java:field:: protected OSCommander osCommander
   :outertype: OSManager

Methods
-------
getCommander
^^^^^^^^^^^^

.. java:method:: public OSCommander getCommander()
   :outertype: OSManager

getName
^^^^^^^

.. java:method:: public String getName()
   :outertype: OSManager

init
^^^^

.. java:method:: public void init() throws Exception
   :outertype: OSManager

