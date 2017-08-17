Installing Hermes
=================

Introduction
------------

The Hermes installer is packaged in the form of a self-extracted java archive (JAR). Upon proper invocation, you will see an installation wizard, either in graphical or text format. Following the steps will install the following components:

* Hermes core
* Hermes plugins (AS2 / AS2 Plus / ebMS)
* Database tables of Hermes plugins for one of the following database:
  
  * Postgres 9.2 or later
  * Oracle 11gR2 or later
  * MySQL 5.5 or later with InnoDB storage engine supported

* Web service usage sample


Prerequisite
------------
1. Java SE Development Kit 8
#. Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy Files 

   a. Download the JCE Unlimited Strength Jurisdiction Policy Files for JDK 8 from 

      http://www.oracle.com/technetwork/java/javase/downloads/jce8-download-2133166.html

   #. Unzip the downloaded file

      .. code-block:: sh

         unzip jce_policy-8.zip
      
   #. Replace the two jar files :file:`local_policy.jar` and :file:`US_export_policy.jar` in the directory :file:`/usr/lib/jvm/java-8-oracle/jre/lib/security` with the corresponding jar file unzipped in the previous step.

      .. code-block:: sh

         cd UnlimitedJCEPolicyJDK8
         sudo cp local_policy.jar /usr/lib/jvm/java-8-oracle/jre/lib/security/local_policy.jar
         sudo cp US_export_policy.jar /usr/lib/jvm/java-8-oracle/jre/lib/security/US_export_policy.jar

#. Tomcat 8.5 or above with port ``8080``

   a. Edit :file:`/etc/systemd/system/tomcat.service`. 
      Change :envvar:`Environment=JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-amd64/jre` to :envvar:`Environment=JAVA_HOME=/usr/lib/jvm/java-8-oracle/jre`

   #. Restart Tomcat

   .. note::
      To access the admin page, you will need to have a Tomcat user with an admin role.  One way to do this is to define the user in :file:`tomcat-users.xml`.  Please refer to the Realm Configuration section in the Tomcat documentation for more details.

   Sample of :file:`tomcat-user.xml`:

   .. code-block:: xml

      <?xml version='1.0' encoding='utf-8'?>
      <tomcat-users>
          <role rolename="tomcat"/>
          <role rolename="admin"/>
          <role rolename="api"/>
          <user username="corvus" password="corvus" roles="tomcat,admin,api"/>
      </tomcat-users>

#. One of the following databases installed on any server:

   * PostgreSQL 9.2 or later. :file:`{<POSTGRES_HOME>}` is referring to the home directory of PostgreSQL in the remaining parts of the document.
   * MySQL 5.5 or later. :file:`{<MYSQL_HOME>}` is referring to the home directory of MySQL in the remaining parts of the document.
   * Oracle 11gR2 or later. :file:`{<ORACLE_HOME>}` is referring to the home directory of Oracle in the remaining parts of the document.

Installation
------------
Step 1 – Environment setup
^^^^^^^^^^^^^^^^^^^^^^^^^^
Install all the prerequisite items. The rest of this guide assumes that they are all running on the same machine.

Step 2 – Database Configuration
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Postgres**

#. Create a database user with username ``corvus`` and password ``corvus``.

   a. Open a command prompt
   #. Go to :file:`{<POSTGRES_HOME>}/bin`
   #. Type :samp:`createuser -A -d -P -U {<POSTGRES_ADMIN>} corvus` where :samp:`{<POSTGRES_ADMIN>}` represents the name of an administrator/super-user in the PostgreSQL database. This value is ``postgres`` if not specified. This may require a super user or Postgres owner to execute in Linux.
   #. Enter the password ``corvus``
   #. Enter the password again for confirmation
   #. Enter the PostgreSQL administrator password for creating a new user role.

#. Create two databases named ``as2`` and ``ebms`` with the ``corvus`` user.

   a. Open a command prompt
   #. Go to :file:`{<POSTGRES_HOME>}/bin`
   #. Type ``createdb –U corvus –W as2``
   #. Enter the password ``corvus``
   #. Repeat steps 2.3 - 2.4 for the ``ebms`` database.

**MySQL**

1. Create two databases named ``as2`` and ``ebms`` with username ``corvus`` and password ``corvus``.

   a. Open a command prompt
   #. Go to :file:`{<MYSQL_HOME>}/bin`
   #. Type :samp:`mysql –u {<MYSQL_ADMIN>} -p` where :samp:`{<MYSQL_ADMIN>}` represents the name of an administrator/super-user in the MySQL database. This is ``root`` by default. This may require super user or MySQL owner to execute in Linux.
   #. Enter the command below to create the ``as2`` database. Note that specifying collate to ``latin1_general_cs`` is essential.
    
      .. code-block:: sql

         create database as2 collate=latin1_general_cs;
     
   #. Enter the command below to create and assign access privileges to user ``corvus``. 

      .. code-block:: sql

         grant all on as2.* to 'corvus'@'localhost' identified by 'corvus';
     
   #. Repeat steps 1.4 – 1.5 for the ``ebms`` database.

**Oracle**

Oracle database creation involves a number of steps and custom parameters for different requirements for the database server. We propose the following reference as a guideline for creating an Oracle database for Hermes:

https://docs.oracle.com/cd/E11882_01/server.112/e10897/install.htm#ADMQS0232

Step 3 – Hermes Deployment
^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Execute the installer

   * For Unix/Linux, open :program:`terminal` and type ``sudo java –jar hermes2_installer.jar``.

   .. image:: /_static/images/3-4-1-hermes-2-0-text-installer.png

   Press :guilabel:`Enter` until you get to Screen (Step1).
   
   * For Windows, open a command prompt as an Administrator and type ``java –jar hermes2_installer.jar`` or if :program:`java` is not set in your environment path, specify the full path.

   .. image:: /_static/images/3-4-1-hermes-2-0-opensource-installer.png

   Click :guilabel:`Next` until you get to Screen (Step 1).

#. Step 1 - Configure Hermes Core

   .. image:: /_static/images/3-4-1-step-1-configure-hermes-2-core.png
   .. image:: /_static/images/3-4-1-step-1-h2o-installer.png

   Descriptions of the settings:

   +-----------------------------------+---------------------------------------------------------------------+
   | Web Application Folder            | Folder to place the web application (e.g :file:`webapps`) in Tomcat.|
   +-----------------------------------+---------------------------------------------------------------------+
   | Hermes Home                       | Location to place the Hermes core library and some related files.   |
   +-----------------------------------+---------------------------------------------------------------------+
   | JDBC Driver                       | Specify which database vendor to connect to.                        |
   |                                   | One of the following 3 database vendors can be selected:            |
   |                                   |                                                                     | 
   |                                   |   * Postgres                                                        |
   |                                   |   * Oracle                                                          |
   |                                   |   * MySQL                                                           |
   +-----------------------------------+---------------------------------------------------------------------+
   | Hermes ebMS Plugin                | Optional. Install the ebMS component.                               |
   +-----------------------------------+---------------------------------------------------------------------+
   | Hermes AS2 Plugin                 | Optional. Install the AS2 component.                                |
   +-----------------------------------+---------------------------------------------------------------------+
   | Web Service Usage Sample          | Optional. Install the sample program of web service client.         |
   +-----------------------------------+---------------------------------------------------------------------+

   Click :guilabel:`Next` and press :guilabel:`Yes` if the installer prompts you to create a new directory.

#. Step 1.1 - Configure Database Driver
   
   Oracle and MySQL drivers need to be downloaded manually. Once this is done, specify the location of the driver:
   
   .. image:: /_static/images/3-4-1-step-1-1-configure-database-driver.png
   .. image:: /_static/images/3-4-1-step-1-1-h2o-installer.png

   Descriptions of the settings:
   
   +-----------------------------+----------------------------------------------------+
   | JDBC Driver Folder (.jar)   | Directory of the downloaded JDBC driver.           |
   +-----------------------------+----------------------------------------------------+

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
   |                   | * If this is your **first time** installing Hermes, please check this option.                                                                         |
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
   |                   | * If this is your **first time** installing Hermes, please check this option.                                                                         |
   |                   |                                                                                                                                                       |
   |                   | * If you are switching from AS2 to AS2 Plus or vice versa, we highly recommend you check this option.                                                 |
   |                   |                                                                                                                                                       |
   |                   | * If you choose to re-create the tables, all of the existing data in the specified database will be removed during installation.                      |
   |                   |   Please backup all the data in the selected database before choosing to re-create the tables.                                                        |
   +-------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------+

   If you followed the prerequisite installation procedures above, you can just leave it as the default. Click :guilabel:`Next` when you have finished the configuration.

