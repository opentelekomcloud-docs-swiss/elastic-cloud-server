:original_name: en-us_topic_0121978383.html

.. _en-us_topic_0121978383:

Querying NICs of an ECS
=======================

Function
--------

This API is used to query NICs of an ECS.

URI
---

GET /v1/{project_id}/cloudservers/{server_id}/os-interface

:ref:`Table 1 <en-us_topic_0121978383__table38523909>` describes the parameters in the URI.

.. _en-us_topic_0121978383__table38523909:

.. table:: **Table 1** Parameter description

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory             | Description                                                                                         |
   +=======================+=======================+=====================================================================================================+
   | project_id            | Yes                   | Specifies the project ID.                                                                           |
   |                       |                       |                                                                                                     |
   |                       |                       | For details about how to obtain the ID, see :ref:`Obtaining a Project ID <en-us_topic_0022670701>`. |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | server_id             | Yes                   | Specifies the ECS ID.                                                                               |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+

Request
-------

None

Response
--------

:ref:`Table 2 <en-us_topic_0121978383__table25276401>` describes the response parameters.

.. _en-us_topic_0121978383__table25276401:

.. table:: **Table 2** Response parameters

   +----------------------+------------------+----------------------------------------------------------------------------------------------+
   | Parameter            | Type             | Description                                                                                  |
   +======================+==================+==============================================================================================+
   | interfaceAttachments | Array of objects | Specifies ECS NICs. For details, see :ref:`Table 3 <en-us_topic_0121978383__table49805933>`. |
   +----------------------+------------------+----------------------------------------------------------------------------------------------+

.. _en-us_topic_0121978383__table49805933:

.. table:: **Table 3** **interfaceAttachments** field description

   +------------+------------------+-------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Type             | Description                                                                                                             |
   +============+==================+=========================================================================================================================+
   | port_state | String           | Specifies the NIC port status.                                                                                          |
   +------------+------------------+-------------------------------------------------------------------------------------------------------------------------+
   | fixed_ips  | Array of objects | Specifies private IP addresses for NICs. For details, see :ref:`Table 4 <en-us_topic_0121978383__table15567163961815>`. |
   +------------+------------------+-------------------------------------------------------------------------------------------------------------------------+
   | net_id     | String           | Specifies the network ID to which the NIC port belongs.                                                                 |
   +------------+------------------+-------------------------------------------------------------------------------------------------------------------------+
   | port_id    | String           | Specifies the NIC port ID.                                                                                              |
   +------------+------------------+-------------------------------------------------------------------------------------------------------------------------+
   | mac_addr   | String           | Specifies the MAC address of the NIC.                                                                                   |
   +------------+------------------+-------------------------------------------------------------------------------------------------------------------------+

.. _en-us_topic_0121978383__table15567163961815:

.. table:: **Table 4** **fixed_ips** field description

   ========== ====== ===================================================
   Parameter  Type   Description
   ========== ====== ===================================================
   subnet_id  String Specifies the subnet of the NIC private IP address.
   ip_address String Specifies the NIC private IP address.
   ========== ====== ===================================================

Example Request
---------------

Query NICs of an ECS.

.. code-block:: text

   GET https://{endpoint}/v1/{project_id}/cloudservers/{server_id}/os-interface

Example Response
----------------

.. code-block::

   {
       "interfaceAttachments": [
           {
               "port_state": "ACTIVE",
               "fixed_ips": [
                   {
                       "subnet_id": "ba31e1f5-fa76-4530-862c-5176fad033cf",
                       "ip_address": "192.168.0.33"
                   }
               ],
               "net_id": "610a4af2-1d90-4d2b-8057-dc238b26febf",
               "port_id": "04819c0a-6a07-44b6-945e-fb932071888e",
               "mac_addr": "fa:16:3e:45:65:c4"        }
       ]
   }

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.
