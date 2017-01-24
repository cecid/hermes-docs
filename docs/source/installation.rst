Hermes 2 Installation Guide
===========================

© CECID

Produced by the Center for E-Commerce Infrastructure Development at The University of Hong Kong.

The contents of this document remain the property of and may not be reproduced in whole or in part without the express permission of CECID.


Objectives of the Document
--------------------------
This document describes how to install and run the open source business-to-business messaging gateway Hermes 2.0 (codenamed Corvus).

Introduction
------------

The application is packaged in the form of a self-extracted java archive (JAR). Upon proper invocation, you will see an installation wizard, either in graphical or text format. Following the steps will install the following components:

* Hermes 2 core
* Hermes 2 plugins
* Database tables of Hermes 2 plugins for one of the following database:
  
  * Postgres 8.0 or later
  * Oracle 9i or later
  * MySQL 5.0 or later with InnoDB storage engine supported

* Web service usage sample


Prerequisite
------------
1. Java SE Development Kit 8
#. Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy Files 

   a. Download the JCE Unlimited Strength Jurisdiction Policy Files for JDK 8 from 

      http://www.oracle.com/technetwork/java/javase/downloads/jce8-download-2133166.html

   #. Unzip the downloaded file

      .. code:: sh

         unzip jce_policy-8.zip
      
   #. Replace the two jar files :file:`local_policy.jar` and :file:`US_export_policy.jar` in the directory :file:`/usr/lib/jvm/java-8-oracle/jre/lib/security` with the corresponding jar file unzipped in the previous step.

      .. code:: sh

         cd UnlimitedJCEPolicyJDK8
         sudo cp local_policy.jar /usr/lib/jvm/java-8-oracle/jre/lib/security/local_policy.jar
         sudo cp US_export_policy.jar /usr/lib/jvm/java-8-oracle/jre/lib/security/US_export_policy.jar

#. Tomcat 5.5 or above with port :literal:`8080` 

   a. Change the access permissions, the owner and the group of :file:`{<TOMCAT_HOME>}/webapps` after Tomcat is installed.

      .. code:: sh

         sudo chmod 775 <TOMCAT_HOME>/webapps
         sudo chown tomcat:cecid <TOMCAT_HOME>/webapps

   #. Edit :file:`/etc/systemd/system/tomcat.service`. Change :envvar:`Environment=JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-amd64/jre` to :envvar:`Environment=JAVA_HOME=/usr/lib/jvm/java-8-oracle/jre`
   #. Restart Tomcat

   **Note:**  To access the admin page, you will need to have a Tomcat user with an admin role.  One way to do this is to define the user in :file:`tomcat-users.xml`.  Please refer to the Realm Configuration section in the Tomcat documentation for more details.

   Sample of :file:`tomcat-user.xml`:

   .. code-block:: xml

      <?xml version='1.0' encoding='utf-8'?>
      <tomcat-users>
        <role rolename="tomcat"/>
        <role rolename="admin"/>
        <user username="corvus" password="corvus" roles="tomcat,admin"/>
      </tomcat-users>

#. One of the following databases installed on any server:

   * PostgreSQL 8.0 or later. :file:`{<POSTGRES_HOME>}` is referring to the home directory of PostgreSQL in the remaining parts of the document.
   * MySQL 5.0 or later. :file:`{<MYSQL_HOME>}` is referring to the home directory of MySQL in the remaining parts of the document.
   * Oracle 9i or later. :file:`{<ORACLE_HOME>}` is referring to the home directory of Oracle in the remaining parts of the document.

Installation
------------
Step 1 – Environment setup
^^^^^^^^^^^^^^^^^^^^^^^^^^
Install all the prerequisite items. The rest of this guide assumes that they are all running on the same machine.

