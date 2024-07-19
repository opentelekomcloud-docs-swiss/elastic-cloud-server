:original_name: en-us_topic_0065817708.html

.. _en-us_topic_0065817708:

Creating a Disk (Discarded)
===========================

Function
--------

This API is used to create a disk.

This API has been discarded. Use the EVS API "Creating EVS Disks (OpenStack Cinder API v2)".

URI
---

POST /v2.1/{project_id}/os-volumes

:ref:`Table 1 <en-us_topic_0065817708__en-us_topic_0057973208_table2814978410562>` describes the parameters in the URI.

.. _en-us_topic_0065817708__en-us_topic_0057973208_table2814978410562:

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

:ref:`Table 2 <en-us_topic_0065817708__en-us_topic_0057973208_table34804632>` describes the request parameters.

.. _en-us_topic_0065817708__en-us_topic_0057973208_table34804632:

.. table:: **Table 2** Request parameters

   +---------------------+-----------------------------------------------------------------------------+-----------------+-------------------------------------------------------------------------------------------------------+
   | Parameter           | Mandatory                                                                   | Type            | Description                                                                                           |
   +=====================+=============================================================================+=================+=======================================================================================================+
   | availability_zone   | No                                                                          | String          | Specifies the AZ where the volume is created.                                                         |
   |                     |                                                                             |                 |                                                                                                       |
   |                     |                                                                             |                 | If the specified AZ does not exist, creating the volume failed, and the volume is in **error** state. |
   |                     |                                                                             |                 |                                                                                                       |
   |                     |                                                                             |                 | An AZ must be specified during the volume creation.                                                   |
   +---------------------+-----------------------------------------------------------------------------+-----------------+-------------------------------------------------------------------------------------------------------+
   | display_description | No                                                                          | String          | Specifies the volume description.                                                                     |
   +---------------------+-----------------------------------------------------------------------------+-----------------+-------------------------------------------------------------------------------------------------------+
   | snapshot_id         | No                                                                          | String          | Specifies the snapshot ID.                                                                            |
   |                     |                                                                             |                 |                                                                                                       |
   |                     |                                                                             |                 | If this parameter is specified, the volume is to be created from a snapshot.                          |
   +---------------------+-----------------------------------------------------------------------------+-----------------+-------------------------------------------------------------------------------------------------------+
   | size                | Yes (If the volume is created from a snapshot, this parameter is optional.) | Integer         | Specifies the volume size.                                                                            |
   |                     |                                                                             |                 |                                                                                                       |
   |                     |                                                                             |                 | Unit: GB                                                                                              |
   +---------------------+-----------------------------------------------------------------------------+-----------------+-------------------------------------------------------------------------------------------------------+
   | display_name        | No                                                                          | String          | Specifies the volume name.                                                                            |
   +---------------------+-----------------------------------------------------------------------------+-----------------+-------------------------------------------------------------------------------------------------------+
   | volume_type         | No                                                                          | String          | Specifies the volume type.                                                                            |
   +---------------------+-----------------------------------------------------------------------------+-----------------+-------------------------------------------------------------------------------------------------------+
   | metadata            | No                                                                          | Object          | Specifies the volume metadata.                                                                        |
   +---------------------+-----------------------------------------------------------------------------+-----------------+-------------------------------------------------------------------------------------------------------+

Response
--------

:ref:`Table 3 <en-us_topic_0065817708__en-us_topic_0057973208_table36305920>` describes the response parameters.

.. _en-us_topic_0065817708__en-us_topic_0057973208_table36305920:

.. table:: **Table 3** Response parameters

   +--------------------+------------------+-------------------------------------------------+
   | Parameter          | Type             | Description                                     |
   +====================+==================+=================================================+
   | id                 | String           | Specifies the disk ID in UUID format.           |
   +--------------------+------------------+-------------------------------------------------+
   | displayName        | String           | Specifies the volume name.                      |
   +--------------------+------------------+-------------------------------------------------+
   | status             | String           | Specifies the volume status.                    |
   +--------------------+------------------+-------------------------------------------------+
   | attachments        | Array of objects | Specifies the volume attachment information.    |
   +--------------------+------------------+-------------------------------------------------+
   | availabilityZone   | String           | Specifies the AZ to which the volume belongs.   |
   +--------------------+------------------+-------------------------------------------------+
   | createdAt          | String           | Specifies the time when the volume was created. |
   +--------------------+------------------+-------------------------------------------------+
   | displayDescription | String           | Specifies the volume description.               |
   +--------------------+------------------+-------------------------------------------------+
   | volumeType         | String           | Specifies the volume type.                      |
   +--------------------+------------------+-------------------------------------------------+
   | snapshotId         | String           | Specifies the snapshot ID.                      |
   +--------------------+------------------+-------------------------------------------------+
   | metadata           | Object           | Specifies the volume metadata.                  |
   +--------------------+------------------+-------------------------------------------------+
   | size               | Integer          | Specifies the size of the volume.               |
   +--------------------+------------------+-------------------------------------------------+

Example Request
---------------

.. code-block:: text

   POST https://{endpoint}/v2.1/b84c367e4d1047fc9b54f28b400ddbc2/os-volumes

.. code-block::

   {
       "volume": {
           "availability_zone": "az1-dc1",
           "display_description": "test1",
           "snapshot_id": null,
           "size": 1,
           "display_name": "test",
           "volume_type": "SSD",
           "metadata": {
               "testkey": "testvalue"
           }
       }
   }

Example Response
----------------

.. code-block::

   {
     "volume": {
       "displayDescription": "test1",
       "volumeType": "SATA",
       "createdAt": "2018-05-18T01:17:03.871808",
       "metadata": {
         "testkey": "testvalue",
         "resourceSpecCode": "SATA"
       },
       "attachments": [
         {}
       ],
       "snapshotId": null,
       "size": 1,
       "displayName": "test",
       "id": "b4fb891c-c665-4478-92b0-8a7fa65a57cd",
       "availabilityZone": "az1.dc1",
       "status": "creating"
     }
   }

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.
