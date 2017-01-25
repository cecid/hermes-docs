.. java:import:: java.net URL

.. java:import:: java.util Properties

PersistentComponent
===================

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public abstract class PersistentComponent extends Component

   PersistentComponent represents a component that is persistent. Subclasses should override the loading(URL) and storing(URL) methods to provide their specific implementations.

   :author: Hugo Y. K. Lam

Constructors
------------
PersistentComponent
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public PersistentComponent()
   :outertype: PersistentComponent

   Creates a new instance of PersistentComponent.

PersistentComponent
^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public PersistentComponent(URL url) throws ComponentException
   :outertype: PersistentComponent

   Creates a new instance of PersistentComponent.

   :param url: the url representing this component.
   :throws Exception: when there is any error in loading the source.

Methods
-------
getURL
^^^^^^

.. java:method:: public URL getURL()
   :outertype: PersistentComponent

   Gets the url representing this component.

   :return: the url representing this component.

init
^^^^

.. java:method:: protected void init() throws Exception
   :outertype: PersistentComponent

   Initializes this component from the URL specified in the parameter 'config'. The load() method will then be invoked to handle the loading of this component.

   **See also:** :java:ref:`.load(URL)`, :java:ref:`Component.init()`, :java:ref:`Component.getParameters()`

load
^^^^

.. java:method:: public void load(URL url) throws ComponentException
   :outertype: PersistentComponent

   Loads this component from the specified url.

   :param url: the url representing this component.
   :throws Exception: when there is any error in loading.

   **See also:** :java:ref:`.loading(URL)`

load
^^^^

.. java:method:: public void load() throws ComponentException
   :outertype: PersistentComponent

   Loads this component from the URL representing it.

   :throws ComponentException: if unable to load this component from the URL.

   **See also:** :java:ref:`.load(URL)`

loading
^^^^^^^

.. java:method:: protected void loading(URL url) throws Exception
   :outertype: PersistentComponent

   Invoked by the load() method and should be overridden by subclasses to provide implementation.

   **See also:** :java:ref:`.load(URL)`

store
^^^^^

.. java:method:: public void store(URL url) throws ComponentException
   :outertype: PersistentComponent

   Stores this component to the specified url.

   :param url: the url representing this component.
   :throws Exception: when there is any error in storing.

   **See also:** :java:ref:`.storing(URL)`

store
^^^^^

.. java:method:: public void store() throws ComponentException
   :outertype: PersistentComponent

   Stores this component to the URL representing it.

   :throws ComponentException: if unable to store this component from the URL.

   **See also:** :java:ref:`.store(URL)`

storing
^^^^^^^

.. java:method:: protected void storing(URL url) throws Exception
   :outertype: PersistentComponent

   Invoked by the store() method and should be overridden by subclasses to provide implementation.

   **See also:** :java:ref:`.store(URL)`

