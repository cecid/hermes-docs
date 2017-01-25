.. java:import:: java.util ArrayList

.. java:import:: java.util Collection

.. java:import:: java.util Iterator

.. java:import:: java.util List

EventModule
===========

.. java:package:: hk.hku.cecid.piazza.commons.module
   :noindex:

.. java:type:: public class EventModule<TEventListener> extends Module

Fields
------
MODULE_ID
^^^^^^^^^

.. java:field:: public static final String MODULE_ID
   :outertype: EventModule

eventListenerList
^^^^^^^^^^^^^^^^^

.. java:field:: protected List<TEventListener> eventListenerList
   :outertype: EventModule

Constructors
------------
EventModule
^^^^^^^^^^^

.. java:constructor:: public EventModule(String descriptorLocation, ClassLoader loader)
   :outertype: EventModule

EventModule
^^^^^^^^^^^

.. java:constructor:: public EventModule(String descriptorLocation, boolean shouldInitialize)
   :outertype: EventModule

EventModule
^^^^^^^^^^^

.. java:constructor:: public EventModule(String descriptorLocation, ClassLoader loader, boolean shouldInitialize)
   :outertype: EventModule

EventModule
^^^^^^^^^^^

.. java:constructor:: public EventModule(String descriptorLocation)
   :outertype: EventModule

Methods
-------
getListeners
^^^^^^^^^^^^

.. java:method:: public Collection<TEventListener> getListeners()
   :outertype: EventModule

hasListeners
^^^^^^^^^^^^

.. java:method:: public boolean hasListeners()
   :outertype: EventModule

init
^^^^

.. java:method:: public void init()
   :outertype: EventModule