Step 2 – Configuration
^^^^^^^^^^^^^^^^^^^^^^
Databases
"""""""""

Postgres
''''''''

#. Create a database user with username :literal:`corvus` and password :literal:`corvus`.

   a. Open a command prompt
   #. Go to :file:`{<POSTGRES_HOME>}/bin`
   #. Type :samp:`createuser -A -d -P -U {<POSTGRES_ADMIN>} corvus` where :samp:`{<POSTGRES_ADMIN>}` represents the name of an administrator/super-user in the PostgreSQL database. This value is :literal:`postgres` if not specified. This may require a super user or Postgres owner to execute in Linux.
   #. Enter the password :literal:`corvus`
   #. Enter the password again for confirmation
   #. Enter the PostgreSQL administrator password for creating a new user role.

#. Create two databases named :literal:`as2` and :literal:`ebms` with the :literal:`corvus` user

  a. Open a command prompt
  #. Go to :file:`{<POSTGRES_HOME>}/bin`
  #. Type :samp:`createdb –U corvus –W as2`
  #. Enter the password :literal:`corvus`
  #. Repeat steps 2.3 - 2.4 for the :literal:`ebms` database.

MySQL
'''''

1. Create two databases named :literal:`as2` and :literal:`ebms` with username :literal:`corvus` and password :literal:`corvus`.

  a. Open a command prompt
  #. Go to :file:`{<MYSQL_HOME>}/bin`
  #. Type :samp:`mysql –u {<MYSQL_ADMIN>} -p` where :samp:`{<MYSQL_ADMIN>}` represents the name of an administrator/super-user in the MySQL database. This is ``root`` by default. This may require super user or MySQL owner to execute in Linux.
  #. Enter the command below to create the :literal:`as2` database. Note that specifying collate to :literal:`latin1_general_cs` is essential.
    
     .. code-block:: sql

        create database as2 collate=latin1_general_cs;
     
  #. Enter the command below to create and assign access privileges to user :literal:`corvus`. 

     .. code-block:: sql

        grant all on as2.* to 'corvus'@'localhost' identified by 'corvus';
     
  #. Repeat steps 1.4 – 1.5 for the :literal:`ebms` database.

Oracle
''''''

Oracle database creation involves a number of steps and custom parameters for different requirements for the database server. We propose the following reference as a guideline for creating an Oracle database for Hermes 2:

https://docs.oracle.com/cd/E11882_01/server.112/e10897/install.htm#ADMQS0232

Step 3 – Hermes 2 Deployment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

  1. Execute the installer.

     * For Windows, open a command prompt and type :samp:`java –jar hermes2_installer.jar` or if :program:`java` is not set in your environment path, specify the full path.
     * For Unix/Linux, open :program:`xterm` and follow the same procedure as above.

     **Or:**

     * For Windows, you can execute the installer by double-clicking on the :file:`.jar` file or right-clicking and selecting :menuselection:`open with --> javaw` (located where you installed java, in the :file:`bin` folder).
     
     .. image:: /_static/images/3-4-1-hermes-2-0-text-installer.png
     .. image:: /_static/images/3-4-1-hermes-2-0-opensource-installer.png

     Click :guilabel:`Next` until you get to Step 1 of the installation.
  #. Step 1 - Configure Hermes 2 Core:

     .. image:: /_static/images/3-4-1-step-1-configure-hermes-2-core.png
     .. image:: /_static/images/3-4-1-step-1-h2o-installer.png

     Descriptions of the settings:

     +-----------------------------------+---------------------------------------------------------------------+
     | Web Application Folder            | Folder to place the web application (e.g :file:`webapps`) in Tomcat.|
     +-----------------------------------+---------------------------------------------------------------------+
     | Hermes 2 Home                     | Location to place the Hermes 2 core library and some related files. |
     +-----------------------------------+---------------------------------------------------------------------+
     | JDBC Driver                       | Specify which database vendor to connect to.                        |
     |                                   | One of the following 3 database vendors can be selected:            |
     |                                   |                                                                     | 
     |                                   |   * Postgres                                                        |
     |                                   |   * Oracle                                                          |
     |                                   |   * MySQL                                                           |
     +-----------------------------------+---------------------------------------------------------------------+
     | Hermes 2 ebMS Plugin              | Optional. Install the ebMS component.                               |
     +-----------------------------------+---------------------------------------------------------------------+
     | Hermes 2 AS2 Plugin               | Optional. Install the AS2 component.                                |
     +-----------------------------------+---------------------------------------------------------------------+
     | Web Service Usage Sample          | Optional. Install the sample program of web service client.         |
     +-----------------------------------+---------------------------------------------------------------------+

     Click :guilabel:`Next` and press :guilabel:`Yes` if the installer prompts you to create a new directory.

  #. Step 2 - Configure Database for ebMS Plugin (Optional)
  
     .. image:: /_static/images/3-4-1-step-2-configure-database-for-ebms-plugin.png
     .. image:: /_static/images/3-4-1-step-2-h2o-installer.png


     Descriptions of the settings:
     
     +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
     | Database URL      | The URL address of the database server. Port number may be attached to the address with the format :samp:`{<HOST_ADDRESS>}:{<PORT>}` where            |
     |                   | :samp:`{<HOST_ADDRESS>}` is the address of the database server and :samp:`{<PORT>}` is the port number of the database server address.                |
     +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
     | Database Name/SID | For Postgres and MySQL, please specify the name of the database. For Oracle, please specify the Oracle System ID (SID).                               |
     +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
     | Username          | Username to access the database.                                                                                                                      |
     +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
     | Password          | Password to access the database.                                                                                                                      |
     +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
     | Re-create Tables  | Optional. Re-create all the tables in the specified database.                                                                                         |
     |                   |                                                                                                                                                       |
     |                   | **Important Notes:**                                                                                                                                  |
     |                   |                                                                                                                                                       |
     |                   | * If this is your **first time** installing Hermes 2, please check this option.                                                                       |
     |                   |                                                                                                                                                       |
     |                   | * If you choose to re-create the tables, all of the existing data in the specified database will be removed during installation.                      |
     |                   |   Please backup all the data in the selected database before choosing to re-create the tables.                                                        |
     +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+

     If you followed the prerequisite installation procedures above, you can just leave it as the default. Click :guilabel:`Next` when you have finished the configuration.

  #. Step 3 - Configure Database for AS2 Plugin (Optional)

     .. image:: /_static/images/3-4-1-step-3-configure-database-for-as2-plugin.png
     .. image:: /_static/images/3-4-1-step-3-h2o-installer.png

     Descriptions of the settings:

     +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
     | Database URL      | The URL address of the database server. Port number may be attached to the address with the format :samp:`{<HOST_ADDRESS>}:{<PORT>}` where            |
     |                   | :samp:`{<HOST_ADDRESS>}` is the address of the database server and :samp:`{<PORT>}` is the port number of the database server address.                |
     +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
     | Database Name/SID | For Postgres and MySQL, please specify the name of the database. For Oracle, please specify the Oracle System ID (SID).                               |
     +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
     | Username          | Username to access the database.                                                                                                                      |
     +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
     | Password          | Password to access the database.                                                                                                                      |
     +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
     | AS2 Plugin        | **AS2:** Original AS2 plugin certified by Drummond Group Inc.                                                                                         |
     |                   |                                                                                                                                                       |
     |                   | **AS2 Plus:** Built based on AS2 plugin with new/enhanced features.                                                                                   |
     +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+
     | Re-create Tables  | Optional. Re-create all the tables in the specified database.                                                                                         |
     |                   |                                                                                                                                                       |
     |                   | **Important Notes:**                                                                                                                                  |
     |                   |                                                                                                                                                       |
     |                   | * If this is your **first time** installing Hermes 2, please check this option.                                                                       |
     |                   |                                                                                                                                                       |
     |                   | * If you are switching from AS2 to AS2 Plus or vice versa, we highly recommend you check this option.                                                 |
     |                   |                                                                                                                                                       |
     |                   | * If you choose to re-create the tables, all of the existing data in the specified database will be removed during installation.                      |
     |                   |   Please backup all the data in the selected database before choosing to re-create the tables.                                                        |
     +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+

     If you followed the prerequisite installation procedures above, you can just leave it as the default. Click :guilabel:`Next` when you have finished the configuration.

  #. Click on :guilabel:`Install` and you're done!

Step 4 – Start Hermes 2
^^^^^^^^^^^^^^^^^^^^^^^

#. Checklist:

   * Java 2 SDK 5.0 or above with Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy Files 5.0.
   * Apache Tomcat 5.5 or above Servlet/JSP Container.
   * Database server is running with ebMS and/or AS2 database instances and the tables are created.
   * If you are running Unix/Linux, make sure that at least read permissions are set to the core directory and read/write for the AS2 repository directory in :file:`{<HERMES2_HOME>}`.
   * Start Tomcat.

#. To verify that Hermes 2 is running, access the following URL from a web browser:

     http://localhost:8080/corvus/home

   The welcome page should be displayed as below:

   .. image:: /_static/images/3-5-step-4-welcome-page.jpeg

#. To access the admin page, go to the following URL. The login user and password are the same as the Tomcat user with admin privileges specified in `Prerequisite`_.

    http://localhost:8080/corvus/admin/home

#. Once you have gained access to the admin page, you should see the Hermes 2 Administration Console page:

   .. image:: /_static/images/3-5-step-4-administration-console-page.png

That's it! Your Hermes 2 should now be up and running. You can test your setup by running our web service usage sample in next section.


Partnership Maintenance and Web Service Usage Sample
-------------------------------------------------------

A tool kit called :program:`Web Service Usage Sample` was installed under the :file:`{<HERMES2_HOME>}/sample` folder. It contains tools to test the installed Hermes 2 and demonstrate messaging flow. It provides a set of sample code for writing web service client applications and connect them to Hermes 2.

Directory Organization
^^^^^^^^^^^^^^^^^^^^^^

+---------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
| Directory/File                        | Description                                                                                                                                         |
+=======================================+=====================================================================================================================================================+
| :file:`config/*`                      | Contains the configuration file for the sample programs. The folders inside this directory contain related files for specific sample programs.      |
+---------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
| :file:`config/ebms-partnership.xml`   | These two files contain partnership settings for ebMS and AS2 that are used by the sample programs.                                                 |
| and                                   |                                                                                                                                                     |
| :file:`config/as2-partnership.xml`    |                                                                                                                                                     |
+---------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
| :file:`logs/*`                        | A set of logs that contain the output from each sample program.                                                                                     |
+---------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
| :file:`lib/*`                         | The library files required for the sample programs.                                                                                                 |
+---------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
| :file:`*.bat`/:file:`*.sh`            | The scripts for executing the sample programs.                                                                                                      |
+---------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+

Preparation
^^^^^^^^^^^

Windows environment
"""""""""""""""""""

1. Set environment variable :envvar:`JAVA_HOME` to the directory where Java is located.

UNIX environment
""""""""""""""""

1. Set environment variable :envvar:`JAVA_HOME` to the directory where Java is located.
#. Change the permissions of all shell-script files to :literal:`755` with the following command:
   
   .. code:: sh

      sudo chmod 755 *.sh

#. Change the owner and the group of :file:`{<HERMES2_HOME>}` and :file:`{<TOMCAT_HOME>}/webapps/corvus` with the following commands:

   .. code:: sh

      sudo chown -R tomcat:cecid <HERMES2_HOME>
      sudo chown -R tomcat:cecid <TOMCAT_HOME>/webapps/corvus

Partnership Maintenance
^^^^^^^^^^^^^^^^^^^^^^^

Users need to define a **partnership**, which contains the messaging details between sender and recipient. It is required to identify the sender and the recipient when transporting messages.

A web service sample program is provided to manage partnerships (add, update or delete). The partnership configuration for the AS2/ebMS loopback test is placed in :file:`{<HERMES2_HOME>}/sample/config/{<as2/ebms>}-partnership.xml`.

+------------------------------+----------------------------------------------------------+
| Program                      | Purpose                                                  |
+==============================+==========================================================+
| :program:`as2-partnership` / | Maintains a specified AS2/ebMS partnership in Hermes 2.  |
| :program:`ebms-partnership`  |                                                          |
+------------------------------+----------------------------------------------------------+

Creating an AS2 Partnership
"""""""""""""""""""""""""""

To create the partnership required to perform the AS2 messaging loopback test using `AS2 Web Service Usage Sample`_, you need to execute the script :program:`as2-partnership`.

**Or:**

Access http://localhost:8080/corvus/admin/as2/partnership to configure the partnership manually. Below is a simple loopback configuration sample:

.. image:: /_static/images/4-3-1-create-as2-partnership.png


+-------------------------------+------------------------------------------------+
| Partnership ID                | :literal:`as2-loopback`                        |
+-------------------------------+------------------------------------------------+
| AS2 From                      | :literal:`as2loopback`                         |
+-------------------------------+------------------------------------------------+
| AS2 To                        | :literal:`as2loopback`                         |
+-------------------------------+------------------------------------------------+
| Disabled                      | :guilabel:`No`                                 |
+-------------------------------+------------------------------------------------+
| Subject                       | none                                           |
+-------------------------------+------------------------------------------------+
| Recipient Address             | http://127.0.0.1:8080/corvus/httpd/as2/inbound |
+-------------------------------+------------------------------------------------+
| Hostname Verified in SSL?     | :guilabel:`No`                                 |
+-------------------------------+------------------------------------------------+
| Request Receipt?              | :guilabel:`No`                                 |
+-------------------------------+------------------------------------------------+
| Signed Receipt?               | :guilabel:`No`                                 |
+-------------------------------+------------------------------------------------+
| Asynchronous Receipt?         | :guilabel:`No`                                 |
+-------------------------------+------------------------------------------------+
| Receipt Return URL            | http://127.0.0.1:8080/corvus/httpd/as2/inbound |
+-------------------------------+------------------------------------------------+
| Message Compression Required? | :guilabel:`No`                                 |
+-------------------------------+------------------------------------------------+
| Message Signing Required?     | :guilabel:`No`                                 |
+-------------------------------+------------------------------------------------+
| Signing Algorithm             | :guilabel:`sha1`                               |
+-------------------------------+------------------------------------------------+
| Message Encryption Required?  | :guilabel:`No`                                 |
+-------------------------------+------------------------------------------------+
| Encryption Algorithm          | :guilabel:`rc2`                                |
+-------------------------------+------------------------------------------------+
| Certificate For Encryption    | none                                           |
+-------------------------------+------------------------------------------------+
| MIC Algorithm                 | :guilabel:`sha1`                               |
+-------------------------------+------------------------------------------------+
| Maximum Retries               | :literal:`1`                                   |
+-------------------------------+------------------------------------------------+
| Retry Interval (ms)           | :literal:`30000`                               |
+-------------------------------+------------------------------------------------+
| Message Signature Enforced?   | :guilabel:`No`                                 |
+-------------------------------+------------------------------------------------+
| Message Encryption Enforced?  | :guilabel:`No`                                 |
+-------------------------------+------------------------------------------------+
| Certificate For Verification  | none                                           |
+-------------------------------+------------------------------------------------+

Creating an AS2 Plus Partnership
""""""""""""""""""""""""""""""""

Please follow the procedure in `Creating an AS2 Partnership`_ to create an AS2 Plus partnership.

Creating an ebMS Partnership
""""""""""""""""""""""""""""

