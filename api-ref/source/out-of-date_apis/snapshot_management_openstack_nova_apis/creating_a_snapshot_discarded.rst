:original_name: en-us_topic_0065817725.html

.. _en-us_topic_0065817725:

Creating a Snapshot (Discarded)
===============================

Function
--------

This API is used to create a snapshot for a volume.

This API has been discarded. Use the EVS API "Creating an EVS Snapshot (OpenStack Cinder API v2)".

Constraints
-----------

A snapshot name cannot be prefixed with **autobk_snapshot**.

URI
---

POST /v2.1/{project_id}/os-snapshots

:ref:`Table 1 <en-us_topic_0065817725__en-us_topic_0057973215_table2814978410562>` describes the parameters in the URI.

.. _en-us_topic_0065817725__en-us_topic_0057973215_table2814978410562:

.. table:: **Table 1** Parameter description

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory             | Description                                                                                         |
   +=======================+=======================+=====================================================================================================+
   | project_id            | Yes                   | Specifies the project ID.                                                                           |
   |                       |                       |                                                                                                     |
   |                       |                       | For details about how to obtain the ID, see :ref:`Obtaining a Project ID <en-us_topic_0022670701>`. |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+

Request
-------

:ref:`Table 2 <en-us_topic_0065817725__en-us_topic_0057973215_table51396461>` describes the request parameters.

.. _en-us_topic_0065817725__en-us_topic_0057973215_table51396461:

.. table:: **Table 2** Request parameters

   +---------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter           | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                                                                                                                            |
   +=====================+=================+=================+========================================================================================================================================================================================================================================================================================================================================================================================+
   | display_description | No              | String          | Specifies the snapshot description.                                                                                                                                                                                                                                                                                                                                                    |
   +---------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | volume_id           | Yes             | String          | Specifies the volume ID.                                                                                                                                                                                                                                                                                                                                                               |
   +---------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | display_name        | No              | String          | Specifies the name of the EVS snapshot.                                                                                                                                                                                                                                                                                                                                                |
   |                     |                 |                 |                                                                                                                                                                                                                                                                                                                                                                                        |
   |                     |                 |                 | The value contains a maximum of 255 bytes.                                                                                                                                                                                                                                                                                                                                             |
   |                     |                 |                 |                                                                                                                                                                                                                                                                                                                                                                                        |
   |                     |                 |                 | .. note::                                                                                                                                                                                                                                                                                                                                                                              |
   |                     |                 |                 |                                                                                                                                                                                                                                                                                                                                                                                        |
   |                     |                 |                 |    When creating a backup for an EVS disk through VBS, a snapshot will be created and named with prefix **autobk_snapshot\_**. The EVS console has imposed operation restrictions on snapshots with prefix **autobk_snapshot\_**. You are advised to not use **autobk_snapshot\_** as the name prefix for the snapshots you created. Otherwise, the snapshots cannot be used normally. |
   +---------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | force               | No              | Boolean         | Specifies whether a snapshot is to be forcibly created.                                                                                                                                                                                                                                                                                                                                |
   |                     |                 |                 |                                                                                                                                                                                                                                                                                                                                                                                        |
   |                     |                 |                 | If the value is **true**, a snapshot for the volume in use can be created.                                                                                                                                                                                                                                                                                                             |
   +---------------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

:ref:`Table 3 <en-us_topic_0065817725__en-us_topic_0057973215_table772049>` describes the response parameters.

.. _en-us_topic_0065817725__en-us_topic_0057973215_table772049:

.. table:: **Table 3** Response parameters

   +--------------------+-----------+---------+----------------------------------------------------------+
   | Parameter          | Mandatory | Type    | Description                                              |
   +====================+===========+=========+==========================================================+
   | id                 | Yes       | String  | Specifies the disk snapshot ID in UUID format.           |
   +--------------------+-----------+---------+----------------------------------------------------------+
   | status             | Yes       | String  | Specifies the volume snapshot status.                    |
   +--------------------+-----------+---------+----------------------------------------------------------+
   | displayName        | No        | String  | Specifies the volume snapshot name.                      |
   +--------------------+-----------+---------+----------------------------------------------------------+
   | displayDescription | No        | String  | Specifies the volume snapshot description.               |
   +--------------------+-----------+---------+----------------------------------------------------------+
   | createdAt          | Yes       | String  | Specifies the time when the volume snapshot was created. |
   +--------------------+-----------+---------+----------------------------------------------------------+
   | volumeId           | Yes       | String  | Specifies the disk ID in UUID format for the snapshot.   |
   +--------------------+-----------+---------+----------------------------------------------------------+
   | size               | Yes       | Integer | Specifies the volume snapshot size.                      |
   +--------------------+-----------+---------+----------------------------------------------------------+

Example Request
---------------

.. code-block:: text

   POST https://{endpoint}/v2.1/d6c277ba8820452e83df36f33c9fa561/os-snapshots

.. code-block::

   {
       "snapshot": {
           "display_name": "test",
           "display_description": null,
           "volume_id": "ba5730ea-8621-4ae8-b702-ff0ffc12c209"
       }
   }

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
