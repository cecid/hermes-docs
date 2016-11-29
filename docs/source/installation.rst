.. _installation:

Hermes 2 Installation Guide
===========================

Version 0.9
28/11/2016

3.Procedures
------------
This document is to describe how to install and run open-source business-to-business messaging gateway Hermes 2.0 (codenamed Corvus).

3.1. Introduction
^^^^^^^^^^^^^^^^^

The application is packaged in the form of a self-extracted java archive (JAR). Upon proper invocation, you will see an installation wizard, either in graphical or text format. Following through the steps will have the following components installed,

* Hermes 2 Core
* Hermes 2 plugins
* Database tables of Hermes 2 plugins for either one of the following database:

  * Postgres 8.0 or later
  * Oracle 9i or later
  * MySQL 5.0 or later with InnoDB storage engine supported
* Web service usage sample


3.2. Prerequisite
^^^^^^^^^^^^^^^^^
1. Java 2 SDK version 5.0 or above 
2. A security patch, Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy Files, is also required for the java cryptography extension. 
3. Tomcat 5.5 or above with port 8080, TOMCAT_HOME is used for referring to the home directory of tomcat in the remaining parts of document.  

  **Note:**  To access the admin page, you will need to have a Tomcat user with an admin role.  One way is to define the user in "**tomcat-users.xml**".  Please refer to the Realm Configuration section in the Tomcat documentation for more details.

  ***Sample:**

  Tomcat-user.xml

  .. code-block:: xml

      <?xml version='1.0' encoding='utf-8'?>
      <tomcat-users>
        <role rolename="tomcat"/>
        <role rolename="admin"/>
        <user username="corvus" password="corvus" roles="tomcat,admin"/>
      </tomcat-users>



4. One of the following database installed on any server:

  * PostgreSQL 8.0 or later, POSTGRES_HOME is referring to the home directory of PostgreSQL in the remaining parts of the document.
  * MySQL 5.0 or later, MYSQL_HOME is referring to the home directory of MySQL in the remaining parts of the document.
  * Oracle 9i or later, ORACLE_HOME is referring to the home directory of Oracle in the remaining parts of the document.

3.3. Step 1 – Environment setup
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Install all the prerequisite items. It is assumed that they are all running on the same machine in the rest of this guide.

3.4. Step 2 – Configuration
^^^^^^^^^^^^^^^^^^^^^^^^^^^
3.4.1 Database
""""""""""""""

* Postgres


1 Create database user with username "corvus" and password "corvus".

  1.1 Open a command prompt
  
  1.2 Go to POSTGRES_HOME/bin
  
  1.3 Type "**createuser -A -d -P -U <postgres_admin>**" where <postgres_admin> representing the name of administrator / super-user in PostgreSQL database. This value is "**postgres**" if not specified. It may require super user or Postgres owner to execute in Linux.
  
  1.4 Create a user named "**corvus**"
  
  1.5 Enter the password "**corvus**"
  
  1.6 Enter the password again for confirmation
  
  1.7 Enter "n" for question "Shall the new role be allowed to create more new roles?"
  
  1.8 Enter the PostgreSQL administrator password for creating a new user role.

2 Create two databases named "**as2**" and "**ebms**" with "**corvus**" user

  2.1 Open a command prompt
  
  2.2 Go to POSTGRES_HOME/bin
  
  2.3 Type "**createdb –U corvus –W as2**"
  
  2.4 Enter the password "**corvus**"
  
  2.5 Repeat 2.3 - 2.4 for ebms database.

* MySQL

1 Create two database named "**as2**" and "**ebms**" with username "**corvus**" and password "**corvus**".

  1.1 Open a command prompt
  
  1.2 Go to MYSQL_HOME/bin
  
  1.3 Type "**mysql –u <mysql_admin> -p**" where <mysql_admin> representing the name of administrator / super-user in mySQL database. This is "**root**" by default. It may require super user or mySQL owner to execute in Linux.
  
  1.4 Enter command below to create as2 database. Notice that specifying collate to "latin1_general_cs" is essential.
  
  **create database as2 collate=latin1_general_cs;**
  
  1.5 Enter command below to create and assign access privileges to user "**corvus**".
  
  **grant all on as2.* to 'corvus'@'localhost' identified by 'corvus';**
  
  1.6 Repeat 1.4 – 1.5 for ebMS database.

* Oracle

For Oracle database creation, since it involve a number of steps and custom parameters for different requirement for the database server. We propose the following reference for the guideline of creating an Oracle database for Hermes 2:

http://www.peacetech.com/flipper/oracle9i/901_doc/server.901/a90117/create.htm

