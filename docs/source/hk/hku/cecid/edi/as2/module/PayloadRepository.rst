.. java:import:: hk.hku.cecid.piazza.commons.io FileSystem

.. java:import:: hk.hku.cecid.piazza.commons.module Component

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyMap

.. java:import:: java.io File

.. java:import:: java.util ArrayList

.. java:import:: java.util Hashtable

.. java:import:: java.util Iterator

.. java:import:: java.util List

.. java:import:: java.util Map

.. java:import:: java.util Properties

PayloadRepository
=================

.. java:package:: hk.hku.cecid.edi.as2.module
   :noindex:

.. java:type:: public class PayloadRepository extends Component

   PayloadRepository

   :author: Hugo Y. K. Lam

Constructors
------------
PayloadRepository
^^^^^^^^^^^^^^^^^

.. java:constructor:: public PayloadRepository()
   :outertype: PayloadRepository

Methods
-------
createPayloadCache
^^^^^^^^^^^^^^^^^^

.. java:method:: public PayloadCache createPayloadCache(String messageID, String fromPartyID, String toPartyID, String type)
   :outertype: PayloadRepository

getPayloadCaches
^^^^^^^^^^^^^^^^

.. java:method:: public List getPayloadCaches()
   :outertype: PayloadRepository

getPayloadContentType
^^^^^^^^^^^^^^^^^^^^^

.. java:method:: public String getPayloadContentType(String type)
   :outertype: PayloadRepository

getPayloadType
^^^^^^^^^^^^^^

.. java:method:: public String getPayloadType(String contentType)
   :outertype: PayloadRepository

getPayloadTypes
^^^^^^^^^^^^^^^

.. java:method:: public Map getPayloadTypes()
   :outertype: PayloadRepository

getRepository
^^^^^^^^^^^^^

.. java:method:: public File getRepository()
   :outertype: PayloadRepository

init
^^^^

.. java:method:: protected void init() throws Exception
   :outertype: PayloadRepository

initRepository
^^^^^^^^^^^^^^

.. java:method:: protected void initRepository(String repository)
   :outertype: PayloadRepository

initRepository
^^^^^^^^^^^^^^

.. java:method:: protected void initRepository(File repository)
   :outertype: PayloadRepository

setPayloadTypes
^^^^^^^^^^^^^^^

.. java:method:: public void setPayloadTypes(Map m)
   :outertype: PayloadRepository