To create the partnership required to perform the ebMS messaging loopback test using `ebMS Web Service Usage Sample`_, you need to execute the script :program:`ebms-partnership`.

**Or:**

Access http://localhost:8080/corvus/admin/ebms/partnership to configure the partnership manually. Below is a simple loop-back configuration sample:

  .. image:: /_static/images/4-3-3-ebms-plugin.png

+----------------------------------+-------------------------------------------------+
| Partnership ID                   | :literal:`ebms-loopback`                        |
+----------------------------------+-------------------------------------------------+
| CPA ID                           | :literal:`cpaid`                                |
+----------------------------------+-------------------------------------------------+
| Service                          | http://localhost:8080/corvus/httpd/ebms/inbound |
+----------------------------------+-------------------------------------------------+
| Action                           | :literal:`action`                               |
+----------------------------------+-------------------------------------------------+
| Disabled                         | :guilabel:`No`                                  |
+----------------------------------+-------------------------------------------------+
| Transport Endpoint               | http://localhost:8080/corvus/httpd/ebms/inbound |
+----------------------------------+-------------------------------------------------+
| Hostname Verified in SSL?        | :guilabel:`No`                                  |
+----------------------------------+-------------------------------------------------+
| Sync Reply Mode                  | :guilabel:`none`                                |
+----------------------------------+-------------------------------------------------+
| Acknowledgement Requested        | :guilabel:`never`                               |
+----------------------------------+-------------------------------------------------+
| Acknowledgement Signed Requested | :guilabel:`never`                               |
+----------------------------------+-------------------------------------------------+
| Duplicate Elimination            | :guilabel:`never`                               |
+----------------------------------+-------------------------------------------------+
| Message Order                    | :guilabel:`NotGuaranteed`                       |
+----------------------------------+-------------------------------------------------+
| Signing Required?                | :guilabel:`No`                                  |
+----------------------------------+-------------------------------------------------+
| Encryption Required? (Mail Only) | :guilabel:`No`                                  |
+----------------------------------+-------------------------------------------------+
| Certificate For Encryption       | none                                            |
+----------------------------------+-------------------------------------------------+
| Maximum Retries                  | :literal:`1`                                    |
+----------------------------------+-------------------------------------------------+
| Retry Interval (ms)              | :literal:`30000`                                |
+----------------------------------+-------------------------------------------------+
| Certificate For Verification     | none                                            |
+----------------------------------+-------------------------------------------------+

Web Service Usage Sample Flow
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In order to validate the installation of Hermes 2, a web service usage sample program is provided. It can be executed by running the following scripts in a command prompt.