Step 3 – Hermes 2 Deployment

  1. In Windows platform, open a command prompt and type "**java –jar hermes2_installer.jar**" or if java is not set in your environment path, specify the full path.
  
  2. In Unix/Linux platform, open **xterm** and follow the same procedure as above.
  
  **OR**
  
  3. In Windows platform, you can execute by double-click or right-click on the .jar file and selecting "**open with**" and choosing **javaw** (located where you installed java, in the bin folder).

  .. image:: _static/images/hermes-2-0-opensource-installer.gif
  
  4. Click **next** until you get to Step 1 of the installation.

  5. Step 1 - Configure Hermes 2 Core:

  .. image:: _static/images/step-1-configure-hermes-2-core.gif
  .. image:: _static/images/step-1-h2o-installer.gif

  Setting description

  +-----------------------------------+-------------------------------------------------------------------+
  | **Web Application Folder Folder** | Folder to place the web application(e.g *webapps*) in Tomcat      |
  +-----------------------------------+-------------------------------------------------------------------+
  | **Hermes 2 Home**                 | Location to place the Hermes 2 core library and some related files|
  +-----------------------------------+-------------------------------------------------------------------+
  | **JDBC Driver**                   | Specify which database vendor to connect to                       |
  |                                   | One of these 3 database vendor can be chosen:                     |
  |                                   |                                                                   | 
  |                                   | * Postgres                                                        |
  |                                   | * Oracle                                                          |
  |                                   | * MySQL                                                           |
  +-----------------------------------+-------------------------------------------------------------------+
  | **Hermes 2 ebMS Plugin**          | Whether to install the ebMS conponent                             |
  +-----------------------------------+-------------------------------------------------------------------+
  | **Hermes 2 AS2 Plugin**           | Whether to install the AS2 component                              |
  +-----------------------------------+-------------------------------------------------------------------+
  | **Web Service Usage Sample**      | Whether to install the sample program of web service client       |
  +-----------------------------------+-------------------------------------------------------------------+

  6. Click **next** and press **yes** if the installer prompts you to create a new directory.

  7. Step 2 - Configure Database for ebMS Plugin (Optional)
  
  .. image:: _static/images/step-2-configure-database-for-ebms-plugin.gif
  .. image:: _static/images/step-2-h2o-installer.gif


  Setting description



+-------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Database URL      | The URL address of the database server located. Port number may attached to the address as the format <host_address>:<port> where <host_address> is the address of the database server and <port > is the port number of the database server address |
+-------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Database Name/SID | For Postgres and MySQL, please specify the name of the database. For Oracle, please specify the Oracle System ID (SID)                                                                                                                               |
+-------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Username          | Username to access database                                                                                                                                                                                                                          |
+-------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Password          | Password to access database                                                                                                                                                                                                                          |
+-------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Re-create Tables  | Whether to re-create all the table in the specified database **Important Notes:** If this is your first **time to install hermes**, please check this option. If choose to re-create the tables, all of the existing data in the specified database  |
|                   | will remove at the later step of installation. Please backup all the data on the selected database before choose to re-create tables.                                                                                                                |
+-------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+








  8. If you followed the prerequisite install procedures from above, you can just leave it as the default.

  9. Then click **next**.

  10. If AS2 Plugin was not selected, click **next** and then click on **install** and you’re done!

  11. Step 3 - Configure Database for AS2 Plugin (Optional)

  .. image:: _static/images/step-3-configure-database-for-as2-plugin.gif
  .. image:: _static/images/step-3-h2o-installer.gif

  Setting description


  Setting description

+---------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Database URL        | The URL address of the database server located. Port number may attached to the address as the format <host_address>:<port> where <host_address> is the address of the database server and <port> is the port number of the database server address |
+---------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Database Name / SID | For Postgres and MySQL, please specify the name of the database. For Oracle, please specify the Oracle System ID (SID)                                                                                                                              |
+---------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Username            | Username to access database                                                                                                                                                                                                                         |
+---------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Password            | Password to access database                                                                                                                                                                                                                         |
+---------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| AS2 Plugin          | AS2: Original AS2 plugin certified by Drummond Group Inc.                                                                                                                                                                                           |
+---------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
|                     | AS2 Plus: Built based on AS2 plugin with new/enhanced features.                                                                                                                                                                                     |
+---------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Re-create Tables    | Whether to re-create all the table in the specified database Important Notes: If this is your first time to install hermes, pleas check this option. If you purposely switch your plugin from AS2 to AS2 Plus, or versus. We highly recommend you   |
|                     | checked this option. If choose to re-create the tables, all of the existing data on the specified database will remove at the later step of installation. Please backup all the data on the selected database before choose to re-create tables.    |
+---------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

  12. If you followed the prerequisite install procedures from above, you can just leave it as the default.

  13. Then click **next** and then click on **install** and you’re done!




