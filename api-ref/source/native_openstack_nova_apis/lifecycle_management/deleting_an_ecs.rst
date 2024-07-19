:original_name: en-us_topic_0025560296.html

.. _en-us_topic_0025560296:

Deleting an ECS
===============

Function
--------

This API is used to delete an ECS.

Constraints
-----------

When an ECS is deleted, the NIC that is attached to the ECS and specified by **port_id** through the OpenStack Nova API will be retained, and the NIC specified by **net_id** will be deleted.

URI
---

DELETE /v2.1/{project_id}/servers/{server_id}

:ref:`Table 1 <en-us_topic_0025560296__table2659898791032>` describes the parameters in the URI.

.. _en-us_topic_0025560296__table2659898791032:

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

None

Example Request
---------------

Delete a specified ECS.

.. code-block:: text

   DELETE https://{endpoint}/v2.1/{project_id}/servers/{server_id}

Example Response
----------------

None

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.
