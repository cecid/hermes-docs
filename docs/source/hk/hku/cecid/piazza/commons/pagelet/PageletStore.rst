.. java:import:: java.util Hashtable

.. java:import:: java.util Map

PageletStore
============

.. java:package:: hk.hku.cecid.piazza.commons.pagelet
   :noindex:

.. java:type:: public class PageletStore

   A PageletStore is a holder which stores a set of pagelets for a certain context.

   :author: Hugo Y. K. Lam

   **See also:** :java:ref:`Pagelet`

Constructors
------------
PageletStore
^^^^^^^^^^^^

.. java:constructor:: public PageletStore()
   :outertype: PageletStore

   Creates a new instance of PageletStore.

Methods
-------
addPagelet
^^^^^^^^^^

.. java:method:: public Pagelet addPagelet(Pagelet pagelet)
   :outertype: PageletStore

   Adds a pagelet to this store.

   :param pagelet: the pagelet to be added.
   :return: the previous pagelet, if any, which has the same ID with the given pagelet.

getPagelet
^^^^^^^^^^

.. java:method:: public Pagelet getPagelet(String id)
   :outertype: PageletStore

   Retrieves a pagelet from this store.

   :param id: the pagelet ID.
   :return: the corresponding pagelet, if any.

removePagelet
^^^^^^^^^^^^^

.. java:method:: public Pagelet removePagelet(String id)
   :outertype: PageletStore

   Removes a pagelet from this store.

   :param id: the pagelet ID.
   :return: the removed pagelet, if any.

