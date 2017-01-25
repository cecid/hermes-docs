.. java:import:: hk.hku.cecid.piazza.commons.dao DAOFactory

.. java:import:: hk.hku.cecid.piazza.commons.util Logger

.. java:import:: hk.hku.cecid.piazza.commons.util PropertySheet

SystemComponent
===============

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public abstract class SystemComponent extends Component

Methods
-------
getComponent
^^^^^^^^^^^^

.. java:method:: public Component getComponent(String id)
   :outertype: SystemComponent

getDAOFactory
^^^^^^^^^^^^^

.. java:method:: public DAOFactory getDAOFactory()
   :outertype: SystemComponent

getLogger
^^^^^^^^^

.. java:method:: public Logger getLogger()
   :outertype: SystemComponent

getProperties
^^^^^^^^^^^^^

.. java:method:: public PropertySheet getProperties()
   :outertype: SystemComponent

getSystemModule
^^^^^^^^^^^^^^^

.. java:method:: public SystemModule getSystemModule()
   :outertype: SystemComponent