+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Program                  | Purpose                                                                                                                                                        |
+==========================+================================================================================================================================================================+
| :program:`as2-send` /    | Send an AS2/ebMS message to the installed Hermes 2.                                                                                                            |
| :program:`ebms-send`     |                                                                                                                                                                |
+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :program:`as2-history` / | Show the message history of Hermes 2. This program will list the inbox and outbox messages in the data storage of Hermes 2.                                    |
| :program:`ebms-history`  | The user can view the details of the inbox and outbox. For inbox messages, the user can also download the payload in the repository of Hermes 2, if available. |
+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+

In order to test whether Hermes 2 has installed successfully or not, we suggest running the sample programs in the following steps:

#. Send a message to the local Hermes 2 by running :program:`ebms-send`/:program:`as2-send`.

#. Check the status of the sent message by running :program:`ebms-history`/:program:`as2-history` and select the message from the outbox.

#. Check the received message by running :program:`ebms-history`/:program:`as2-history` and select the message from the inbox to download the payload.

AS2 Web Service Usage Sample
""""""""""""""""""""""""""""

Before executing the following AS2 web service usage sample, the partnership from `Creating an AS2 Partnership`_ must be created.

#. Send a message to the local Hermes 2 using the script :program:`as2-send`.

   This program creates and sends a request attached with the payload named :file:`testpayload` under the directory :file:`{<HERMES2_HOME>}/sample/config/as2-send` to Hermes 2.
   
   Upon successful execution, you should be able to see the similar output shown as follow:
   
   .. code-block:: none

      ----------------------------------------------------
                      AS2 Message Sender
      ----------------------------------------------------
      Initialize Logger ...
      Importing AS2 sending parameters ... ./config/as2-send/as2- request.xml
      Importing AS2 partnership parameters ... ./config/as2- partnership.xml
      Initialize AS2 message sender...
      Adding payload in the AS2 message...
      Sending AS2 sending request ...

                         Sending Done:
      ----------------------------------------------------
      New message id: 20080722-133931-01300@127.0.1.1
      Please view log for details ..

#. Check the sent message using the script :program:`as2-history`.

   This program retrieves the list of sent/received message from Hermes 2. 

   .. code-block:: none

      ----------------------------------------------------
           AS2 Message History Web Service Client
      ----------------------------------------------------
      Initialize Logger ...
      Importing AS2 config parameters ... ./config/as2-history/as2- request.xml
      Initialize AS2 messsage history queryer ...
      Sending AS2 message history query request ...
    
                          Sending Done:
      ----------------------------------------------------
                 AS2 Message that are matched
      ----------------------------------------------------
      No. of message: 2
      0 | Message id : 20080722-133931-01300@127.0.1.1
      1 | Message id : 20080722-133931-01300@127.0.1.1
      MessageBox: outbox
      MessageBox: inbox
      ----------------------------------------------------
      Select message (0 - 1), -1 to exit:

   Enter :literal:`0` to check the sent message. A display similar to the following will appear: 

   .. code-block:: none

      Select message (0 - 1), -1 to exit: 0
      Query Message ID          : 20080722-133931-01300@127.0.1.1 
      Query Message Status      : DL 
      Query Message Status Desc : null 
      ACK Message ID            : null 
      ACK Message Status        : null 
      ACK Message Status Desc   : null

#. Check the received message and download the payload.

   From the select message screen of :program:`as2-history`, enter 1 to select the inbox message and it will display ``Please provide the folder to store the payload(s):``. Press enter to save the payload in the current folder. A file named :file:`as2.{<timestamp>}@127.0.1.1.Payload.0` will be downloaded, where :file:`{<timestamp>}` is the time :program:`as2-send` was executed. Open that file and you will see the follow content:

   .. image:: /_static/images/4-4-1-smaple-message.png

ebMS Web Service Usage Sample
"""""""""""""""""""""""""""""

Before executing the following ebMS web service usage sample, the partnership from `Creating an ebMS Partnership`_ must be created.

