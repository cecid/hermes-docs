.. java:import:: hk.hku.cecid.piazza.commons.util StringUtilities

.. java:import:: java.util Properties

LimitedActiveTaskList
=====================

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public abstract class LimitedActiveTaskList extends ActiveTaskList

   A limited active task list is a active task list that can be set it's limit in the parameters list. But it has not effect on how big the active task list can return (no bound, only a limit value). Creation Date: 31/10/2006.

   :author: Twinsen

Methods
-------
getMaxTasksPerList
^^^^^^^^^^^^^^^^^^

.. java:method:: public int getMaxTasksPerList()
   :outertype: LimitedActiveTaskList

   :return: the maxTasksPerList

init
^^^^

.. java:method:: protected void init() throws Exception
   :outertype: LimitedActiveTaskList

   Component Initialization.

   :throws Exception:

