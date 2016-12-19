.. _configuration:

Hermes 2 Configuration Guide
============================

iASPEC Services Limited

Unit 507-9, InnoCentre, 

72 Tat Chee Avenue, Kowloon Tong, Hong Kong

July 2005

The copyright in the Document, and all original documents attached to it or enclosed, is vested in iASPEC Services Limited.  All other copyrights and Trademarks referenced in the Document are acknowledged.

The Document must not be reproduced, in whole or in part by any means, or used for tendering or manufacturing purposes, or disclosed to a third party, except with the written consent of iASPEC Services Limited.


Introduction
------------

Purpose of This Document
^^^^^^^^^^^^^^^^^^^^^^^^

This document acts as a configuration reference for Hermes 2.0 Community Edition (CE) and Enterprise Edition (EE). The configurations of Hermes 2.0 are specified by various XML-based configuration files. By modifying these files, the administrators or developers can configure all the settings such as the location of the message database, log file locations, etc.

Intended Audience
^^^^^^^^^^^^^^^^^

The intended audience of this document includes system administrators, application developers and plug-in developers of the Hermes 2.0 system. It is expected the audience has some background knowledge of the following:

*   Java 2 Standard Edition
*   XML
*   AS2
*   ebXML Messaging Services
*   Public Key Infrastructure
*   Application server compliant to Servlet 2.x specification
*   Databases

Overview on how properties file are loaded
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Hermes 2 has employed a module-group-component architecture which you can define your own module for each application. You can then assign a property file for each component and the Hermes 2 Core System will load them.

There are 2 loading mechanism, one for the Core System and one for the Plugins. The two resembles closely except the initial definition.  

Let's take a look at how the Core System modules are being loaded. 

.. image:: _static/images/2-overview-1.jpeg

For the Core System, it will look for the existence of a file named :file:`sys.properties` from the classpath which contains the location of the module-group definition file. E.g.,

    :file:`sys.module.group=doc-processor.module-group.xml`

From there, the system will look for the specified XML file and load up the modules specified in within. The modules specified could be a System Module, which contains infrastructure components like logging, database access. Or, it could be an Active Module, which performs the business function like sending out messages.

.. code-block:: xml

   <module id="piazza.corvus" name="Piazza Corvus" version="1.0">
     <component id="logger" name="System Logger">
       <class>hk.hku.cecid.piazza.commons.util.LoggerLog4j</class>
       <parameter name="config" 
                  value="hk/hku/cecid/piazza/corvus/core/conf/corvus.log.properties.xml" />		
       <parameter name="category" value="hk.hku.cecid.piazza" />
     </component>
   ...
   </module>

For the plugins, the loading mechanism will be a little bit different, instead of looking for a file named :file:`sys.properties`, it will look for a file named :file:`plugin.xml` instead. 

.. image:: _static/images/2-overview-2.jpeg

From within, a parameter with value named as :literal:`module-group-descriptor` will define the location of the module-group definition.

.. code-block:: xml

   <?xml version="1.0" encoding="UTF-8"?>
   <plugin
     id="hk.hku.cecid.edi.as2"
     name="Corvus AS2 Plugin"
     version="1.0.1"
     provider-name="hk.hku.cecid"
     class="hk.hku.cecid.edi.as2.AS2Processor"
   >
     <parameters>
       <parameter name="module-group-descriptor"
                  value="hk/hku/cecid/edi/as2/conf/as2.module-group.xml"/>
     </parameters>
   ...
   </plugin>

Hermes 2 Core System properties
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
You can modify the following information either through the web admin interface or by manipulating the XML configuration files directly.

The configuration files are stored in :file:`{[Webapps Location]}/corvus/WEB-INF/classes/hk/hku/cecid/piazza/corvus/core/conf` (where :file:`{[Webapps Location]}` is the Web application repository of the application server).

+----------------------------------------------------------------------+----------------------------------------+
| Tasks                                                                | Responsible configuration file         |
+======================================================================+========================================+
| 1.    Hermes 2 location                                              |                                        |
|                                                                      |                                        | 
| 2.    Plugin location for Hermes 2                                   |                                        |
|                                                                      |                                        | 
| 3.    SSL trust store information                                    |                                        |
|                                                                      |                                        | 
| 4.    Information in accessing proxy server                          | :file:`corvus.properties.xml`          |           
|                                                                      |                                        | 
| 5.    Encoding setting for core system                               |                                        |       
|                                                                      |                                        | 
| 6.    Connection timeout setting                                     |                                        | 
+----------------------------------------------------------------------+----------------------------------------+
| 7.    Log file location and levels of logging                        | :file:`corvus.log.properties.xml`      |
+----------------------------------------------------------------------+----------------------------------------+

Hermes 2 location
^^^^^^^^^^^^^^^^^
You can change the location of the Hermes 2 by modifying this element:

.. code-block:: xml

   <corvus>
     <home>/corvus</home>
     …
   </corvus>

+----------------------------------+--------------------------------------------------------------------------------------------------+
| XPath of the Element / Attribute | Expected information                                                                             |
+==================================+==================================================================================================+
| :file:`/corvus/home`             | The location from which Hermes 2 is installed. Note that the path specified is an absolute path. |
+----------------------------------+--------------------------------------------------------------------------------------------------+
 
Plugin location for Hermes 2
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
You can change the plugin location of the Hermes 2 by modifying this element.

.. code-block:: xml

   <corvus>
     …
     <plugin>
       …   
       <registry>/corvus/plugins</registry>
       <descriptor>plugin.xml</descriptor>
       …
     </plugin>
     …
   </corvus>

+-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Element / Attribute               | Expected information                                                                                                                                                                                                  |
+===================================+=======================================================================================================================================================================================================================+
| :code:`/corvus/plugin/registry`   | The location from which Hermes 2 plugin is installed. Normally it should be the :literal:`plugins` directory under the home directory where Hermes 2 is installed.  Note that the path specified is an absolute path. |
+-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/corvus/plugin/descriptor` | The name of the XML file which Hermes 2 will use in loading the Modulegroup-Component.                                                                                                                                |
+-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

SSL trust store information
^^^^^^^^^^^^^^^^^^^^^^^^^^^
.. code-block:: xml

   <corvus>
     …
       <environment>
         <properties>
             …
           <javax.net.ssl.trustStore>/j2sdk1.4.2_04/jre/lib/security/cacerts
           </javax.net.ssl.trustStore>
           <javax.net.ssl.trustStorePassword>password
           </javax.net.ssl.trustStorePassword>
           …
         </properties>
       <environment>
   </corvus>


+-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Element / Attribute                                                     | Expected information                                                                                                                                                                                                                                                                                                                                                                        |
+=========================================================================+=============================================================================================================================================================================================================================================================================================================================================================================================+
| :code:`/corvus/environment/properties/javax.net.ssl.trustStore`         | The location of the java keystore which is used for establishing SSL connection. The keystore should contain the certificates of trusted certificate authorities. To maintain the keystore, the reader should use the :program:`keytool` provided by :program:`JDK`. For more information, the reader may reference http://java.sun.com/j2se/1.4.2/docs/tooldocs/windows/keytool.html.      |
+-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/corvus/environment/properties/javax.net.ssl.trustStorePassword` | The password used to access the keystore specified above.                                                                                                                                                                                                                                                                                                                                   |
+-------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

HTTP/HTTPS proxy server
^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: xml

   <corvus>
     …
       <environment>
         <properties>
           <http.proxyHost>proxy.csis.hku.hk</http.proxyHost> 
           <http.proxyPort>8282</http.proxyPort> 
           <https.proxyHost>proxy.csis.hku.hk</https.proxyHost> 
           <https.proxyPort>8282</https.proxyPort>
           …
         </properties>
       <environment>
   </corvus>


+--------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------+
| Element / Attribute                                    | Expected information                                                                                            |
+========================================================+=================================================================================================================+
| :code:`/corvus/environment/properties/http.proxyHost`  | The hostname or IP address of the proxy host for Hermes 2 to establish HTTP connections for outgoing messages.  |
+--------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------+
| :code:`/corvus/environment/properties/http.proxyPort`  | The TCP port of the proxy server that is specified above.                                                       |
+--------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------+
| :code:`/corvus/environment/properties/https.proxyHost` | The hostname or IP address of the proxy host for Hermes 2 to establish HTTPS connections for outgoing messages. |
+--------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------+
| :code:`/corvus/environment/properties/https.proxyPort` | The TCP port of the proxy that is specified above.                                                              |
+--------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------+

Encoding setting for core system
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: xml

   <corvus>
     …
       <encoding>
         <servlet-request>UTF-8</servlet-request>
         <servlet-response>text/html;UTF-8</servlet-response>
       </encoding>
   …
   </corvus>


+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------+
| Element / Attribute                       | Expected information                                                                                                                         |
+===========================================+==============================================================================================================================================+
| :code:`/corvus/encoding/servlet-request`  | The encoding of the incoming HTTP or HTTPS requests. :literal:`UTF-8` is the recommended value because it can handle most written languages. |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/corvus/encoding/servlet-response` | The encoding of the outgoing HTTP or HTTP responses.                                                                                         |
+-------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------+

Connection timeout setting
^^^^^^^^^^^^^^^^^^^^^^^^^^
.. code-block:: xml

   <corvus>
       …
     <properties>
       …
       <sun.net.client.defaultConnectTimeout>30000</sun.net.client.defaultConnectTimeout>
       <sun.net.client.defaultReadTimeout>300000</sun.net.client.defaultReadTimeout>
       …
     </properties>
     …
   </corvus>


+----------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Element / Attribute                                            | Expected information                                                                                                                                                       |
+================================================================+============================================================================================================================================================================+
| :code:`/corvus/properies/sun.net.client.defaultConnectTimeout` | It specifies the timeout (in milliseconds) to establish the HTTP or HTTPS connections for outgoing messages. :literal:`30` seconds is the recommended value.               |
+----------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/corvus/properies/sun.net.client.defaultReadTimeout`    | It specifies the timeout (in milliseconds) when reading from input stream when a HTTP or HTTPS connection is established. :literal:`300` seconds is the recommended value. |
+----------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Log file location and levels of logging
To change the settings of the log reported by corvus, you will need to modify the XML file named :file:`corvus.log.properties.xml`. How to configure the logging module is the same as configuring Apache Log4j. Note that for configuring the logs of ebMS plug-ins, you need to edit another configuration file.

.. code-block:: xml

   <log4j:configuration debug="null" threshold="null" xmlns:log4j="http://jakarta.apache.org/log4j/">
   <appender name="corvus" class="org.apache.log4j.RollingFileAppender">     
     <param name="File" value="/corvus/corvus.log"/>     
     <param name="Encoding" value="UTF-8"/>     
     <param name="MaxFileSize" value="100KB"/>     
     <param name="MaxBackupIndex" value="1"/>     
     <layout class="org.apache.log4j.PatternLayout">       
       <param name="ConversionPattern" value="%d{yyyy-MM-dd HH:mm:ss} [%-12.12t] &lt;%-5p&gt; &lt;%m&gt;%n"/>     
     </layout>  
   </appender>
   <category additivity="true" name="hk.hku.cecid.piazza">
     <priority value="debug"/>
     <appender-ref ref="corvus"/>
   </category>
   </log4j:configuration>

+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Element / Attribute                                                                                                                                                                                                  | Expected information                                                                                                                                                                                                                                                                                             |
+======================================================================================================================================================================================================================+==================================================================================================================================================================================================================================================================================================================+
| :code:`log4j/category/priority`                                                                                                                                                                                      | The log level of the Corvus logging. The available levels are :code:`debug`, :code:`info`, :code:`warn`, :code:`error` and :code:`fatal`. If you set the value as :code:`debug`, all logs will be printed.                                                                                                       |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/category/appender-ref@ref`                                                                                                                                                                             | The name of the :code:`appender` to be used for logging. An :code:`appender` is to specify how to generate log files. In the above example, an :code:`appender` configuration element :code:`corvus` is used. The settings of the :code:`appender` are specified by the referenced :code:`appender` element.     |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender@class`                                                                                                                                                                                        | The appender specified by this :code:`appender` configuration element. Apache Log4j provides a series of appender, such :code:`RollingFileAppender`, :code:`DailyRollingFileAppender`, etc.                                                                                                                      |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender@name`                                                                                                                                                                                         | The name of this appender configuration element. The :file:`/category/appender-ref@ref` should reference the appender configuration element by this name.                                                                                                                                                        |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/param[@name='File']/@value` (i.e. The :code:`value` attribute of the :code:`param` element under :code:`appender` element, whose :code:`name` attribute is :code:`File`)                      | The path of Corvus log of this appender.                                                                                                                                                                                                                                                                         |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/param[@name='Encoding']/@value` (i.e. The :code:`value` attribute of the :code:`param` element under :code:`appender` element, whose :code:`name` attribute is :code:`Encoding`               | The encoding to be used for the log file.                                                                                                                                                                                                                                                                        |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/param[@name='MaxFileSize']/@value` (i.e. The :code:`value` attribute of the :code:`param` element under :code:`appender` element, whose :code:`name` attribute is :code:`MaxFileSize'`        | If the size of a log file has grown to exceed this limit, another new log file will be written and the old log file will be backed up. The backed-up log file's filename will have an index appended (e.g. :file:`corvus.log.1`).                                                                                |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/param[@name='MaxBackupIndex']/@value` (i.e. The :code:`value` attribute of the :code:`param` element under :code:`appender` element, whose :code:`name` attribute is :code:`MaxBackupIndex`   | The maximum number of log files which will be backed up. For example, if it is set to 10, the maximum number of backed up log files will be 10 and their filenames will be :file:`xxx.log.1`, :file:`xxx.log.2`, … :file:`xxx.log.10`.                                                                           | 
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/layout/param[@name='ConversionPattern']/@value`                                                                                                                                               | The pattern used in writing out the log file.                                                                                                                                                                                                                                                                    |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Hermes2 Plugins properties
----------------------------------------------

AS2 Plugin
^^^^^^^^^^
In the directory :file:`{<Hermes 2 Plugins Location>}/hk.hku.cecid.edi.as2/conf/hk/hku/cecid/edi/as2/conf`, there are some configuration files for Hermes 2's AS2 plug-in. Which configuration file you should edit depends on your configuration task:


+----------------------------------------------------+----------------------------------------+
| Tasks                                              | Responsible configuration file         |
+====================================================+========================================+
| Log file location and level of logging             | :file:`As2.log.properties.xml`         |
+----------------------------------------------------+----------------------------------------+
| Information of the database to use                 | :file:`As2.module.core.xml`            |
+----------------------------------------------------+                                        |
| Location of keystore for signing outgoing messages |                                        |
+----------------------------------------------------+                                        |
| Location of the message repository                 |                                        |
+----------------------------------------------------+----------------------------------------+


Log file location and levels of logging
"""""""""""""""""""""""""""""""""""""""
To change the location of the log file, you will need to modify the XML file named :file:`as2.log.properties.xml`.

    .. code-block:: xml

       <log4j:configuration debug="null" threshold="null" xmlns:log4j="http://jakarta.apache.org/log4j/">
       <appender name="as2" class="org.apache.log4j.RollingFileAppender">     
         <param name="File" value="/as2.log"/>     
         <param name="Encoding" value="UTF-8"/>     
         <param name="MaxFileSize" value="100KB"/>     
         <param name="MaxBackupIndex" value="1"/>     
         <layout class="org.apache.log4j.PatternLayout">       
         <param name="ConversionPattern" 
                value="%d{yyyy-MM-dd HH:mm:ss} [%-12.12t] &lt;%-5p&gt; &lt;%m&gt;%n"/>     
         </layout>  
       </appender>
       <category additivity="true" name="hk.hku.cecid.piazza">
         <priority value="debug"/>
         <appender-ref ref="as2"/>
       </category>
       </log4j:configuration>

+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Element / Attribute                                                                                                                                                                                                     | Expected information                                                                                                                                                                                                                                                                                            | 
+=========================================================================================================================================================================================================================+=================================================================================================================================================================================================================================================================================================================+
| :code:`/log4j/category/priority`                                                                                                                                                                                        | The log level of the AS2 plug-in logging. The available levels are :code:`debug`, :code:`info`, :code:`warn`, :code:`error` and :code:`fatal`. If you set the value as :code:`debug`, all logs will be printed.                                                                                                 | 
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/category/appender-ref@ref`                                                                                                                                                                                | The name of the :code:`appender` to be used for logging. An :code:`appender` is to specify how to generate log files. In the above example, an :code:`appender` configuration element :code:`as2` is used. The settings of the :code:`appender` are specified by the referenced :code:`appender` element.       |
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender@class`                                                                                                                                                                                           | The appender specified by this "appender" configuration element. Apache Log4j provides a series of appender, such RollingFileAppender, DailyRollingFileAppender, etc.                                                                                                                                           | 
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender@name`                                                                                                                                                                                            | The name of this appender configuration element. The :file:`/category/appender-ref@ref` should reference the appender configuration element by this name.                                                                                                                                                       | 
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/param[@name='File']/@value` (i.e. The :code:`value` attribute of the :code:`param` element under :code:`appender` element, whose :code:`name` attribute is :code:`File`)                         | The path of AS2 log of this appender.                                                                                                                                                                                                                                                                           |
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/param[@name='Encoding']/@value` (i.e. The :code:`value` attribute of the :code:`param` element under :code:`appender` element, whose :code:`name` attribute is :code:`Encoding`)                 | The encoding to be used for the log file.                                                                                                                                                                                                                                                                       |
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/param[@name='MaxFileSize']/@value` (i.e. The :code:`value` attribute of the :code:`param` element under :code:`appender` element, whose :code:`name` attribute is :code:`MaxFileSize`)           | If the size of a log file has grown to exceed this limit, another new log file will be written and the old log file will be backed up. The backed-up log file's filename will have an index appended (e.g. :file:`as2.log.1`).                                                                                  |
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/param[@name='MaxBackupIndex]/@value` (i.e. The :code:`value` attribute of the :code:`param` element under :code:`appender` element, whose :code:`name` attribute is :code:`MaxBackupIndex`)      | The maximum number of log files which will be backed up. For example, if it is set to 10, the maximum number of backed up log files will be 10 and their filenames will be :file:`xxx.log.1`, :file:`xxx.log.2`, … :file:`xxx.log.10`.                                                                          |
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/layout/param[@name='ConversionPattern']/@value`                                                                                                                                                  | The pattern used in writing out the log file.                                                                                                                                                                                                                                                                   |
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+


Connections to Message Database
"""""""""""""""""""""""""""""""

.. code-block:: xml

   <module>
   …
   <component id="daofactory" name="AS2 DAO Factory">
   <class>
   hk.hku.cecid.piazza.commons.dao.ds.SimpleDSDAOFactory
   </class>
     <parameter name="driver" value="org.postgresql.Driver" />
     <parameter name="url" 
                value="jdbc:postgresql://localhost:5432/as2" />
     <parameter name="username" value="corvus" />
     <parameter name="password" value="corvus" />
     <parameter name="pooling" value="true" />
     <parameter name="maxActive" value="20" />
     <parameter name="maxIdle" value="10" />
     <parameter name="maxWait" value="-1" />
     <parameter name="config" 
                value="hk/hku/cecid/edi/as2/conf/as2.dao.xml" />
   </component>
   …
   </module>

+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Element / Attribute                                                                         | Expected information                                                                                                                                                                                                                                                              |
+=============================================================================================+===================================================================================================================================================================================================================================================================================+
| :code:`/module/component[@id='daofactory']/class`                                           | The java class to use in establishing database connection, you can select from                                                                                                                                                                                                    |  
|                                                                                             |                                                                                                                                                                                                                                                                                   | 
|                                                                                             | * :code:`hk.hku.cecid.piazza.commons.dao.ds.SimpleDSDAOFactory`, if you want AS2 to manage the database connection pool                                                                                                                                                           |
|                                                                                             | * :code:`hk.hku.cecid.piazza.commons.dao.ds.DataSourceDAOFactory`, if you want the application server manages the database connection pool, which is accessible through JNDI (Java Naming and Directory Interface) name.                                                          | 
+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Belows are fields you need to fill in if you are using SimpleDSDAOFactory                                                                                                                                                                                                                                                                                                       |
+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='driver']/@value`       | The JDBC driver that should be used, we have provided the driver for postgres by default. You should put the driver to your :file:`{[Tomcat Home]}/webapps/corvus/WEB-INF/lib`, where we suppose the web application repository is configured as :file:`{[Tomcat Home]}/webapps`. |
+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='url']/@value`          | The URL in establishing the database connection, please refer to the document of the JDBC driver for the syntax. For PostgreSQL datatabse, the syntax is :code:`jdbc:postgresql://<IP or hostname of the database>/<message database name for AS2>`                               |
+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='username']/@value`     | The username to connect to the database.                                                                                                                                                                                                                                          |
+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='password']/@value`     | The password for the username specified.                                                                                                                                                                                                                                          |
+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='pooling']/@value`      | The boolean value (:literal:`true`/:literal:`false`) specifying if connection pooling should be used.                                                                                                                                                                             |
+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='maxActive']/@value`    | The maximum number of active threads.                                                                                                                                                                                                                                             |
+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='maxIdle']/@value`      | The maximum number of threads that can remains idle.                                                                                                                                                                                                                              |
+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='maxWait']/@value`      | The maximum number of milliseconds that the pool will wait (when there are no available connections) for a connection to be returned before throwing an exception, or :literal:`-1` to wait indefinitely.                                                                         |
+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='config']/@value`       | Additional configuration files that will be used by the plug-in. You should just leave it as is.                                                                                                                                                                                  |
+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Belows are fields you need to fill in if you are using DataSourceDAOFactory                                                                                                                                                                                                                                                                                                     |
+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| datasource                                                                                  | The JNDI name of the Data Source for connecting the message database, e.g. :code:`java:/comp/env/jdbc/as2db`                                                                                                                                                                      |
+---------------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Location of Keystore for Digital Sigature on Outgoing Messages
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

.. code-block:: xml

    <module id="as2.core" name="Corvus AS2" version="1.0">
    …
    <component id="keystore-manager" name="AS2 Key Store Manager">
      <class>hk.hku.cecid.piazza.commons.security.KeyStoreManager</class>
      <parameter name="keystore-location" value="as2.p12"/>
      <parameter name="keystore-password" value="password"/>
      <parameter name="key-alias" value="corvusas2"/>
      <parameter name="key-password" value=""/>
      <parameter name="keystore-type" value="PKCS12"/>
      <parameter name="keystore-provider" 
                 value="org.bouncycastle.jce.provider.BouncyCastleProvider"/>
      </component>
    …
    </module>

+-----------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------+
| Element / Attribute                                                                           | Expected information                                                                     |
+===============================================================================================+==========================================================================================+
| :code:`/module/component[@id='keystore-manager']/parameter[@name='keystore-location']/@value` | The path of the keystore for signing outgoing messages.                                  |
+-----------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='keystore-manager']/parameter[@name='keystore-password']/@value` | The password for accessing the keystore.                                                 |
+-----------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='keystore-manager]/parameter[@name='key-alias']/@value`          | The alias of the private key for digital signature.                                      |
+-----------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='keystore-manager]/parameter[@name='key-password']/@value`       | The password protecting the private key for digital signature.                           |
+-----------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='keystore-manager]/parameter[@name='keystore-type']/@value`      | The keystore format of the keystore. It is either :literal:`PKCS12` or :literal:`JKS`.   |
+-----------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------+

Location of the message repository
""""""""""""""""""""""""""""""""""
Outgoing Repository:

.. code-block:: xml

   <module id="as2.core" name="Corvus AS2" version="1.0">
   …
   <component id="outgoing-payload-repository" name="AS2 Outgoing Payload Repository">
   <class>
   hk.hku.cecid.edi.as2.module.PayloadRepository
   </class>
     <parameter name="location" value="/as2-outgoing-repository" />
     <parameter name="type-edi" value="application/EDIFACT" />
     <parameter name="type-x12" value="application/EDI-X12" />
     <parameter name="type-eco" value="application/edi-consent" />
     <parameter name="type-xml" value="application/XML" />
   </component>
   …
   </module>


+---------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
| Element / Attribute                                                                                     | Expected information                                                                                                                   |
+=========================================================================================================+========================================================================================================================================+
| :code:`/module/component[id='outgoing-payload-repository']/class`                                       | The java class responsible for handing the outgoing payload. You should just leave it as is.                                           |
+---------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[id='outgoing-payload-repository']/` :code:`parameter[@name='location']/@value` | The folder location which will store the outgoing payload. E.g., :file:`c:\program files\hermes2\repository\as2-outgoing-repository`   |
+---------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[id='outgoing-payload-repository']/` :code:`parameter[@name='type-edi]/@value`  | You should leave the field as what it is.                                                                                              |
+---------------------------------------------------------------------------------------------------------+                                                                                                                                        |
| :code:`/module/component[id='outgoing-payload-repository']/` :code:`parameter[@name='type-x12]/@value`  |                                                                                                                                        |
+---------------------------------------------------------------------------------------------------------+                                                                                                                                        |
| :code:`/module/component[id='outgoing-payload-repository']/` :code:`parameter[@name='type-eco]/@value`  |                                                                                                                                        |
+---------------------------------------------------------------------------------------------------------+                                                                                                                                        |
| :code:`/module/component[id='outgoing-payload-repository']/` :code:`parameter[@name='type-xml]/@value`  |                                                                                                                                        |
+---------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+

.. code-block:: xml

   <module id="as2.core" name="Corvus AS2" version="1.0">
   …
   <component id="incoming-payload-repository" name="AS2 Incoming Payload Repository">		
     <class>
       hk.hku.cecid.edi.as2.module.PayloadRepository
     </class>
     <parameter name="location" value="/as2-incoming-repository" />
     <parameter name="type-edi" value="application/EDIFACT" />
     <parameter name="type-x12" value="application/EDI-X12" />
     <parameter name="type-eco" value="application/edi-consent" />
     <parameter name="type-xml" value="application/XML" />
   </component>
   …
   </module>


+-------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+
| Element / Attribute                                                                                         | Expected information                                                                                                                  |
+=============================================================================================================+=======================================================================================================================================+
| :code:`/module/component[id='incoming-payload-repository']/class`                                           | The java class responsible for handing the incoming payload. You should just leave it as is.                                          |
+-------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[id='outgoing-payload-repository']/` :code:`parameter[@name='location']/@value`     | The folder location which will store the outgoing payload. E.g., :file:`c:\program files\hermes2\repository\as2-incoming-repository`  |
+-------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[id='outgoing-payload-repository']/` :code:`parameter[@name='type-edi]/@value`      | You should leave the field as what it is.                                                                                             |
+-------------------------------------------------------------------------------------------------------------+                                                                                                                                       |
| :code:`/module/component[id='outgoing-payload-repository']/` :code:`parameter[@name='type-x12]/@value`      |                                                                                                                                       |
+-------------------------------------------------------------------------------------------------------------+                                                                                                                                       |
| :code:`/module/component[id='outgoing-payload-repository']/` :code:`parameter[@name='type-eco]/@value`      |                                                                                                                                       |
+-------------------------------------------------------------------------------------------------------------+                                                                                                                                       |
| :code:`/module/component[id='outgoing-payload-repository']/` :code:`parameter[@name='type-xml]/@value`      |                                                                                                                                       |
+-------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------+


Original Message Repository (It is a temporary message repository used when Hermes 2 is composing or receiving AS2 messages):


.. code-block:: xml

   <module id="as2.core" name="Corvus AS2" version="1.0">
   …
   <component id="original-message-repository" name="AS2 Original Message Repository">		
     <class>
       hk.hku.cecid.edi.as2.module.MessageRepository
     </class>
       <parameter name="location" value="/as2-message-repository" />
       <parameter name="is-disabled" value="false" />
   </component>
   …
   </module>

+-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
| Element / Attribute                                               | Expected information                                                                                                                |
+===================================================================+=====================================================================================================================================+
| :code:`/module/component[id='original-payload-repository']/class` | The java class responsible for handing the original message. You should just leave it as is.                                        |
+-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
| :code:`location`                                                  | The folder location which will store the outgoing payload. E.g., :file:`c:\program files\hermes2\repository\as2-message-repository` |
+-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
| :code:`is-disabled`                                               | The flag indicates if the original message should be stored locally.                                                                |
+-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+


ebMS Plugin
^^^^^^^^^^^
In the directory :file:`{<Hermes 2 Plugins Location>}/hk.hku.cecid.ebms/conf/hk/hku/cecid/ebms/spa/conf`, there are some configuration files for Hermes 2's AS2 plug-in. Which configuration file you should edit depends on your configuration task:

+------------------------------------------------------------------+----------------------------------------+
| Tasks                                                            | Responsible configuration file         |
+==================================================================+========================================+
| Log file location and level of logging                           | :file:`Log4j.properties.xml`           |
+------------------------------------------------------------------+----------------------------------------+
| Connections to Message Database                                  | :file:`Ebms.module.xml`                |
+------------------------------------------------------------------+                                        |
| Location of keystore for digital signature on outgoing messages  |                                        |
+------------------------------------------------------------------+                                        |
| Location of keystore for S/MIME decryption for incoming messages |                                        |
+------------------------------------------------------------------+----------------------------------------+


Log file location and levels of logging
"""""""""""""""""""""""""""""""""""""""
To change the location of the log file, you will need to modify the XML file named :file:`as2.log.properties.xml`

.. code-block:: xml

   <log4j:configuration debug="null" threshold="null" xmlns:log4j="http://jakarta.apache.org/log4j/">
   <appender name="RollingFileAppender" class="org.apache.log4j.RollingFileAppender">     
     <param name="File" value="/as2.log"/>     
     <param name="Encoding" value="UTF-8"/>     
     <param name="MaxFileSize" value="100KB"/>     
     <param name="MaxBackupIndex" value="1"/>     
     <layout class="org.apache.log4j.PatternLayout">       
     <param name="ConversionPattern" 
            value="%d{yyyy-MM-dd HH:mm:ss} [%-12.12t] &lt;%-5p&gt; &lt;%m&gt;%n"/>     
     </layout>  
   </appender>
   <category additivity="true" name="hk.hku.cecid.piazza">
       <priority value="debug"/>
       <appender-ref ref="RollingFileAppender"/>
     </category>
   </log4j:configuration>

+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Element / Attribute                                                                                                                                                                                                 | Expected information                                                                                                                                                                                                                                                                                                             |
+=====================================================================================================================================================================================================================+==================================================================================================================================================================================================================================================================================================================================+
| :code:`/log4j/category/priority`                                                                                                                                                                                    | The log level of the AS2 plug-in logging. The available levels are :code:`debug`, :code:`info`, :code:`warn`, :code:`error` and :code:`fatal`. If you set the value as :code:`debug`, all logs will be printed.                                                                                                                  |
+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/category/appender-ref@ref`                                                                                                                                                                            | The name of the :code:`appender` to be used for logging. An :code:`appender` is to specify how to generate log files. In the above example, an :code:`appender` configuration element :code:`RollingFileAppender` is used. The settings of the :code:`appender` are specified by the referenced :code:`appender` element.        |
+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender@class`                                                                                                                                                                                       | The appender specified by this :code:`appender` configuration element. Apache Log4j provides a series of appender, such :code:`RollingFileAppender`, :code:`DailyRollingFileAppender`, etc.                                                                                                                                      |
+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender@name`                                                                                                                                                                                        | The name of this appender configuration element. The :file:`/category/appender-ref@ref` should reference the appender configuration element by this name.                                                                                                                                                                        |
+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/param[@name='File']/@value` (i.e. The :code:`value` attribute of the :code:`param` element under :code:`appender` element, whose :code:`name` attribute is :code:`File`)                     | The path of AS2 log of this appender.                                                                                                                                                                                                                                                                                            |
+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/param[@name='Encoding']/@value` (i.e. The :code:`value` attribute of the :code:`param` element under :code:`appender` element, whose :code:`name` attribute is :code:`Encoding`)             | The encoding to be used for the log file.                                                                                                                                                                                                                                                                                        |
+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/param[@name='MaxFileSize']/@value` (i.e. The :code:`value` attribute of the :code:`param` element under :code:`appender` element, whose :code:`name` attribute is :code:`MaxFileSize'`)      | If the size of a log file has grown to exceed this limit, another new log file will be written and the old log file will be backed up. The backed-up log file's filename will have an index appended (e.g. :file:`as2.log.1`).                                                                                                   |
+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/param[@name='MaxBackupIndex']/@value` (i.e. The :code:`value` attribute of the :code:`param` element under :code:`appender` element, whose :code:`name` attribute is :code:`MaxBackupIndex`) | The maximum number of log files which will be backed up. For example, if it is set to 10, the maximum number of backed up log files will be 10 and their filenames will be :file:`xxx.log.1`, :file:`xxx.log.2`, … :file:`xxx.log.10`.                                                                                           |
+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/log4j/appender/layout/param[@name='ConversionPattern']/@value`                                                                                                                                              | The pattern used in writing out the log file.                                                                                                                                                                                                                                                                                    |
+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Connections to Message Database
"""""""""""""""""""""""""""""""

.. code-block:: xml

   <module>
   …
   <component id="daofactory" name="System DAO Factory">
   <class>
   hk.hku.cecid.piazza.commons.dao.ds.SimpleDSDAOFactory
   </class>
     <parameter name="driver" value="org.postgresql.Driver" />
     <parameter name="url" 
                value="jdbc:postgresql://localhost:5432/ebms" />
     <parameter name="username" value="corvus" />
     <parameter name="password" value="corvus" />
       <parameter name="pooling" value="true" />
       <parameter name="maxActive" value="20" />
       <parameter name="maxIdle" value="10" />
       <parameter name="maxWait" value="-1" />
     <parameter name="config">
             hk/hku/cecid/ebms/spa/conf/DAOMessage.xml,
             hk/hku/cecid/ebms/spa/conf/DAORepository.xml,
             hk/hku/cecid/ebms/spa/conf/DAOOutbox.xml,
             hk/hku/cecid/ebms/spa/conf/DAOInbox.xml,
             hk/hku/cecid/ebms/spa/conf/DAOMessageServer.xml,
             hk/hku/cecid/ebms/spa/conf/DAOPartnership.xml
      </parameter>
   </component>
   …
   </module>

+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Element / Attribute                                                                      | Expected information                                                                                                                                                                                                                                                               |
+==========================================================================================+====================================================================================================================================================================================================================================================================================+
| :code:`/module/component[@id='daofactory']/class`                                        | The java class to use in establishing database connection, you can select from                                                                                                                                                                                                     |
|                                                                                          |                                                                                                                                                                                                                                                                                    |
|                                                                                          | * :code:`hk.hku.cecid.piazza.commons.dao.ds.SimpleDSDAOFactory`, if you want AS2 to manage the database connection pool.                                                                                                                                                           |
|                                                                                          | * :code:`hk.hku.cecid.piazza.commons.dao.ds.DataSourceDAOFactory`, if you want the application server manages the database connection pool, which is accessible through JNDI (Java Naming and Directory Interface) name.                                                           |
+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Belows are fields you need to fill in if you are using SimpleDSDAOFactory                                                                                                                                                                                                                                                                                                     |
+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='driver']/@value`    | The JDBC driver that should be used, we have provided the driver for postgres by default. You should put the driver to your :file:`{[Tomcat Home]}/webapps/corvus/WEB-INF/lib`, where we suppose the web application repository is configured as :file:`{[Tomcat Home]}/webapps`.  |
+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='url']/@value`       | The URL in establishing the database connection, please refer to the document of the JDBC driver for the syntax. For PostgreSQL datatabse, the syntax is :code:`jdbc:postgresql://<IP or hostname of the database>/<message database name for AS2>`                                |
+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='username']/@value`  | The username to connect to the database.                                                                                                                                                                                                                                           |
+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='password']/@value`  | The password for the username specified.                                                                                                                                                                                                                                           |
+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='pooling']/@value`   | The boolean value (:literal:`true`/:literal:`false`) specifying if connection pooling should be used.                                                                                                                                                                              |
+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='maxActive']/@value` | The maximum number of active threads.                                                                                                                                                                                                                                              |
+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='maxIdle']/@value`   | The maximum number of threads that can remains idle.                                                                                                                                                                                                                               |
+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='maxWait']/@value`   | The maximum number of milliseconds that the pool will wait (when there are no available connections) for a connection to be returned before throwing an exception, or :literal:`-1` to wait indefinitely.                                                                          |
+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='daofactory']/` :code:`parameter[@name='config']/@value`    | Additional configuration files that will be used by the plug-in. You should just leave it as is.                                                                                                                                                                                   |
+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Belows are fields you need to fill in if you are using DataSourceDAOFactory                                                                                                                                                                                                                                                                                                   |
+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| datasource                                                                               | The JNDI name of the Data Source for connecting the message database, e.g. :code:`java:/comp/env/jdbc/ebmsdb`                                                                                                                                                                      |
+------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Location of Keystore for Digital Signature on Outgoing Messages
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

.. code-block:: xml

   <module id="ebms.main" name="Ebms Plugin" version="1.0">
   …
   <component id="keystore-manager" name="Key Store Manager for Digital Signature">
     <class>hk.hku.cecid.piazza.commons.security.KeyStoreManager</class>
     <parameter name="keystore-location" value="ebms.p12"/>
     <parameter name="keystore-password" value="password"/>
     <parameter name="key-alias" value="CorvusEbMS"/>
     <parameter name="key-password" value="password"/>
     <parameter name="keystore-type" value="PKCS12"/>
     <parameter name="keystore-provider" 
                value="org.bouncycastle.jce.provider.BouncyCastleProvider"/>
     </component>
   …
   </module>

+-----------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| Element / Attribute                                                                           | Expected information                                                                      |
+===============================================================================================+===========================================================================================+
| :code:`/module/component[@id='keystore-manager']/parameter[@name='keystore-location']/@value` | The path of the keystore for signing outgoing messages.                                   |
+-----------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='keystore-manager']/parameter[@name='keystore-password']/@value` | The password for accessing the keystore.                                                  |
+-----------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='keystore-manager]/parameter[@name='key-alias']/@value`          | The alias of the private key for digital signature.                                       |
+-----------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='keystore-manager]/parameter[@name='key-password']/@value`       | The password protecting the private key for digital signature.                            |
+-----------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='keystore-manager]/parameter[@name='keystore-type']/@value`      | The keystore format of the keystore. It is either :literal:`PKCS12` or :literal:`JKS`.    |
+-----------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+

Location of Keystore for S/MIME Decryption (for Incoming Messages)
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

.. code-block:: xml

   <module id="ebms.main" name="Ebms Plugin" version="1.0">
   …
     <component id="keystore-manager-for-decryption" name="Key Store Manager for Decryption">
       <class>hk.hku.cecid.piazza.commons.security.KeyStoreManager</class>
       <parameter name="keystore-location" 
                  value="C:/Program Files/hermes2_ee/plugins/hk.hku.cecid.ebms/security/ebms.p12"/>
       <parameter name="keystore-password" value="password"/>
       <parameter name="key-alias" value="CorvusEbMS"/>
       <parameter name="key-password" value="password"/>
       <parameter name="keystore-type" value="PKCS12"/>
       <parameter name="keystore-provider" value="org.bouncycastle.jce.provider.BouncyCastleProvider"/>
     </component>
   …
   </module>


+-----------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| Element / Attribute                                                                           | Expected information                                                                      |
+===============================================================================================+===========================================================================================+
| :code:`/module/component[@id='keystore-manager']/parameter[@name='keystore-location']/@value` | The path of the keystore for decrypting incoming messages encrypted by S/MIME encryption. |
+-----------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='keystore-manager']/parameter[@name='keystore-password']/@value` | The password for accessing the keystore.                                                  |
+-----------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='keystore-manager]/parameter[@name='key-alias']/@value`          | The alias of the private key for the decryption.                                          |
+-----------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='keystore-manager]/parameter[@name='key-password']/@value`       | The password protecting the private key for digital signature.                            |
+-----------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+
| :code:`/module/component[@id='keystore-manager]/parameter[@name='keystore-type']/@value`      | The keystore format of the keystore. It is either :literal:`PKCS12` or :literal:`JKS`.    |
+-----------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------+


References
----------

* Hermes 2 Application Development Guide
* Hermes 2 Technical Guide
* Hermes 2 Administration Tool User Guide
* Hermes 2 Enterprise Edition Installation Guide
* Hermes 2 GPL Edition Installation Guide
* Hermes 2 Plug-in Development Guide
* OASIS ebXML Message Service Specification 2.0
* MIME-based Secure Peer-to-Peer Business Data Interchange over the Internet Using HTTP AS2 (:file:`draft-ietf-ediint-as2-17.txt`)
