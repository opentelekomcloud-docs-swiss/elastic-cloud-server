:original_name: en-us_topic_0077845908.html

.. _en-us_topic_0077845908:

Binding a Virtual IP Address to an ECS NIC
==========================================

Function
--------

A virtual IP address provides the second IP address for one or multiple ECS NICs, improving high availability between the ECSs.

This API is used to configure a virtual IP address for an ECS NIC.

-  If the specified IP address is a virtual IP address that has not been assigned, the system automatically assigns the virtual IP address and binds it to a specified NIC.
-  If the specified IP address is a virtual IP address that has been assigned, the system binds the virtual IP address to a specified NIC. If the **device_owner** of this IP address is left blank, only intra-VPC layer 2 and layer 3 communication is supported. If the **device_owner** of this IP address is **neutron:VIP_PORT**, intra-VPC layer 2 and layer 3 communication, inter-VPC peer access, as well as Internet access through EIP, VPN, and Cloud Connect are supported.

URI
---

PUT /v1/{project_id}/cloudservers/nics/{nic_id}

:ref:`Table 1 <en-us_topic_0077845908__table55925239>` describes the parameters in the URI.

.. _en-us_topic_0077845908__table55925239:

.. table:: **Table 1** Parameter description

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory             | Description                                                                                         |
   +=======================+=======================+=====================================================================================================+
   | project_id            | Yes                   | Specifies the project ID.                                                                           |
   |                       |                       |                                                                                                     |
   |                       |                       | For details about how to obtain the ID, see :ref:`Obtaining a Project ID <en-us_topic_0022670701>`. |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | nic_id                | Yes                   | Specifies the ECS NIC ID.                                                                           |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+

Request
-------

:ref:`Table 2 <en-us_topic_0077845908__table21989419>` describes the request parameters.

.. _en-us_topic_0077845908__table21989419:

.. table:: **Table 2** Request parameters

   +-----------+-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                                                                      |
   +===========+===========+========+==================================================================================================================================================+
   | nic       | Yes       | Object | Specifies the NIC parameters required for binding a virtual IP address. For details, see :ref:`Table 3 <en-us_topic_0077845908__table44975500>`. |
   +-----------+-----------+--------+--------------------------------------------------------------------------------------------------------------------------------------------------+

.. _en-us_topic_0077845908__table44975500:

.. table:: **Table 3** **nic** field description

   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                           |
   +=================+=================+=================+=======================================================================================================================+
   | subnet_id       | Yes             | String          | Specifies the information about the NICs to be added to an ECS.                                                       |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | Set the parameter value to the ID (in UUID format) of the network created in the VPC to which the target ECS belongs. |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+
   | ip_address      | Yes             | String          | Specifies the virtual IP address to be bound to a NIC.                                                                |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+
   | reverse_binding | No              | Boolean         | Specifies whether to add the NIC IP/MAC address pair to **allowed_address_pairs**.                                    |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 | .. note::                                                                                                             |
   |                 |                 |                 |                                                                                                                       |
   |                 |                 |                 |    The virtual IP address can be displayed on the NIC details page only after the IP/MAC address pair is added.       |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+

Response
--------

:ref:`Table 4 <en-us_topic_0077845908__table54154414204821>` describes the response parameters.

.. _en-us_topic_0077845908__table54154414204821:

.. table:: **Table 4** Response parameters

   ========= ====== =========================
   Parameter Type   Description
   ========= ====== =========================
   port_id   String Specifies the ECS NIC ID.
   ========= ====== =========================

Example Request
---------------

Bind the virtual IP address **192.168.0.7** to the NIC whose network ID is **d32019d3-bc6e-4319-9c1d-6722fc136a23**.

.. code-block:: text

   PUT https://{endpoint}/v1/{project_id}/cloudservers/nics/{nic_id}

   {
       "nic": {
              "subnet_id": "d32019d3-bc6e-4319-9c1d-6722fc136a23",
              "ip_address": "192.168.0.7",
              "reverse_binding": true
       }
   }

Example Response
----------------

.. code-block::

   {
      "port_id": "d32019d3-bc6e-4319-9c1d-6722fc136a23"
   }

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.

Error Codes
-----------

See :ref:`Error Codes <en-us_topic_0022067717>`.
