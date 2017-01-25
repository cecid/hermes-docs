.. java:import:: java.net URL

.. java:import:: hk.hku.cecid.piazza.commons.module ComponentException

.. java:import:: hk.hku.cecid.piazza.commons.util PropertyTree

AdminProperties
===============

.. java:package:: hk.hku.cecid.piazza.corvus.core.main.admin.hc.util
   :noindex:

.. java:type:: public class AdminProperties

   A class to wrap the admin.main properties file for easier handling.

   :author: Joel Matsumoto

Fields
------
ADMIN
^^^^^

.. java:field:: public static final String ADMIN
   :outertype: AdminProperties

   The base element for the admin properties file.

CUTOFF_BEFORE
^^^^^^^^^^^^^

.. java:field:: public static final String CUTOFF_BEFORE
   :outertype: AdminProperties

DAY
^^^

.. java:field:: public static final String DAY
   :outertype: AdminProperties

EMAIL
^^^^^

.. java:field:: public static final String EMAIL
   :outertype: AdminProperties

HCPATH
^^^^^^

.. java:field:: public static final String HCPATH
   :outertype: AdminProperties

   Properties within the housecleaning element.

HOUSECLEANING
^^^^^^^^^^^^^

.. java:field:: public static final String HOUSECLEANING
   :outertype: AdminProperties

   Properties within the admin element

LAST_RUN
^^^^^^^^

.. java:field:: public static final String LAST_RUN
   :outertype: AdminProperties

NEXT_RUN
^^^^^^^^

.. java:field:: public static final String NEXT_RUN
   :outertype: AdminProperties

ON
^^

.. java:field:: public static final String ON
   :outertype: AdminProperties

PASSWORD
^^^^^^^^

.. java:field:: public static final String PASSWORD
   :outertype: AdminProperties

PORT
^^^^

.. java:field:: public static final String PORT
   :outertype: AdminProperties

REASON_FAILED
^^^^^^^^^^^^^

.. java:field:: public static final String REASON_FAILED
   :outertype: AdminProperties

SMTP
^^^^

.. java:field:: public static final String SMTP
   :outertype: AdminProperties

STATUS
^^^^^^

.. java:field:: public static final String STATUS
   :outertype: AdminProperties

TIME
^^^^

.. java:field:: public static final String TIME
   :outertype: AdminProperties

USERNAME
^^^^^^^^

.. java:field:: public static final String USERNAME
   :outertype: AdminProperties

Constructors
------------
AdminProperties
^^^^^^^^^^^^^^^

.. java:constructor:: public AdminProperties(PropertyTree tree)
   :outertype: AdminProperties

Methods
-------
getCutoff
^^^^^^^^^

.. java:method:: public int getCutoff() throws AdminPropertiesException
   :outertype: AdminProperties

   Return the 'cutoff' property if set, else if null or invalid, throw an exception.

   :throws AdminPropertiesException:
   :return: int

getDay
^^^^^^

.. java:method:: public int getDay() throws AdminPropertiesException
   :outertype: AdminProperties

   Return the 'day' property or throw an exception if an invalid integer

   :throws AdminPropertiesException:
   :return: int

getElementHC
^^^^^^^^^^^^

.. java:method:: public String getElementHC(String name) throws AdminPropertiesException
   :outertype: AdminProperties

getEmail
^^^^^^^^

.. java:method:: public String getEmail() throws AdminPropertiesException
   :outertype: AdminProperties

   Return the 'email' property if set or return an empty String. If null throw an exception.

   :throws AdminPropertiesException:
   :return: String

getLastRun
^^^^^^^^^^

.. java:method:: public String getLastRun() throws AdminPropertiesException
   :outertype: AdminProperties

   Return the 'lastrun' property if set, else return an empty String. If null, throw an exception.

   :throws AdminPropertiesException:
   :return: String

getNextRun
^^^^^^^^^^

.. java:method:: public String getNextRun() throws AdminPropertiesException
   :outertype: AdminProperties

   Return the 'nextrun' property if set, else return an empty String. If null, throw an exception.

   :throws AdminPropertiesException:
   :return: String

getPassword
^^^^^^^^^^^

.. java:method:: public String getPassword()
   :outertype: AdminProperties

getPort
^^^^^^^

.. java:method:: public int getPort() throws AdminPropertiesException
   :outertype: AdminProperties

   Return the 'port' property if set or throw an exception if null/invalid. If the value is not set, will return the deafult, 25;

   :throws AdminPropertiesException:
   :return: int

getReason
^^^^^^^^^

.. java:method:: public String getReason() throws AdminPropertiesException
   :outertype: AdminProperties

   Return the 'reason' property if set, else return an empty String. If null, throw an exception.

   :throws AdminPropertiesException:
   :return: String

getSmtp
^^^^^^^

.. java:method:: public String getSmtp() throws AdminPropertiesException
   :outertype: AdminProperties

   Return the 'smtp' property if set or return an empty String. If null, throw an exception.

   :throws AdminPropertiesException:
   :return: String

getStatus
^^^^^^^^^

.. java:method:: public String getStatus() throws AdminPropertiesException
   :outertype: AdminProperties

   Return the 'status' property if set, else return an empty String. If null, throw an exception.

   :throws AdminPropertiesException:
   :return: String

getTime
^^^^^^^

.. java:method:: public String getTime() throws AdminPropertiesException
   :outertype: AdminProperties

   Return the 'time' property.

   :throws AdminPropertiesException:
   :return: String

getUsername
^^^^^^^^^^^

.. java:method:: public String getUsername() throws AdminPropertiesException
   :outertype: AdminProperties

   Return the 'username' property if set, else return an empty String. If null, throw an exception.

   :throws AdminPropertiesException:
   :return: String

isOn
^^^^

.. java:method:: public boolean isOn()
   :outertype: AdminProperties

   Return a boolean depending on if the value is set to ON/OFF or return false if none set/null/invalid.

   :return: boolean

setCutoff
^^^^^^^^^

.. java:method:: public void setCutoff(int cutoff)
   :outertype: AdminProperties

   Set the property 'cutoff'.

   :param cutoff:

setDay
^^^^^^

.. java:method:: public void setDay(int day)
   :outertype: AdminProperties

   Set the property 'day'. 1-7 Sun-Sat

   :param day:

setElementHC
^^^^^^^^^^^^

.. java:method:: public void setElementHC(String name, String value)
   :outertype: AdminProperties

setEmail
^^^^^^^^

.. java:method:: public void setEmail(String email)
   :outertype: AdminProperties

   Set the property 'email'.

   :param email:

setLastRun
^^^^^^^^^^

.. java:method:: public void setLastRun(String lastrun)
   :outertype: AdminProperties

   Set the property 'lastrun'.

   :param lastrun:

setNextRun
^^^^^^^^^^

.. java:method:: public void setNextRun(String nextrun)
   :outertype: AdminProperties

   Set the property 'nextrun'.

   :param nextrun:

setOn
^^^^^

.. java:method:: public void setOn(boolean b)
   :outertype: AdminProperties

   Set the property 'on'.

   :param b:

setPassword
^^^^^^^^^^^

.. java:method:: public void setPassword(String password)
   :outertype: AdminProperties

setPort
^^^^^^^

.. java:method:: public void setPort(int port)
   :outertype: AdminProperties

   Set the property 'port'.

   :param port:

setReason
^^^^^^^^^

.. java:method:: public void setReason(String reason)
   :outertype: AdminProperties

   Set the property 'reason'.

   :param reason:

setSmtp
^^^^^^^

.. java:method:: public void setSmtp(String smtp)
   :outertype: AdminProperties

   Set the property 'smtp'.

   :param smtp:

setStatus
^^^^^^^^^

.. java:method:: public void setStatus(String status)
   :outertype: AdminProperties

   Set the property 'status'.

   :param status:

setTime
^^^^^^^

.. java:method:: public void setTime(String time)
   :outertype: AdminProperties

   Set the property 'time'.

   :param time:

setUsername
^^^^^^^^^^^

.. java:method:: public void setUsername(String username)
   :outertype: AdminProperties

   Set the property 'username'.

   :param username:

write
^^^^^

.. java:method:: public void write() throws AdminPropertiesException
   :outertype: AdminProperties

   Writes the property tree to url asscoaited with the component

   :throws AdminPropertiesException:

write
^^^^^

.. java:method:: public void write(URL u) throws AdminPropertiesException
   :outertype: AdminProperties

   Writes to the specified url.

   :param u:
   :throws AdminPropertiesException:

