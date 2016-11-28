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

  ::

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

  1. In Windows platform, open a command prompt and type "java –jar hermes2_installer.jar" or if java is not set in your environment path, specify the full path.
  
  2. In Unix/Linux platform, open xterm and follow the same procedure as above.
  
  **OR**
  
  3. In Windows platform, you can execute by double-click or right-click on the .jar file and selecting "open with" and choosing javaw (located where you installed java, in the bin folder).

  .. image:: _static/images/hermes-2-0-opensource-installer.png
  
  4. Click next until you get to Step 1 of the installation.