3.5. Step 4 – Start Hermes 2
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Check list:**

1. Java 2 SDK 5.0 or above with Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy Files 5.0.

2. Apache Tomcat 5.5 or above Servlet/JSP Container

3. Database server is running with ebMS/AS2 database instance and tables created.

4. If you are running Unix/Linux, make sure that at least read permissions are set to the core directory and read/write for AS2 repository directory in Hermes 2 Home.

5. Start Tomcat.

6. To verify Hermes 2 is running, access the following URL from browser.

**http://localhost:8080/corvus/home**

Welcome page should be displayed as below:

.. image:: _static/images/step-4-welcome-page.gif

7. To access the admin page, go to the following URL. The login user and password is the same as the Tomcat user with admin privileges specified in Section 3.2.

**http://localhost:8080/corvus/admin/home**

8. Once you have gained access to the admin page, you should see the Hermes 2 Administration Console page like this:

.. image:: _static/images/step-4-administration-console-page.gif

That’s it! Your Hermes 2 should now be up and running. You can test your setup by running our web service usage sample in Section!.


4. Partnership Maintenance and Web Service Usage Sample
-------------------------------------------------------

A tool kit called **Web Service Usage Sample** was installed under Hermes 2, “<HERMES2_HOME>/sample” folder. It contains tools to test the installed Hermes, demonstrate messaging flow and provided a set of sample code for user to write web service client application to connect to the Hermes 2.

4.1. Directory Organization
^^^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
| Directory/ File |  Description                                                                                                                                  |
+===========+=====================================================================================================================================================+
| config/*  | Contains the configuration file for the sample programs. The folders inside this directory contain related files for specific sample program.       |
+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
| config/   | These two files contain the setting of the partnership for ebMS and AS2 commonly used by sample programs.                                           |
| ebms- par |                                                                                                                                                     |
| tnership. |                                                                                                                                                     |
| xml and   |                                                                                                                                                     |
| as2- part |                                                                                                                                                     |
| nership.x |                                                                                                                                                     |
| ml        |                                                                                                                                                     |
+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
| logs/*    | A set of logs contains the output from each sample program.                                                                                         |
+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
| lib/*     | The library files required for the sample programs.                                                                                                 |
+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
| *.bat /   | The scripts for executing the sample programs.                                                                                                      |
| *.sh      |                                                                                                                                                     |
+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------+

4.2. Preparation
^^^^^^^^^^^^^^^^

4.2.1. Windows environment
""""""""""""""""""""""""""

1. Set environment variable **JAVA_HOME** to the directory installed the java.

4.2.2. UNIX environment
"""""""""""""""""""""""

1. Set environment variable **JAVA_HOME** to the directory installed the java.

2. Change the permission of all shell-script files to 755 by following command.

**chown 755 *.sh**

4.3. Partnership Maintenance
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Users need to define a "**Partnership**", which contains the relationship of messaging in transport level between a sender and a recipient. It is required to specify the "**Partnership**" in sender the recipient.

A web service sample program is provided to manage "Partnership" (to add, update or delete). Partnership configuration for AS2/ebMS loopback test is placed in *<HERMES2_HOME>/sample/config*/as2(ebms)-partnership.xml.

4.3.1. Creating AS2 Partnership
"""""""""""""""""""""""""""""""

To create the partnership required to perform the AS2 messaging loopback test using Web Service Usage Sample in next step, you just need to execute the following command.

    as2-partnership

**OR**

Access http://localhost:8080/corvus/admin/as2/partnership to configure the partnership manually. Below is a simple loop-back configuration sample.

.. image:: _static/images/4-3-1-create-as2-partnership.gif


