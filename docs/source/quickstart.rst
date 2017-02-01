Quickstart
==========
H2O development environment
---------------------------
#. Install `Vagrant <https://www.vagrantup.com/>`_
#. Install `Virtualbox <https://www.virtualbox.org/>`_
#. Clone repository (if not already cloned)

   .. code-block:: sh

      git clone git@gitlab.com:cecid/hermes.git

#. Start vagrant box

   .. code-block:: sh
     
      cd hermes
      vagrant up

   Provision is done when ``Provision done!`` message is shown.
#. Open Hermes admin page at http://localhost:18080/corvus/admin/home. 
   Username and password are both ``corvus``

Create and run Docker containers
--------------------------------
#. Install `Docker`_ and `Docker Compose`_

   .. _Docker: https://www.docker.com/
   .. _Docker Compose: https://docs.docker.com/compose/

#. Clone repository (if not already cloned)

   .. code-block:: sh

      git clone git@gitlab.com:cecid/hermes.git

#. Set environment variable

   .. code-block:: sh
      
      export DOCKER_HOST=unix:///var/run/docker.sock

#. Run

   .. code-block:: sh
      
      cd hermes
      docker-compose -f deploy/docker-compose.yml up -d

Create Docker container for Hermes database
-------------------------------------------
(Optional, should be automatically built if ``docker-compose`` is used)

#. Install `Docker <https://www.docker.com/>`_
#. Clone repository (if not already cloned)
   
   .. code-block:: sh

      git clone git@gitlab.com:cecid/hermes.git

#. Set environment variable

   .. code-block:: sh
    
      export DOCKER_HOST=unix:///var/run/docker.sock

#. Build Hermes Database image

   .. code-block:: sh
      
      cd hermes
      docker build --tag "h2o/db:1.0" -f deploy/db/Dockerfile .

#. Run Docker Container for Hermes Database

   .. code-block:: sh

      docker run --name h2o_db -e MYSQL_ROOT_PASSWORD=<ROOT_PASSWORD> -d h2o/db:1.0

   Two databases (``ebms`` and ``as2``) and a user (``corvus`` with password ``corvus``) will be created.
#. Connect to databases
   
   .. code-block:: sh

      docker run -it --link h2o_db:db --rm h2o/db:1.0 mysql -hdb -P3306 -ucorvus -p ebms
      docker run -it --link h2o_db:db --rm h2o/db:1.0 mysql -hdb -P3306 -ucorvus -p as2

Create Docker container for Hermes application server
-----------------------------------------------------
(Optional, should be automatically built if ``docker-compose`` is used)

#. Install `Docker <https://www.docker.com/>`_
#. Clone repository (if not already cloned)
   
   .. code-block:: sh

      git clone git@gitlab.com:cecid/hermes.git

#. Set environment variable

   .. code-block:: sh
    
      export DOCKER_HOST=unix:///var/run/docker.sock

#. Build Hermes App Server image

   .. code-block:: sh
      
      cd hermes
      docker build --tag "h2o/app:1.0" -f deploy/app_server/Dockerfile .

#. Run Docker Container for Hermes Database (should be built beforehand)

   .. code-block:: sh

      docker run --name h2o_db -e MYSQL_ROOT_PASSWORD=<ROOT_PASSWORD> -d h2o/db:1.0

#. Run Docker Container for Hermes Application Server

   .. code-block:: sh
      
      docker run --name h2o_app --link h2o_db:db -p 18080:8080 -d h2o/app:1.0

Admin page and connect to Hermes API
------------------------------------
#. Once Hermes server is deployed, you should be able to login to Admin page of Hermes and start working with it.
   The URL is at ``http://localhost:18080/corvus/admin/home``
#. Authentication is needed to use the admin page and API. The user settings for accessing both are located at :file:`<TOMCAT_HOME>/tomcat-users.xml`.
   Note that for both Vagrant and Docker environments, accounts have already been created in the build script. It can be modified if needed.
#. (Optional) The authentication setting is configured via deployment descriptor at :file:`corvus-webapp/src/main/webapp/WEB-INF/web.xml`.
   During development, it might be handy to "disable" authentication on API temporarily.
   To do so, just comment out the whole ``security-constraint`` element with web resource name as ``Restricted API resources`` at :file:`corvus-webapp/src/main/webapp/WEB-INF/web.xml`, and re-deploy the ``corvus`` webapp at Tomcat.
#. To test the API, the simplest way is to connect to it using any API client. For example, ``curl`` can be used as a command line client.
   GUI based client like Postman is a useful tool too.
#. API for checking Hermes API server status:
   
   .. code-block:: sh
      
      $ curl -X GET http://127.0.0.1:18080/corvus/api/status

   Response:

   .. code-block:: sh
      
      {"status":"healthy","server_time":1479185615}

#. API for adding partnership:
   
   .. code-block:: sh
      
      $ curl -X POST \
        -- data '{"id":"loopback", "cpa_id":"cpa", "service":"service", "action":"action", "transport-endpoint":"http://127.0.0.1:18080/corvus/httpd/ebms/inbound"}' \
        http://127.0.0.1:18080/corvus/api/partnership/ebms

   Response:

   .. code-block:: sh

      {"id":"loopback"}

#. API for querying partnerships:

   .. code-block:: sh
      
      $ curl -X GET http://127.0.0.1:18080/corvus/api/partnership/ebms

   Response:

   .. code-block:: sh

      {"partnerships":[{"id":"loopback","cpa_id":"cpa","service":"service","action":"action","disabled":false,"transport_endpoint":"http://127.0.0.1:8080/corvus/httpd/ebms/inbound","ack_requested":null,"signed_ack_requested":null,"duplicate_elimination":null,"message_order":null,"retries":-2147483648,"retry_interval":-2147483648,"sign_requested":false,"sign_certicate":null}]}

#. API for sending message:

   .. code-block:: sh
      
      $ curl -X POST \
        --data '{"partnership_id":"loopback", "from_party_id":"from", "to_party_id":"to", "conversation_id":"conv", "payload":"dGhpcyBpcyBhIHRlc3QK"}' \
        http://127.0.0.1:18080/corvus/api/message/send/ebms

   Response:

   .. code-block:: sh

      {"id":"20161115-053847-08213@127.0.1.1"}

#. API for checking message status:

   .. code-block:: sh

      $ curl -X GET http://127.0.0.1:18080/corvus/api/message/send/ebms?id=20161115-053847-08213@127.0.1.1
   
   Response: 
      
   .. code-block:: sh

      {"message_id":"20161115-053847-08213@127.0.1.1","status":"DL"}

#. API for receiving message list:

   .. code-block:: sh

      $ curl -X GET http://127.0.0.1:18080/corvus/api/message/receive/ebms?partnership_id=loopback

   Response:

   .. code-block:: sh

      {"message_ids":[{"id":"20161115-053847-08213@127.0.1.1","timestamp":1479188327}]}

#. API for receiving a message:
   
   .. code-block:: sh

      $ curl -X POST \
        --data '{"message_id":"20161115-053847-08213@127.0.1.1"}' \
        http://127.0.0.1:18080/corvus/api/message/receive/ebms

   Response:

   .. code-block:: sh

      {"id":"20161115-053847-08213@127.0.1.1","cpa_id":"cpa","service":"service","action":"action","from_party_id":"from","to_party_id":"to","conversation_id":"conv","timestamp":1479188327,"status":"DL","payloads":[{"payload":"dGhpcyBpcyBhIHRlc3QK"}]}