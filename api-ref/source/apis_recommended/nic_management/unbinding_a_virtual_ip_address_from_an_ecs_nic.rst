:original_name: en-us_topic_0077846077.html

.. _en-us_topic_0077846077:

Unbinding a Virtual IP Address from an ECS NIC
==============================================

Function
--------

A virtual IP address provides the second IP address for one or multiple ECS NICs, improving high availability between the ECSs.

This API is used to unbind a virtual IP address from an ECS NIC. After the NIC is unbound, it is not deleted. For instructions about how to delete an ECS NIC, see :ref:`Deleting NICs from an ECS in a Batch <en-us_topic_0020212665>`.

URI
---

PUT /v1/{project_id}/cloudservers/nics/{nic_id}

:ref:`Table 1 <en-us_topic_0077846077__table55925239>` describes the parameters in the URI.

.. _en-us_topic_0077846077__table55925239:

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

:ref:`Table 2 <en-us_topic_0077846077__table21989419>` describes the request parameters.

.. _en-us_topic_0077846077__table21989419:

.. table:: **Table 2** Request parameters

   +-----------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                                                                        |
   +===========+===========+========+====================================================================================================================================================+
   | nic       | Yes       | Object | Specifies the NIC parameters required for unbinding a virtual IP address. For details, see :ref:`Table 3 <en-us_topic_0077846077__table44975500>`. |
   +-----------+-----------+--------+----------------------------------------------------------------------------------------------------------------------------------------------------+

.. _en-us_topic_0077846077__table44975500:

.. table:: **Table 3** **nic** field description

   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                         |
   +=================+=================+=================+=====================================================================================================================================+
   | subnet_id       | Yes             | String          | Specifies the information about the NICs to be added to an ECS.                                                                     |
   |                 |                 |                 |                                                                                                                                     |
   |                 |                 |                 | This parameter must be left blank when you unbind the virtual IP address from an ECS NIC.                                           |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------+
   | ip_address      | Yes             | String          | Specifies the virtual IP address to be unbound from a NIC.                                                                          |
   |                 |                 |                 |                                                                                                                                     |
   |                 |                 |                 | This parameter must be left blank when you unbind the virtual IP address from an ECS NIC.                                           |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------+
   | reverse_binding | No              | Boolean         | Indicates the **allowed_address_pairs** attribute of a virtual IP address, specifying whether the NIC IP/MAC address pair is added. |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

:ref:`Table 4 <en-us_topic_0077846077__table54154414204821>` describes the response parameters.

.. _en-us_topic_0077846077__table54154414204821:

.. table:: **Table 4** Response parameters

   ========= ====== =========================
   Parameter Type   Description
   ========= ====== =========================
   port_id   String Specifies the ECS NIC ID.
   ========= ====== =========================

Example Request
---------------

Unbind a virtual IP address from an ECS NIC.

.. code-block:: text

   PUT https://{endpoint}/v1/{project_id}/cloudservers/nics/{nic_id}

   {
       "nic": {
              "subnet_id": "",
              "ip_address": "",
              "reverse_binding": false
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
