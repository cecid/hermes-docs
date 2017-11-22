Quickstart
==========

Install Hermes with Docker
--------------------------

#. Install the `Docker Engine <https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/#install-using-the-repository>`_ on Ubuntu 16.04+.

   .. code-block:: sh

      sudo apt-get update
      sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
      curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
      sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
      sudo apt-get update
      sudo apt-get install docker-ce      

#. Run the Docker container for Hermes database (MySQL).

   .. code-block:: sh

      docker run --name hermes_db -e MYSQL_ROOT_PASSWORD=corvus -d cecid/hermes_db:2.2

#. Run the Docker container for Hermes application server (Tomcat).
   
   .. code-block:: sh

      docker run --name hermes_app --link hermes_db:db -p 8080:8080 -d cecid/hermes_app:2.2

#. Log in to the Hermes administration console at ``http://localhost:8080/corvus/admin/home`` (username:``corvus``, password:``corvus``) to check if Hermes is up and running.

.. note::

   1. In Step 2 and 3, the corresponding Docker image will be downloaded from the `Docker Hub <https://hub.docker.com/>`_ for the initial run. As the size of ``cecid/hermes_db`` and ``cecid/hermes_app`` are about 400MB and 1.0GB, these steps may take at least several minutes to complete depending on the network speed.
   2. You may need the administrator or root privilage to execute ``docker run``.


Loopback Messaging with Sample Clients
--------------------------------------

Preparation
^^^^^^^^^^^

**Linux (Ubuntu 16.04+):**

.. _java-install:

#. Install `Java SE 8 <http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html>`_ or above.

   .. code-block:: sh

      sudo add-apt-repository ppa:webupd8team/java
      sudo apt update
      sudo apt install oracle-java8-unlimited-jce-policy
      sudo apt install oracle-java8-set-default

#. Please check Java 8 has been set up properly.  

   .. code-block:: sh

      java -version

#. Download and extract the :download:`Hermes sample clients <_static/Hermes_client_sample.zip>` to a working directory :file:`{<WorkDir>}`

   .. code-block:: sh

      cd <WorkDir> 
      curl -O http://hermes.cecid.org/en/latest/_downloads/Hermes_client_sample.zip
      unzip Hermes_client_sample.zip
      sudo chmod -R 755 sample 

#. Change the current directory to :file:`{<WorkDir>}/sample`.


**Windows:**

#. Install `Java 8 <http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html>`_ or above.

#. Please check Java 8 has been set up properly.  

   .. code-block:: sh

      java -version

  If the above command fails to run, please try to set environment variable :envvar:`JAVA_HOME` to the directory where Java is installed.

#. Download and extract the :download:`Hermes simple clients  <_static/Hermes_client_sample.zip>` to a working directory :file:`{<WorkDir>}/sample`.

#. Change the current directory to :file:`{<WorkDir>}/sample`.


Create Loopback Partnership
^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Linux / Unix:**

.. code-block:: sh

   ./ebms-partnership.sh

**Windows:**

.. code-block:: sh

   ebms-partnership.bat

You will see the following message.

.. code-block:: none
   
   ----------------------------------------------------
         EBMS Partnership Maintainance Tool      
   ----------------------------------------------------
   Initialize logger .. 
   Importing EBMS partnership parameters ...
   Importing EBMS administrative sending parameters ... 
   Initialize EBMS HTTP data service client... 
   log4j:WARN No appenders could be found for logger    (org.apache.commons.httpclient.HttpClient).
   log4j:WARN Please initialize the log4j system properly.
   Sending    EBMS HTTP partnership maintenance request ... 
   
                       Sending Done:                   
   ----------------------------------------------------
   The result status : Operation executed successfully.
   Please view log for details .. 

In the Hermes administration console at ``http://localhost:8080/corvus/admin/ebms/partnership``, you will find a new Partnership :kbd:`ebms-loopback` is created.


Send Loopback Message
^^^^^^^^^^^^^^^^^^^^^

**Linux / Unix:**

.. code-block:: sh

   ./ebms-send.sh

**Windows:**

.. code-block:: sh

   ebms-send.bat

This program sends a request attached with the payload named :file:`testpayload` under the directory :file:`{<WorkDir>}/sample/config/ebms-send` to local Hermes server. You will see the following message.

.. code-block:: none
   
   ----------------------------------------------------
             EbMS sender web service client            
   ----------------------------------------------------
   Initialize Logger ... 
   Importing  ebMS sending parameters ... ./config/ebms-send/ebms-request.xml
   Importing  ebMS partnership parameters ... ./config/ebms-partnership.xml
   Initialize ebMS web service client... 
   Adding     payload in the ebMS message... 
   Sending    ebMS sending request ... 
   
                       Sending Done:                   
   ----------------------------------------------------
   New message id: 20170204-090520-45900@172.17.0.3

In the Hermes administration console at ``http://localhost:8080/corvus/admin/ebms/message_history``, you will find a new message is created in outbox.

Query Message History
^^^^^^^^^^^^^^^^^^^^^

**Linux / Unix:**

.. code-block:: sh

   ./ebms-history.sh

**Windows:**

.. code-block:: sh

   ebms-history.bat

This program lists all sent and received messages. You will see the following message.

.. code-block:: none
   
   ----------------------------------------------------
            EbMS Message History Queryer      
   ----------------------------------------------------
   Initialize Logger ... 
   Importing  ebMS config parameters ... ./config/ebms-history/ebms-request.xml
   Initialize ebMS messsage history queryer ... 
   Sending ebMS message history query request ... 
   
                       Sending Done:                   
   ----------------------------------------------------
   ----------------------------------------------------
            EbMS Message Query Result          
   ----------------------------------------------------
   0	| Message id : 20170204-090520-45900@172.17.0.3 | MessageBox: outbox
   1	| Message id : 20170204-090520-45900@172.17.0.3 | MessageBox: inbox
   ----------------------------------------------------
   
   Select message (0 - 1), -1 to exit: 0


Enter :kbd:`0` to check the sent message and the following message will be displayed: 

.. code-block:: none
   
   Sending    EBMS-status sending request ... 

                    Sending Done:                   
   ----------------------------------------------------
   Query Message ID          : 20170204-090520-45900@172.17.0.3
   Query Message Status      : DL
   Query Message Status Desc : Message was sent.
   ACK   Message ID          : null
   ACK   Message Status      : null
   ACK   Message Status Desc : null
   
   ----------------------------------------------------
   
   Please view log for details .. 


Download Payload of Received Message
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

**Linux / Unix:**

.. code-block:: sh

   ./ebms-history.sh


**Windows:**

.. code-block:: sh

   ebms-history.bat

You will see the following message.

.. code-block:: none
   
   ----------------------------------------------------
            EbMS Message History Queryer      
   ----------------------------------------------------
   Initialize Logger ... 
   Importing  ebMS config parameters ... ./config/ebms-history/ebms-request.xml
   Initialize ebMS messsage history queryer ... 
   Sending ebMS message history query request ... 
   
                       Sending Done:                   
   ----------------------------------------------------
   ----------------------------------------------------
            EbMS Message Query Result          
   ----------------------------------------------------
   0	| Message id : 20170204-090520-45900@172.17.0.3 | MessageBox: outbox
   1	| Message id : 20170204-090520-45900@172.17.0.3 | MessageBox: inbox
   ----------------------------------------------------
   
   Select message (0 - 1), -1 to exit: 1
   Currrent Dir: /home/cecid/WorkDir/sample
   Please provide the folder to store the payload(s): 
   Initialize ebMS receiving web service client... 
   Sending    ebMS receiving request ... for 20170204-090520-45900@172.17.0.3
   ----------------------------------------------------
   
   Please view log for details .. 

#. Enter :kbd:`1` to select the received message and you will be asked to the folder to store the payloads. 

#. Press enter to save the payload in the current folder. A file named :file:`ebms.{<timestamp>}@127.0.1.1.Payload.0` will be downloaded, where :file:`{<timestamp>}` indicates the time :program:`ebms-send` was executed. 

#. Open the payload file and you will see the following content:

.. code-block:: none

   This is an sample message.
   
                     :#+,                                               
                    +'++                                                
                  ,++'+                                                 
                 ++'+#`                                                 
               ;+''++             `           `           `             
              #++''+;`        `++++` ``,:;::   `,::::  ++  ;+'++;       
            ;++''+++         '++++#` `;:;;;;  `;;;;;;  ++  ;'+++++:     
           +'''''++:``;;;:   +#`     ,;;     `::,      ++  ;+   `+#     
          +''''''''  ;:;;;: ;+:      ;;``     ;;`      ++  ;+`   ++`    
         ,+'+''''++ .:;:;;; ;+.     `;;,.,,, `;;`      ++  ;+    ;'.    
         ''+''''''+`,;;;::;`'+......`;::;;;;`.;;``..`.`+#``;+``..:+:`..`
         `++'''+'++ `;;;;;; ''`      :;.```` `:;       ++  ;+`   :'.    
          ;'''+'''+` ;::;;. :':`     ;; `     ;;       ++  ;+    +'`    
           :+'+'+''+  .,,` ` ++`     ::,````  ::,````  ++  ;+   .+#     
         `   #'+'''+`        ''++++` `;;;:;;  `;;:;;;  ++  ;'+++++,`    
              ,++'''#         .;;''`   .:::,`  `,:::,  ''  :'''';       
                +'+''; `                          `                     
                `,+''',                                                 
                   '''+.                                                
                    `+++`                                               
                     :+:     
                     
   This is an sample message.
