:original_name: en-us_topic_0122107472.html

.. _en-us_topic_0122107472:

Querying Disk Attachments of an ECS
===================================

Function
--------

This API is used to query disk attachments of an ECS.

URI
---

GET /v1/{project_id}/cloudservers/{server_id}/os-volume_attachments

:ref:`Table 1 <en-us_topic_0122107472__table35893824>` describes the parameters in the URI.

.. _en-us_topic_0122107472__table35893824:

.. table:: **Table 1** Parameter description

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory             | Description                                                                                         |
   +=======================+=======================+=====================================================================================================+
   | project_id            | Yes                   | Specifies the project ID.                                                                           |
   |                       |                       |                                                                                                     |
   |                       |                       | For details about how to obtain the ID, see :ref:`Obtaining a Project ID <en-us_topic_0022670701>`. |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | server_id             | Yes                   | Specifies the ECS ID in UUID format.                                                                |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+

Request
-------

None

Response
--------

:ref:`Table 2 <en-us_topic_0122107472__table57959838>` describes the response parameters.

.. _en-us_topic_0122107472__table57959838:

.. table:: **Table 2** Response parameters

   +-------------------+------------------+-------------------------------------------------------------------------------------------------------------+
   | Parameter         | Type             | Description                                                                                                 |
   +===================+==================+=============================================================================================================+
   | volumeAttachments | Array of objects | Specifies disks attached to an ECS. For details, see :ref:`Table 3 <en-us_topic_0122107472__table7886611>`. |
   +-------------------+------------------+-------------------------------------------------------------------------------------------------------------+

.. _en-us_topic_0122107472__table7886611:

.. table:: **Table 3** **volumeAttachments** field description

   +-----------------------+-----------------------+------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                              |
   +=======================+=======================+==========================================================================================+
   | device                | String                | Specifies the drive letter of the EVS disk, displayed as the device name on the console. |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------+
   | id                    | String                | Specifies the mount ID, which is the same as the EVS disk ID.                            |
   |                       |                       |                                                                                          |
   |                       |                       | The value is in UUID format.                                                             |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------+
   | serverId              | String                | Specifies the ECS ID in UUID format.                                                     |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------+
   | volumeId              | String                | Specifies the EVS disk ID in UUID format.                                                |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------+

Example Request
---------------

Query the list of disks attached to an ECS.

.. code-block:: text

   GET https://{endpoint}/v1/{project_id}/cloudservers/{server_id}/os-volume_attachments

Example Response
----------------

.. code-block::

   {
       "volumeAttachments": [
           {
               "device": "/dev/sdd",
               "id": "a26887c6-c47b-4654-abb5-dfadf7d3f803",
               "serverId": "4d8c3732-a248-40ed-bebc-539a6ffd25c0",
               "volumeId": "a26887c6-c47b-4654-abb5-dfadf7d3f803"
           },
           {
               "device": "/dev/sdc",
               "id": "a26887c6-c47b-4654-abb5-dfadf7d3f804",
               "serverId": "4d8c3732-a248-40ed-bebc-539a6ffd25c0",
               "volumeId": "a26887c6-c47b-4654-abb5-dfadf7d3f804"
           }
       ]
   }

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.

Error Codes
-----------

See :ref:`Error Codes <en-us_topic_0022067717>`.
