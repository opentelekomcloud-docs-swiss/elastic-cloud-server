:original_name: en-us_topic_0020212666.html

.. _en-us_topic_0020212666:

Deleting a NIC from an ECS
==========================

Function
--------

This API is used to delete a NIC from an ECS based on the port ID.

Constraints
-----------

The primary NIC of an ECS has routing rules configured and cannot be deleted.

When an ECS NIC is detached, the NIC that is attached to the ECS and specified by **port_id** through the OpenStack Nova API will be retained, and the NIC specified by **net_id** will be deleted.

URI
---

DELETE /v2.1/{project_id}/servers/{server_id}/os-interface/{port_id}{?reserve_port}

:ref:`Table 1 <en-us_topic_0020212666__table34333880>` describes the parameters in the URI.

.. _en-us_topic_0020212666__table34333880:

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
   | port_id               | Yes                   | Specifies the port ID of the NIC.                                                                   |
   |                       |                       |                                                                                                     |
   |                       |                       | .. note::                                                                                           |
   |                       |                       |                                                                                                     |
   |                       |                       |    When the ID is the same as the ECS primary NIC ID, the system will return error code 403.        |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | reserve_port          | No                    | Indicates whether to retain the NIC port after the NIC is unbound.                                  |
   |                       |                       |                                                                                                     |
   |                       |                       | **True**: indicates that the port is reserved.                                                      |
   |                       |                       |                                                                                                     |
   |                       |                       | **False**: indicates that the port is deleted. This is the default value.                           |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+

Request
-------

None

Response
--------

None

Example Request
---------------

Delete a NIC from an ECS based on the specified port ID.

.. code-block:: text

   DELETE https://{endpoint}/v2.1/{project_id}/servers/{server_id}/os-interface/{port_id}

Example Response
----------------

None

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.
