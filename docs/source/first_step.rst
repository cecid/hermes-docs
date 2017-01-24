The First Step
==============

Introduction
----------------

One of the most common difficulties in using Hermes 2 for new developers/users is managing a partnership and programming the web service requester before they are able to deliver messages to their partner. This article is purposed to assist the user to create and maintain partnerships in Hermes 2. For more information on the installation and administration console of Hermes 2, please refer to :doc:`installation`.

What is a partnership?
^^^^^^^^^^^^^^^^^^^^^^

A partnership in Hermes 2 is defined as a channel to your business partner. A partnership is a **simplex** (one-way) communication channel to your business partner. In a typical two-way business document exchange, the Hermes 2 in each party should have **TWO** partnerships; one for sending, another for receiving. After the partnerships have been defined, the application can reference the partnerships to send or receive business messages.

.. image:: /_static/images/first_step/Partnership_Overview.png

Existing partnership types
^^^^^^^^^^^^^^^^^^^^^^^^^^

Currently, Hermes 2 has two types of partnerships, which are ebMS and AS2. They represent the communication agreement with your partner to use ebMS protocol and AS2 protocol respectively.


ebMS 2.0 partnership
--------------------
 
.. _what-is-an-ebms-2-0-partnership:

What is an ebMS 2.0 partnership?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

For an ebms 2.0 partnership, **CPA (Collaboration Protocol Agreement) ID**, **Service** and **Action** are used to uniquely identify each partnership. The values of these parameters will appear in the headers of outgoing ebMS messages. The purpose of these parameters for a sending partnership and a receiving partnership are different:

* In a sending partnership, these values are taken as the values in the ebMS headers of outgoing messages.
* In a receiving partnership, these values are taken as filtering criteria. If Hermes 2 receives an ebMS message whose **CPA ID**, **Service** and **Action** values do not have a matching partnership, a negative acknowledgement will be sent back to the sender and no application can retrieve the message on the receiving side.

In Hermes 2, the **Service** parameter for sending and receiving partnerships has to be HTTP URL (Universal Resource Locator). The **Service** has a different meaning in each partnership:

* For a sending artnership, the **Service** acts as the endpoint URL of the sending Hermes for receiving acknowledgement.
* For a receiving partnership, since the **Service** is a filtering criterion for incoming messages, it should be the endpoint URL of the sending Hermes.

Let us look at a typical example below, in which two Hermes communicate using ebMS protocol:

.. image:: /_static/images/first_step/EbMS_Partnership_Overview.png

In the above scenario, the Hermes in company A has an IP 1.1.1.1. Its **Service** value for receiving incoming acknowledgements is http://1.1.1.1:8080/corvus/httpd/ebms/inbound, where we suppose the application server is running on port :literal:`8080`. Similarly, the **Service** value for company B is http://1.1.1.2:8080/corvus/httpd/ebms/inbound.

Since the receiving partnership's **CPA ID**, **Service** and **Action** filter the incoming messages, the values in the receiving partnership of the receiving Hermes should always be the same as the values in the sending partnership of the sending Hermes.

 
How to create your first ebMS 2.0 partnership
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
1. Open a Web browser.
#. Go to Hermes 2 Administration Console at :samp:`http://{<LOCALHOST>}:{<PORT>}/corvus/admin/home`.
#. Enter the administrator username and password for Hermes 2.
#. Click :guilabel:`Ebms Plugin` in the module tab located on the left hand side.
#. Click the :guilabel:`Partnership` tab on the central horizontal tabbed bar to display the partnership creation page.
#. To create the simplest ebMS 2.0 partnership, you are only required to fill in the following seven fields in the form:

   a. Partnership ID
   #. CPA ID
   #. Service
   #. Action
   #. Transport URL
   #. Retries
   #. Retry Interval

#. Fill in **Partnership ID**, **CPA ID**, **Service** and **Action** as shown below:
   Partnership ID is the unique identifier of the partnership in the sending Hermes while the three remaining fields (CPA ID, Service and Action) form a composite identifier between sending and receiving systems.

   +--------------------+------------------------------------------------------------+
   | **Partnership ID** | :literal:`MyFirstPartnership`                              |
   +--------------------+------------------------------------------------------------+
   | **CPA ID**         | :literal:`MyFirstCPAID`                                    |
   +--------------------+------------------------------------------------------------+
   | **Service**        | http://localhost:8080/corvus/httpd/ebms/inbound            |
   +--------------------+------------------------------------------------------------+
   | **Action**         | :literal:`MyFirstAction`                                   |
   +--------------------+------------------------------------------------------------+
  
#. Fill in the **Transport Endpoint** (the receiver's URL) as shown below:

   The Transport Endpoint URL should be formatted as :samp:`http://{<RECEIVER_HOST>}:{<PORT>}/corvus/httpd/ebms/inbound`

   where :samp:`corvus/httpd/ebms/inbound` is the context path for accepting and receiving incoming ebXML messages if the receiving system is also using Hermes 2.

   Since the receiving host below is the same as the sending host (i.e. the ebMS message loops back to the sender), only **ONE** partnership is required for sending and receiving.

   +--------------------+-------------------------------------------------+
   | Transport Endpoint | http://localhost:8080/corvus/httpd/ebms/inbound |
   +--------------------+-------------------------------------------------+
   
#. Fill in the number of retries allowed if the message fails to be delivered and the retry interval as shown below:

   +-------------------------+------------------+
   | **Retries**             | :literal:`3`     |
   +-------------------------+------------------+
   | **Retry Interval (ms)** | :literal:`30000` |
   +-------------------------+------------------+

#. Now you have completed all required fields and you should have the same input as the figure shown here.
   
   .. image:: /_static/images/first_step/CreateEbMS_Partnership_S7.png

#. Click the :guilabel:`add` button at the bottom of the page.
#. A dialog box will prompt you to confirm adding the partnership. Click :guilabel:`Ok`.
#. The message :guilabel:`Partnership Added Successfully` will be shown on the status bar (the bottom of the page).
#. Congratulations! You have successfully created your first ebMS 2.0 partnership.

 
How to update an ebMS 2.0 partnership
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Do **steps 1-5** in `How to create your first ebMS 2.0 partnership`_ or all steps if you have not registered a partnership in Hermes 2.
#. You should able to see a drop-down list under the header :guilabel:`Registered Partnership`.
#. Click the :guilabel:`Change` button.
#. Now you should able to see a module called :guilabel:`Selected Partnership` that contains the information of selected partnership from the previous step like here.

   .. image:: _static/images/first_step/CreateEbMS_Partnership_S9.png

#. Change the desired parameters/fields and click :guilabel:`Update` when you are done.
#. A dialog box will prompt you to confirm the updates. Click :guilabel:`Ok`.
#. The message :guilabel:`Partnership Updated Successfully` will be shown on the status bar (the bottom of the page).

 
How to delete an ebMS 2.0 partnership
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Do the **steps 1-4** in `How to update an ebMS 2.0 partnership`_.
#. Click the :guilabel:`Delete` button
#. The message :guilabel:`Partnership deleted successfully` will be shown on the status bar (the bottom of the page).
 
AS2 partnership
---------------

.. _what-is-an-as2-partnership:

What is an AS2 partnership?
^^^^^^^^^^^^^^^^^^^^^^^^^^^

For an AS2 partnership, the **AS2 From** and **AS2 To** fields in a partnership are used to uniquely identify it. The values of these parameters will appear in AS2 message headers. The purpose of these parameters for a sending partnership and a receiving partnership are different:

* In a sending partnership, these values are taken as the values in the headers of outgoing messages.
* In a receiving partnership, these values are taken as filtering criteria. If Hermes 2 receives an AS2 message whose **AS2 From** and **AS2 To** values do not have a matching partnership, the incoming message is rejected/ignored and no application can retrieve the message on the receiving side.

  **NOTE**: The values of **AS2 From** and **AS2 To** in the incoming AS2 message are interchanged before finding the matching partnership (i.e. the filtering criteria [AS2 From, AS2 To] = [Incoming AS2 To, Incoming AS2 From] in the AS2 message).

Although the values of **AS2 From** and **AS2 To** have no constraints, it is highly recommended that they be company specific, such as Data Universal Numbering System (DUNS) numbers, or simply identification strings agreed upon between trading partners.

Let us look at a typical example below, in which two Hermes communicate using AS2 protocol:

.. image:: /_static/images/first_step/AS2_Partnership_Overview.png
 
