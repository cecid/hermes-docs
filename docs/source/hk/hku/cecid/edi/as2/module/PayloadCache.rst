.. java:import:: hk.hku.cecid.edi.as2.pkg AS2Message

.. java:import:: hk.hku.cecid.piazza.commons.io IOHandler

.. java:import:: java.io File

.. java:import:: java.io FileInputStream

.. java:import:: java.io FileNotFoundException

.. java:import:: java.io FileOutputStream

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.io OutputStream

.. java:import:: java.util.regex Matcher

.. java:import:: java.util.regex Pattern

PayloadCache
============

.. java:package:: hk.hku.cecid.edi.as2.module
   :noindex:

.. java:type:: public class PayloadCache

   PayloadCache

   :author: Hugo Y. K. Lam

Constructors
------------
PayloadCache
^^^^^^^^^^^^

.. java:constructor:: public PayloadCache(PayloadRepository repository, String messageID, String fromPartyID, String toPartyID, String type)
   :outertype: PayloadCache

PayloadCache
^^^^^^^^^^^^

.. java:constructor:: public PayloadCache(PayloadRepository repository, File file)
   :outertype: PayloadCache

Methods
-------
checkIn
^^^^^^^

.. java:method:: public boolean checkIn()
   :outertype: PayloadCache

checkOut
^^^^^^^^

.. java:method:: public boolean checkOut()
   :outertype: PayloadCache

clear
^^^^^

.. java:method:: public boolean clear()
   :outertype: PayloadCache

getCache
^^^^^^^^

.. java:method:: public File getCache()
   :outertype: PayloadCache

getContentType
^^^^^^^^^^^^^^

.. java:method:: public String getContentType()
   :outertype: PayloadCache

getFromPartyID
^^^^^^^^^^^^^^

.. java:method:: public String getFromPartyID()
   :outertype: PayloadCache

getMessageID
^^^^^^^^^^^^

.. java:method:: public String getMessageID()
   :outertype: PayloadCache

getToPartyID
^^^^^^^^^^^^

.. java:method:: public String getToPartyID()
   :outertype: PayloadCache

getType
^^^^^^^

.. java:method:: public String getType()
   :outertype: PayloadCache

isCheckedOut
^^^^^^^^^^^^

.. java:method:: public boolean isCheckedOut()
   :outertype: PayloadCache

isValid
^^^^^^^

.. java:method:: public boolean isValid()
   :outertype: PayloadCache

load
^^^^

.. java:method:: public InputStream load() throws FileNotFoundException
   :outertype: PayloadCache

save
^^^^

.. java:method:: public void save(InputStream content) throws FileNotFoundException, IOException
   :outertype: PayloadCache

toString
^^^^^^^^

.. java:method:: public String toString()
   :outertype: PayloadCache