#. Click on :guilabel:`Install` and you're done!

Step 4 – Start Hermes2
^^^^^^^^^^^^^^^^^^^^^^^

#. Checklist:

   * Java JDK 8 or above with Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy Files 7.

   * Apache Tomcat 8.5 or above Servlet/JSP Container.

   * Database server is running with ebMS and/or AS2 database instances and the tables are created.

   * If you are running Unix/Linux, make sure that at least read permissions are set to the core directory and read/write for the AS2 repository directory in :file:`{<HERMES2_HOME>}`.

   * Start Tomcat.

#. To verify that Hermes is running, access the following URL from a web browser:

     http://localhost:8080/corvus/home

   The welcome page should be displayed as below:

   .. image:: /_static/images/3-5-step-4-welcome-page.jpeg

#. To access the admin page, go to the following URL. The login user and password are the same as the Tomcat user with admin privileges specified in Point 3 of `Prerequisite`_.

    http://localhost:8080/corvus/admin/home

#. Once you have gained access to the admin page, you should see the Hermes Administration Console page:

   .. image:: /_static/images/3-5-step-4-administration-console-page.png

That's it! Hermes should now be up and running. You can test your setup by running our web service usage sample in next section.


Partnership Maintenance and Web Service Usage Sample
-------------------------------------------------------

A tool kit called :program:`Web Service Usage Sample` was installed under the :file:`{<HERMES2_HOME>}/sample` folder. It contains tools to test the installed Hermes.

Directory Organization
^^^^^^^^^^^^^^^^^^^^^^

+---------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
| Directory/File                        | Description                                                                                                                                         |
+=======================================+=====================================================================================================================================================+
| :file:`config/*`                      | Contains the configuration file for the sample programs. The folders inside this directory contain related files for specific sample programs.      |
+---------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
| :file:`config/ebms-partnership.xml`   | These two files contain partnership settings for ebMS and AS2 that are used by the sample programs.                                                 |
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

   .. note::
      To run the sample program, Administrator privilege is required.

UNIX environment
""""""""""""""""

1. Set environment variable :envvar:`JAVA_HOME` to the directory where Java is located.
#. Change the owner and the group of :file:`{<HERMES2_HOME>}` and :file:`{<TOMCAT_HOME>}/webapps/corvus` with the following commands:

   .. code-block:: sh

      sudo chown -R tomcat:<OWNER_GROUP> <HERMES2_HOME>
      sudo chown -R tomcat:<OWNER_GROUP> <TOMCAT_HOME>/webapps/corvus

#. Change the permissions of all files in :file:`{<HERMES2_HOME>}` and :file:`{<TOMCAT_HOME>}/webapps/corvus` to ``775`` with the following command:
   
   .. code-block:: sh

      sudo chmod -R 775 <HERMES2_HOME>
      sudo chmod -R 775 <TOMCAT_HOME>/webapps/corvus
      

Partnership Maintenance
^^^^^^^^^^^^^^^^^^^^^^^

Users need to define a **partnership**, which contains the messaging details between sender and recipient. It is required to identify the sender and the recipient when transporting messages.

A web service sample program is provided to manage partnerships (add, update or delete). The partnership configuration for the AS2/ebMS loopback test is placed in :file:`{<HERMES2_HOME>}/sample/config/{<as2/ebms>}-partnership.xml`.

+------------------------------+----------------------------------------------------------+
| Program                      | Purpose                                                  |
+==============================+==========================================================+
| :program:`as2-partnership` / | Maintains a specified AS2/ebMS partnership in Hermes.    |
| :program:`ebms-partnership`  |                                                          |
+------------------------------+----------------------------------------------------------+

Creating an AS2 Partnership
"""""""""""""""""""""""""""