How to create your first AS2 partnership
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Open a Web browser.
#. Go to Hermes 2 Administration Console at :samp:`http://{<LOCALHOST>}:{<PORT>}/corvus/admin/home`.
#. Enter the administrator user name and password for Hermes 2.
#. Click the :guilabel:`AS2 Plugin` in the module tab located on the left hand side.
#. Click the :guilabel:`Partnership` tab on the central horizontal tabbed bar to display the partnership creation page.
#. To create the simplest AS2 partnership, you are only required to fill in the following seven fields in the form:

   a. Partnership ID
   #. AS2 From
   #. AS2 To
   #. Subject
   #. Transport URL
   #. Retries
   #. Retry Interval

#. Fill in **Partnership ID**, **AS2 From** and **AS2 To** as shown below:
   Partnership ID is the unique identifier of the partnership in the sender Hermes while the two remaining fields (AS2_From, AS2_To) form a composite identifier between sending and receiving systems.

   +--------------------+-------------------------------+
   | **Partnership ID** | :literal:`MyFirstPartnership` |
   +--------------------+-------------------------------+
   | **AS2 From**       | :literal:`FromMyMachine`      |
   +--------------------+-------------------------------+
   | **AS2 To**         | :literal:`ToMyMachine`        |
   +--------------------+-------------------------------+

#. Fill in the **Subject** and **Transport Endpoint** (the receiver's URL) as shown below:

   The Transport Endpoint URL should be formatted as :samp:`http://{<RECEIVER_HOST>}:{<PORT>}/corvus/httpd/as2/inbound`

   where :samp:`corvus/httpd/as2/inbound` is the context path for accepting and receiving incoming AS2 messages if the receiving system is also using Hermes 2.

   Since the receiving host below is the same as the sending host (i.e. the AS2 message loops back to the sender), only **ONE** partnership is required for sending and receiving.

   +--------------------+------------------------------------------------+
   | Subject            | MyFirstSubject                                 |
   +--------------------+------------------------------------------------+
   | Transport Endpoint | http://localhost:8080/corvus/httpd/as2/inbound |
   +--------------------+------------------------------------------------+

#. Fill in the number of retries allowed if the message fails to be delivered and the retry interval as shown below:

   +---------------------+-------+
   | Retries             | 3     |
   +---------------------+-------+
   | Retry Interval (ms) | 30000 |
   +---------------------+-------+

#.  Now you have completed to all required fields and you should have the same input as the figure shown here.

    .. image:: /_static/images/first_step/CreateAS2_Partnership_S3.png

#.  Click the :guilabel:`add` button at the bottom of the page.
#.  A dialog box will prompt you to confirm adding the partnership. Click :guilabel:`Ok`.
#.  The message :guilabel:`Partnership Added Successfully` will be shown on the status bar (the bottom of the page).
#.  Congratulations! You have successfully created your first AS2 partnership.
 
How to update an AS2 partnership
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Do the **steps 1-5** in `How to create your first AS2 partnership`_ or all steps if you have not registered a partnership in Hermes 2.
#. You should able to see a drop-down list under the header :guilabel:`Registered Partnership`.
#. Click the :guilabel:`Change` button.
#. Now you should able to see a module called :guilabel:`Selected Partnership` that contains the information of selected partnership from previous step like here.

   .. image:: /_static/images/first_step/CreateAS2_Partnership_S3.png

#. Change the desired parameters/fields and click :guilabel:`Update` when you are done.
#. A dialog box will prompt you to confirm the update. Click :guilabel:`Ok`.
#. The message :guilabel:`Partnership Updated Successfully` will be shown on the status bar (the bottom of the page).
 
How to delete AS2 partnership
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. Do the **steps 1-4** in `How to update an AS2 partnership`_.
#. Click the :guilabel:`Delete` button.
#. The message :guilabel:`Partnership deleted successfully` will be shown on the status bar (the bottom of the page).
 
Conclusion
----------

The main benefit of partnerships is that it provides abstraction on technical parameters. The abstraction is beneficial because:

1. The application does not need to change if your business partner changes the parameters, since all technical parameters are contained within the partnership.
#. The application only needs to submit payloads. It does not contain any code that is specific to the communication protocol between messaging gateways.
#. The application does not need to handle the raw and cryptic ebMS / AS2 messages. Therefore, developers only need to focus on business logic and integration with the backend systems.
 
References
----------
* :doc:`ebms_partnership`
* :doc:`as2_partnership`
* `OASIS ebMS 2.0 Specification <http://www.oasis-open.org/committees/ebxml-msg/documents/ebMS_v2_0.pdf>`_
* `AS2 Specification <https://tools.ietf.org/html/rfc4130>`_

 
What to read next
-----------------
* :doc:`web_service_communication`