#. Send a message to the local Hermes 2 server using the script :program:`ebms-send`.

   This program creates and sends a request attached with the payload named :file:`testpayload` under the directory :file:`{<HERMES2_HOME>}/sample/config/ebms-send` to Hermes 2.

   Upon successful execution, an output similar to the following will be displayed:

   .. code-block:: none

      ----------------------------------------------------
                 EbMS sender web service client           
      ----------------------------------------------------
      Initialize Logger ...
      Importing xml
      Importing l
      ebMS sending parameters ... ./config/ebms-send/ebms-request.
      ebMS partnership parameters ... ./config/ebms-partnership.xml
      Initialize ebMS web service client...
      Adding
      Sending
      payload in the ebMS message...
      ebMS sending request ...
    
                          Sending Done:
      ----------------------------------------------------
      New message id: 20080722-143157-97302@127.0.1.1
      Please view log for details ..

#. Check the sent message using the script :program:`ebms-history`.

   This program retrieves the list of sent/received message from Hermes 2.

   .. code-block:: none

      ----------------------------------------------------
                 EbMS Message History Queryer
      ----------------------------------------------------
      Initialize Logger ...
      Importing ebMS config parameters ... ./config/ebms-history/ebms-request.xml
      Initialize ebMS messsage history queryer ...
      Sending ebMS message history query request ...
    
                          Sending Done:
      ----------------------------------------------------
                   EbMS Message Query Result             
      ----------------------------------------------------
      0   | Message id : 20080722-143157-97302@127.0.1.1 | MessageBox: outbox
      1   | Message id : 20080722-143157-97302@127.0.1.1 | MessageBox: inbox
      ----------------------------------------------------
      Select message (0 - 1), -1 to exit:

   Enter :literal:`0` to check the sent message and a screen similar to the following will be displayed: 

   .. code-block:: none

                          Sending Done:
      ----------------------------------------------------
      Query Message ID          : 20080722-143157-97302@127.0.1.1
      Query Message Status      : DL
      Query Message Status Desc : Message was sent.
      ACK Message ID            : null
      ACK Message Status        : null
      ACK Message Status Desc   : null
      ----------------------------------------------------
      Please view log for details..

#. Check the received message and download the payload.

   From the select message screen of :program:`ebms-history`, enter :literal:`1` to select the inbox message and it will display ``Please provide the folder to store the payload(s):``. Press enter to save the payload in the current folder. A file named :file:`ebms.{<timestamp>}@127.0.1.1.Payload.0` will be downloaded, where :file:`{<timestamp>}` is the time :program:`ebms-send` was executed. Open that file and you will see the following content:

   .. image:: /_static/images/4-4-1-smaple-message.png


Configuration for Secure Messaging & Secure Channels
----------------------------------------------------

In order to store a private key for message signing, a keystore is needed. Under current implementation, only PKCS12 keystore is supported. If Hermes 2 was installed using the installer, there are keystore files placed in the folder called :file:`security` under both ebMS and AS2/AS2 Plus plugins.

Message Signing
^^^^^^^^^^^^^^^

To enable message signing, please configure the plugin with a corresponding keystore. A default keystore setting can be set through the installer or you can create a new customized keystore. To learn more about generating a keystore, please refer to :ref:`generate-cert`.