To create the partnership required to perform the AS2 messaging loopback test using `AS2 Web Service Usage Sample`_, you need to execute the script :program:`as2-partnership`.

**Or:**

Access http://localhost:8080/corvus/admin/as2/partnership to configure the partnership manually. Below is a simple loopback configuration sample:

.. image:: /_static/images/4-3-1-create-as2-partnership.png


+-------------------------------+------------------------------------------------+
| Partnership ID                | ``as2-loopback``                               |
+-------------------------------+------------------------------------------------+
| AS2 From                      | ``as2loopback``                                |
+-------------------------------+------------------------------------------------+
| AS2 To                        | ``as2loopback``                                |
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
| Maximum Retries               | ``1``                                          |
+-------------------------------+------------------------------------------------+
| Retry Interval (ms)           | ``30000``                                      |
+-------------------------------+------------------------------------------------+
| Message Signature Enforced?   | :guilabel:`No`                                 |
+-------------------------------+------------------------------------------------+
| Message Encryption Enforced?  | :guilabel:`No`                                 |
+-------------------------------+------------------------------------------------+
| Certificate For Verification  | none                                           |
+-------------------------------+------------------------------------------------+

Creating an AS2 Plus Partnership
""""""""""""""""""""""""""""""""

Please follow the same procedure listed in `Creating an AS2 Partnership`_ .

Creating an ebMS Partnership
""""""""""""""""""""""""""""

To create the partnership required to perform the ebMS messaging loopback test using `ebMS Web Service Usage Sample`_, you need to execute the script :program:`ebms-partnership`.

**Or:**

Access http://localhost:8080/corvus/admin/ebms/partnership to configure the partnership manually. Below is a simple loop-back configuration sample:

  .. image:: /_static/images/4-3-3-ebms-plugin.png

+----------------------------------+-------------------------------------------------+
| Partnership ID                   | ``ebms-loopback``                               |
+----------------------------------+-------------------------------------------------+
| CPA ID                           | ``cpaid``                                       |
+----------------------------------+-------------------------------------------------+
| Service                          | http://localhost:8080/corvus/httpd/ebms/inbound |
+----------------------------------+-------------------------------------------------+
| Action                           | ``action``                                      |
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
| Maximum Retries                  | ``1``                                           |
+----------------------------------+-------------------------------------------------+
| Retry Interval (ms)              | ``30000``                                       |
+----------------------------------+-------------------------------------------------+
| Certificate For Verification     | none                                            |
+----------------------------------+-------------------------------------------------+

Web Service Usage Sample Flow
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In order to validate the installation of Hermes, a web service usage sample program is provided. It can be executed by running the following scripts in a command prompt.

+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Program                  | Purpose                                                                                                                                                        |
+==========================+================================================================================================================================================================+
| :program:`as2-send` /    | Send an AS2/ebMS message to the installed Hermes.                                                                                                              |
| :program:`ebms-send`     |                                                                                                                                                                |
+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :program:`as2-history` / | Show the message history of Hermes. This program will list the inbox and outbox messages in the data storage of Hermes.                                        |
| :program:`ebms-history`  | The user can view the details of the inbox and outbox. For inbox messages, the user can also download the payload in the repository of Hermes, if available.   |
+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------+

In order to test whether Hermes has been installed successfully or not, we suggest running the sample programs in the following steps:

#. Send a message to the local Hermes by running :program:`ebms-send`/:program:`as2-send`.

#. Check the status of the sent message by running :program:`ebms-history`/:program:`as2-history` and select the message from the outbox.

#. Check the received message by running :program:`ebms-history`/:program:`as2-history` and select the message from the inbox to download the payload.

AS2 Web Service Usage Sample
""""""""""""""""""""""""""""

Before executing the following AS2 web service usage sample, the partnership from `Creating an AS2 Partnership`_ must be created.

