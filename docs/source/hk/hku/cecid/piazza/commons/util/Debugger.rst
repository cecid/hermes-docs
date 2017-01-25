.. java:import:: hk.hku.cecid.piazza.commons Sys

.. java:import:: hk.hku.cecid.piazza.commons.module Module

.. java:import:: java.util Collection

.. java:import:: java.util Enumeration

.. java:import:: java.util Iterator

.. java:import:: java.util Map

Debugger
========

.. java:package:: hk.hku.cecid.piazza.commons.util
   :noindex:

.. java:type:: public final class Debugger

   Debugger is a convenient tool for logging different Java objects, like string, collection, map, and etc., on debugging purpose. Since the logging of such objects may be expensive, the logging will only be turned on when the debug flag in the system module attached to this debugger is on.

   :author: Hugo Y. K. Lam

Methods
-------
attach
^^^^^^

.. java:method:: public static synchronized void attach(Module m)
   :outertype: Debugger

   Attach a system module to this debugger. All debugging logs will be logged to the specified system module.

   :param m: the system module to be attached.

detach
^^^^^^

.. java:method:: public static synchronized void detach(Module m)
   :outertype: Debugger

   Detach a system module from this debugger. All debugging logs will be logged to the main system module.

   :param m: the system module to be detached.

print
^^^^^

.. java:method:: public static void print(Object obj)
   :outertype: Debugger

   Prints debugging logs of the specified object. If the given object is a collection set, like iterator and list, its elements will be printed accordingly.

   :param obj: the object to be printed.

