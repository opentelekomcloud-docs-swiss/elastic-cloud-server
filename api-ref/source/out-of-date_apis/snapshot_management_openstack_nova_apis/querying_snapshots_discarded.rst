:original_name: en-us_topic_0065817726.html

.. _en-us_topic_0065817726:

Querying Snapshots (Discarded)
==============================

Function
--------

This API is used to query information about a volume snapshot.

This API has been discarded. Use the EVS API "Querying Details About an EVS Snapshot (OpenStack Cinder API v2)".

URI
---

GET /v2.1/{project_id}/os-snapshots/{snapshot_id}

:ref:`Table 1 <en-us_topic_0065817726__en-us_topic_0057973216_table2814978410562>` describes the parameters in the URI.

.. _en-us_topic_0065817726__en-us_topic_0057973216_table2814978410562:

.. table:: **Table 1** Parameter description

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory             | Description                                                                                         |
   +=======================+=======================+=====================================================================================================+
   | project_id            | Yes                   | Specifies the project ID.                                                                           |
   |                       |                       |                                                                                                     |
   |                       |                       | For details about how to obtain the ID, see :ref:`Obtaining a Project ID <en-us_topic_0022670701>`. |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | snapshot_id           | Yes                   | Specifies the volume snapshot ID.                                                                   |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+

Response
--------

**Response parameters**

:ref:`Table 2 <en-us_topic_0065817726__en-us_topic_0057973216_table30138413>` describes the response parameters.

.. _en-us_topic_0065817726__en-us_topic_0057973216_table30138413:

.. table:: **Table 2** Response parameters

   +--------------------+---------+----------------------------------------------------------+
   | Parameter          | Type    | Description                                              |
   +====================+=========+==========================================================+
   | id                 | String  | Specifies the disk snapshot ID in UUID format.           |
   +--------------------+---------+----------------------------------------------------------+
   | status             | String  | Specifies the volume snapshot status.                    |
   +--------------------+---------+----------------------------------------------------------+
   | displayName        | String  | Specifies the volume snapshot name.                      |
   +--------------------+---------+----------------------------------------------------------+
   | displayDescription | String  | Specifies the volume snapshot description.               |
   +--------------------+---------+----------------------------------------------------------+
   | createdAt          | String  | Specifies the time when the volume snapshot was created. |
   +--------------------+---------+----------------------------------------------------------+
   | volumeId           | String  | Specifies the disk ID in UUID format for the snapshot.   |
   +--------------------+---------+----------------------------------------------------------+
   | size               | Integer | Specifies the volume snapshot size.                      |
   +--------------------+---------+----------------------------------------------------------+

Example Request
---------------

.. code-block:: text

   GET https://{endpoint}/v2.1/d6c277ba8820452e83df36f33c9fa561/os-snapshots/b836dc3d-4e10-4ea4-a34c-8f6b0460a583

Example Response
----------------

.. code-block::

   {
       "snapshot":
           {
               "createdAt": "2016-05-20T16:54:14.981520",
               "displayDescription": null,
               "id": "b836dc3d-4e10-4ea4-a34c-8f6b0460a583",
               "displayName": "test",
               "size": 1,
               "status": "creating",
               "volumeId": "ba5730ea-8621-4ae8-b702-ff0ffc12c209"
           }
   }

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.