Sender Settings for Message Signing
"""""""""""""""""""""""""""""""""""

To instruct Hermes 2 to perform message signing with the correct private key, the corresponding Keystore Manager should be configured with the correct parameters.

Here are descriptions of the parameters:

+-------------------+--------------------------------------------------------------------------------------------------------+
| keystore-location | Absolute file path pointing to the keystore file.                                                      |
+-------------------+--------------------------------------------------------------------------------------------------------+
| keystore-password | Password to access to keystore.                                                                        |
+-------------------+--------------------------------------------------------------------------------------------------------+
| key-alias         | Name of the private key.                                                                               |
+-------------------+--------------------------------------------------------------------------------------------------------+
| key-password      | Password to retrieve the private key.                                                                  |
|                   | (**PKCS12** standard: ``key-password`` is equal to ``keystore-password``)                              |
+-------------------+--------------------------------------------------------------------------------------------------------+
| keystore-type     | The type of the keystore. This must be ``PKCS12``.                                                     |
+-------------------+--------------------------------------------------------------------------------------------------------+
| keystore-provider | The class provider to handle the keystore. :code:`org.bouncycastle.jce.provider.BouncyCastleProvider`  |
+-------------------+--------------------------------------------------------------------------------------------------------+

ebMS Sender Settings
''''''''''''''''''''

Open the configuration file named :file:`ebms.module.xml` that is placed in the :file:`conf` folder of the ebMS plugin. A component named :code:`keystore-manager-for-signature` is defined to manage the keystore.


  .. code-block:: xml

    <component id="keystore-manager-for-signature"
               name="Key Store Manager for Digital Signature">
      <class>hk.hku.cecid.piazza.commons.security.KeyStoreManager</class>
        <parameter name="keystore-location"
                   value="/corvus/plugins/hk.hku.cecid.ebms/security/corvus.p12" />
        <parameter name="keystore-password" value="password" />
        <parameter name="key-alias" value="corvus" />
        <parameter name="key-password" value="password" />
        <parameter name="keystore-type" value="PKCS12" />
        <parameter name="keystore-provider"
                   value="org.bouncycastle.jce.provider.BouncyCastleProvider" />
    </component>

AS2/AS2 Plus Sender Settings
''''''''''''''''''''''''''''

Open the configuration file named :file:`as2.module.core.xml` that is placed in the :file:`conf` folder of the AS2/AS2 Plus plugin. A component named :code:`keystore-manager` is defined to manage the keystore.

  .. code-block:: xml

    <component id="keystore-manager" name=" AS2 Key Store Manager">
      <class>hk.hku.cecid.piazza.commons.security.KeyStoreManager</class>
      <parameter name="keystore-location" value="corvus.p12" />
      <parameter name="keystore-password" value="password" />
      <parameter name="key-alias" value="corvus" />
      <parameter name="key-password" value="password" />
      <parameter name="keystore-type" value="PKCS12" />
      <parameter name="keystore-provider"
                 value="org.bouncycastle.jce.provider.BouncyCastleProvider" />
    </component>

Receiver Settings for Message Signing
"""""""""""""""""""""""""""""""""""""

For a receiver to verify the signature, a public certificate should be provided by the sender through the partnership maintenance page.

  .. image:: /_static/images/5-1-2-1.png

Set the value of :guilabel:`Signing Required` to :literal:`true`. For detailed settings of the partnership, please refer to :doc:`as2_partnership` or :doc:`ebms_partnership`.

  .. image:: /_static/images/5-1-2-2.png

Message Tranfer with Secure Channels
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To further ensure the security of message transfers, secure channels are preferable. For more details on the required configuration, please see :ref:`send-message-using-https`.

FAQ
---

Hermes 2 Deployment
^^^^^^^^^^^^^^^^^^^

Q1. The :file:`corvus.log` shows:

    .. code-block:: none
      
       hk.hku.cecid.piazza.commons.spa.PluginException: Error in processing activation by handler:
       hk.hku.cecid.ebms.spa.EbmsProcessor which is caused by java.io.IOException: exception decrypting data - java.lang.SecurityException: Unsupported keysize or algorithm parameters

A1. Please ensure the Java 2 SDK files have been replaced by the JCE files.

Q2. Some log files show the following error:

    .. code-block:: none
       
       hk.hku.cecid.piazza.commons.dao.DAOException: Unable to begin transaction.

A2. Ensure PostgreSQL/MySQL/Oracle was installed properly and check the following files:

    For AS2:

    :file:`{<HERMES2_HOME>}/plugins/hk.hku.cecid.edi.as2/conf/hk/hku/cecid/edi/as2/conf/as2.module.core.xml`. There is a tag in this file named :code:`parameter` with the attribute :code:`name=url`. Check the :code:`value` attribute to see if it references the correct server address. The format of the ``value`` attribute is the same as the JDBC connection string.

    For ebMS:

    :file:`{<HERMES2_HOME>}/plugins/hk.hku.cecid.ebms/conf/hk/hku/cecid/ebms/spa/conf/ebms.module.xml`. There is a tag in this file named:code:`parameter` with the attribute :code:`name=url`. Check the :code:`value` attribute to see if it references the correct server address. The format of the ``value`` attribute is the same as the JDBC connection string.

Web Service Usage Sample
^^^^^^^^^^^^^^^^^^^^^^^^

Q1. The following exception is thrown:
    
    .. code-block:: none
       
       Exception in thread "main" java.lang.UnsupportedClassVersionError: xxx (Unsupported major.minor version 49.0)

A1. It is very likely you are using an incompatible Java version. The web service usage sample requires J2SE 5.0 or above to run properly. In the command prompt, enter :samp:`java –version` to check the Java version.

Q2. The following error occurs:

    .. code-block:: none

       Sending ebMS/AS2 sending request ...
       java.net.ConnectException: Connection refused: connect

A2. Check that the Application Container (Tomcat) has been started.
