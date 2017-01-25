.. java:import:: hk.hku.cecid.ebms.spa EbmsProcessor

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDAO

.. java:import:: hk.hku.cecid.ebms.spa.dao MessageDVO

.. java:import:: hk.hku.cecid.ebms.spa.handler MessageClassifier

.. java:import:: hk.hku.cecid.piazza.commons.dao DAOException

.. java:import:: hk.hku.cecid.piazza.commons.module ActiveTaskList

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: java.util Vector

OutboxCollector
===============

.. java:package:: hk.hku.cecid.ebms.spa.task
   :noindex:

.. java:type:: public class OutboxCollector extends ActiveTaskList

   :author: Donahue Sze

Fields
------
isFirstTime
^^^^^^^^^^^

.. java:field::  boolean isFirstTime
   :outertype: OutboxCollector

Methods
-------
getTaskList
^^^^^^^^^^^

.. java:method:: public List getTaskList()
   :outertype: OutboxCollector

