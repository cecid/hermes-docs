Quickstart
==========
Installing Hermes
-----------------

#. Install `Docker <https://docs.docker.com/engine/installation/>`_
#. Create and run Docker Container for Hermes Database (MySQL)
   
   .. code-block:: sh

      docker run --name hermes_db -e MYSQL_ROOT_PASSWORD=corvus -d cecid/hermes_db:2.1

#. Create and run Docker Container for Hermes Application Server (Tomcat)
   
   .. code-block:: sh

      docker run --name hermes_app --link h2o_db:db -p 8080:8080 -d cecid/hermes_app:2.1
#. Login to Admin page ``http://localhost:8080/corvus/admin/home`` (username:``corvus``, pwd:``corvus``) and start working with Hermes.


Talking to Hermes via sample clients
------------------------------------

Preparation
^^^^^^^^^^^
Windows environment
"""""""""""""""""""

1. Download and extract :download:`the Hermes clients sample <_static/Hermes_client_sample.zip>` to a working directory ``<WorkDir>`` 
2. Set environment variable :envvar:`JAVA_HOME` to the directory where Java is installed.

UNIX environment
""""""""""""""""

1. Download and extract :download:`the Hermes clients sample <_static/Hermes_client_sample.zip>` to a working directory ``<WorkDir>`` 
#. Set environment variable :envvar:`JAVA_HOME` to the directory where Java is installed.
#. Change the permissions of all shell-script files in ``<WorkDir>`` to be executable with the following command:
   
   .. code-block:: sh

      sudo chmod 755 *.sh


Showcases : Loopback messaging example
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Create the partnership
""""""""""""""""""""""

   ``[Unix]``

   .. code-block:: sh

      cd <WorkDir>/sample
      ./ebms-partnership.sh

   ``[Windows]``

   .. code-block:: sh

      cd <WorkDir>\sample
      ebms-partnership.bat

Send a loopback message
"""""""""""""""""""""""

   ``[Unix]``

   .. code-block:: sh

      cd <WorkDir>/sample
      ./ebms-send.sh

   ``[Windows]``

   .. code-block:: sh

      cd <WorkDir>\sample
      ebms-send.bat

   This script sends a request attached with the payload named :file:`testpayload` under the directory :file:`<WorkDir>/sample/config/ebms-send` to local Hermes server.

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

.. _ebms-message-history:

List the message history
""""""""""""""""""""""""

   ``[Unix]``

   .. code-block:: sh

      cd <WorkDir>/sample
      ./ebms-history.sh

   ``[Windows]``

   .. code-block:: sh

      cd <WorkDir>\sample
      ebms-history.bat

   This script retrieves list of sent/received message to/from Hermes.

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

   Enter ``0`` to check the sent message and a screen similar to the following will be displayed: 

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

Download the message's payload
""""""""""""""""""""""""""""""

   ``[Unix]``

   .. code-block:: sh

      cd <WorkDir>/sample
      ./ebms-history.sh

   ``[Windows]``

   .. code-block:: sh

      cd <WorkDir>\sample
      ebms-history.bat

   From the select message screen of :ref:`ebms-message-history`, enter ``1`` to select the inbox message and it will display ``Please provide the folder to store the payload(s):``. Press enter to save the payload in the current folder. A file named :file:`ebms.{<timestamp>}@127.0.1.1.Payload.0` will be downloaded, where :file:`{<timestamp>}` is the time :program:`ebms-send` was executed. Open that file and you will see the following content:

   .. image:: /_static/images/4-4-1-smaple-message.png