#. Send a message to the local Hermes using the script :program:`as2-send`.

   This program creates and sends a request attached with the payload named :file:`testpayload` under the directory :file:`{<HERMES2_HOME>}/sample/config/as2-send` to Hermes.
   
   Upon successful execution, you should be able to see the similar output shown as follow:
   
   .. image:: /_static/images/as2-send.png

#. Check the sent message using the script :program:`as2-history`.

   This program retrieves the list of sent/received message from Hermes. 

   .. image:: /_static/images/as2-history.png

   Enter ``0`` to check the sent message. A display similar to the following will appear: 

   .. image:: /_static/images/as2-history-0.png

#. Check the received message and download the payload.

   From the select message screen of :program:`as2-history`, enter 1 to select the inbox message and it will display ``Please provide the folder to store the payload(s):``. Press enter to save the payload in the current folder. A file named :file:`as2.{<timestamp>}@127.0.1.1.Payload.0` will be downloaded, where :file:`{<timestamp>}` is the time :program:`as2-send` was executed. Open that file and you will see the follow content:

   .. image:: /_static/images/4-4-1-smaple-message.png

ebMS Web Service Usage Sample
"""""""""""""""""""""""""""""

Before executing the following ebMS web service usage sample, the partnership from `Creating an ebMS Partnership`_ must be created.

#. Send a message to the local Hermes server using the script :program:`ebms-send`.

   This program creates and sends a request attached with the payload named :file:`testpayload` under the directory :file:`{<HERMES2_HOME>}/sample/config/ebms-send` to Hermes.

   Upon successful execution, an output similar to the following will be displayed:

   .. image:: /_static/images/ebms-send.png

#. Check the sent message using the script :program:`ebms-history`.

   This program retrieves the list of sent/received message from Hermes.

   .. image:: /_static/images/ebms-history.png

   Enter ``0`` to check the sent message and a screen similar to the following will be displayed: 

   .. image:: /_static/images/ebms-history-0.png

#. Check the received message and download the payload.

   From the select message screen of :program:`ebms-history`, enter ``1`` to select the inbox message and it will display ``Please provide the folder to store the payload(s):``. Press enter to save the payload in the current folder. A file named :file:`ebms.{<timestamp>}@127.0.1.1.Payload.0` will be downloaded, where :file:`{<timestamp>}` is the time :program:`ebms-send` was executed. Open that file and you will see the following content:

   .. image:: /_static/images/4-4-1-smaple-message.png

Configuration for Sending Secure Message
""""""""""""""""""""""""""""""""""""""""

To send signed message through HTTPS, we have to configure a trust-store, keystore and certificate separately in Hermes and Tomcat. For details, please refer to the section :ref:`secure_messaging_configuration`.

FAQ
---

**Hermes Deployment**

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

    :file:`{<HERMES2_HOME>}/plugins/hk.hku.cecid.edi.as2/conf/hk/hku/cecid/edi/as2/conf/as2.module.core.xml`. There is a tag in this file named ``parameter`` with the attribute ``name=url``. Check the ``value`` attribute to see if it references the correct server address. The format of the ``value`` attribute is the same as the JDBC connection string.

    For ebMS:

    :file:`{<HERMES2_HOME>}/plugins/hk.hku.cecid.ebms/conf/hk/hku/cecid/ebms/spa/conf/ebms.module.xml`. There is a tag in this file named ``parameter`` with the attribute ``name=url``. Check the ``value`` attribute to see if it references the correct server address. The format of the ``value`` attribute is the same as the JDBC connection string.

**Web Service Usage Sample**

Q1. The following exception is thrown:
    
    .. code-block:: none
       
       Exception in thread "main" java.lang.UnsupportedClassVersionError: xxx (Unsupported major.minor version 49.0)

A1. It is very likely you are using an incompatible Java version. The web service usage sample requires J2SE 5.0 or above to run properly. In the command prompt, enter ``java –version`` to check the Java version.

Q2. The following error occurs:

    .. code-block:: none

       Sending ebMS/AS2 sending request ...
       java.net.ConnectException: Connection refused: connect

A2. Check that the Application Container (Tomcat) has been started.