+------------------------------------------------------------------+------------------------------------------------+
| Partnership ID                                                   | as2-loopback                                   |
+------------------------------------------------------------------+------------------------------------------------+
| **AS2 From**                                                     | as2loopback                                    |
+------------------------------------------------------------------+------------------------------------------------+
| **AS2 To**                                                       | as2loopback                                    |
+------------------------------------------------------------------+------------------------------------------------+
| Disabled                                                         | No                                             |
+------------------------------------------------------------------+------------------------------------------------+
| Subject                                                          |                                                |
+------------------------------------------------------------------+------------------------------------------------+
| Recipient Address                                                | http://127.0.0.1:8080/corvus/httpd/as2/inbound |
+------------------------------------------------------------------+------------------------------------------------+
| Hostname Verified in SSL?                                        | No                                             |
+------------------------------------------------------------------+------------------------------------------------+
| Request Receipt?                                                 | No                                             |
+------------------------------------------------------------------+------------------------------------------------+
| Signed Receipt?                                                  | No                                             |
+------------------------------------------------------------------+------------------------------------------------+
| Asynchronous Receipt?                                            | No                                             |
+------------------------------------------------------------------+------------------------------------------------+
| Receipt Return URL                                               | http://127.0.0.1:8080/corvus/httpd/as2/inbound |
+------------------------------------------------------------------+------------------------------------------------+
| Message Compression Required?                                    | No                                             |
+------------------------------------------------------------------+------------------------------------------------+
| Message Signing Required?                                        | No                                             |
+------------------------------------------------------------------+------------------------------------------------+
| Signing Algorithm                                                | sha1                                           |
+------------------------------------------------------------------+------------------------------------------------+
| Message Encryption Required?                                     | No                                             |
+------------------------------------------------------------------+------------------------------------------------+
| Encryption Algorithm                                             | rc1                                            |
+------------------------------------------------------------------+------------------------------------------------+
| Certificate For Encryption                                       | none                                           |
+------------------------------------------------------------------+------------------------------------------------+
| MIC Algorithm                                                    | sha1                                           |
+------------------------------------------------------------------+------------------------------------------------+
| Maximum Retries                                                  | 1                                              |
+------------------------------------------------------------------+------------------------------------------------+
| Retry Interval (ms)                                              | 30000                                          |
+------------------------------------------------------------------+------------------------------------------------+
| Message Signature Enforced?                                      | No                                             |
+------------------------------------------------------------------+------------------------------------------------+
| Message Encryption Enforced?                                     | No                                             |
+------------------------------------------------------------------+------------------------------------------------+
| Certificate For Verification                                     | none                                           |
+------------------------------------------------------------------+------------------------------------------------+

4.3.2. Creating AS2 Plus Partnership
""""""""""""""""""""""""""""""""""""

Please reference the procedures of partnership.

4.3.3. Creating ebMS Partnership
""""""""""""""""""""""""""""""""

To create the partnership required to perform the ebMS messaging loopback test using Web Service Usage Sample in next step, you need to execute the following command.

**OR**

Access http://localhost:8080/corvus/admin/ebms/partnership to configure the partnership manually. Below is a simple loop-back configuration sample.

+----------------------------------+-------------------------------------------------+
| Partnership ID                   | ebms-loopback                                   |
+----------------------------------+-------------------------------------------------+
| CPA ID                           | cpaid                                           |
+----------------------------------+-------------------------------------------------+
| Service                          | http://localhost:8080/corvus/httpd/ebms/inbound |
+----------------------------------+-------------------------------------------------+
| Action                           | Action                                          |
+----------------------------------+-------------------------------------------------+
| Disabled                         | No                                              |
+----------------------------------+-------------------------------------------------+
| Transport Endpoint               | http://localhost:8080/corvus/httpd/ebms/inbound |
+----------------------------------+-------------------------------------------------+
| Hostname Verified in SSL?        | No                                              |
+----------------------------------+-------------------------------------------------+
| Sync Reply Mode                  | none                                            |
+----------------------------------+-------------------------------------------------+
| Acknowledgement Requested        | never                                           |
+----------------------------------+-------------------------------------------------+
| Acknowledgement Signed Requested | never                                           |
+----------------------------------+-------------------------------------------------+
| Duplicate Elimination            | never                                           |
+----------------------------------+-------------------------------------------------+
| Message Order                    | NotGuaranteed                                   |
+----------------------------------+-------------------------------------------------+
| Signing Required?                | No                                              |
+----------------------------------+-------------------------------------------------+
| Encryption Required? (Mail Only) | No                                              |
+----------------------------------+-------------------------------------------------+
| Certificate For Encryption       | none                                            |
+----------------------------------+-------------------------------------------------+
| Maximum Retries                  | 1                                               |
+----------------------------------+-------------------------------------------------+
| Retry Interval (ms)              | 30000                                           |
+----------------------------------+-------------------------------------------------+
| Certificate For Verification     | none                                            |
+----------------------------------+-------------------------------------------------+

4.4. Web Service Usage Sample Flow
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In order to validate the installation of Hermes 2, a web service usage sample program is provided. It can be simply executed by running the following command in a command prompt.

In order to test whether the Hermes 2 are installed success or not, we suggest to run sample programs in following steps:

1. Add a partnership by running **ebms-partnership / as2-partnership**.

2. Send message to the local Hermes 2 by running **ebms-send / as2-send**.

3. Check the status of sent message by running **ebms-history / as2-history** and select the message from outbox.

4. Check the received message by running **ebms-history / as2-history** and select the message from inbox, download the payload.

4.4.1. AS2 Web Service Usage Sample
"""""""""""""""""""""""""""""""""""

You are required to execute section 4.3.1 successfully before executing the following AS2 web service usage sample. Next we illustrate the steps to run the test described in section 4.4
