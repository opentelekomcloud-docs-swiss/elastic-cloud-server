:original_name: en-us_topic_0078695383.html

.. _en-us_topic_0078695383:

Attaching a Specified Shared EVS Disk to Multiple ECSs
======================================================

Function
--------

This API is used to attach a specified shared EVS disk to multiple ECSs.

Constraints
-----------

No more than 23 disks have been attached to each of these ECSs.

URI
---

POST /v1/{project_id}/batchaction/attachvolumes/{volume_id}

:ref:`Table 1 <en-us_topic_0078695383__table35528365105553>` describes the parameters in the URI.

.. _en-us_topic_0078695383__table35528365105553:

.. table:: **Table 1** Parameter description

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory             | Description                                                                                         |
   +=======================+=======================+=====================================================================================================+
   | project_id            | Yes                   | Specifies the project ID.                                                                           |
   |                       |                       |                                                                                                     |
   |                       |                       | For details about how to obtain the ID, see :ref:`Obtaining a Project ID <en-us_topic_0022670701>`. |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | volume_id             | Yes                   | Specifies the shared EVS disk ID.                                                                   |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+

Request
-------

:ref:`Table 2 <en-us_topic_0078695383__table55654045105553>` describes the request parameters.

.. _en-us_topic_0078695383__table55654045105553:

.. table:: **Table 2** Request parameters

   +------------+-----------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type             | Description                                                                                                                                              |
   +============+===========+==================+==========================================================================================================================================================+
   | serverinfo | Yes       | Array of objects | Specifies the list of ECSs to which the shared EVS disk is to be attached. For details, see :ref:`Table 3 <en-us_topic_0078695383__table4101646015730>`. |
   +------------+-----------+------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _en-us_topic_0078695383__table4101646015730:

.. table:: **Table 3** **serverinfo** field description

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                                                                                                                                                                                                                                                              |
   +=================+=================+=================+==========================================================================================================================================================================================================================================================================================================================================================================================================================================================+
   | server_id       | Yes             | String          | Specifies the ID of the ECS to which the shared EVS disk is to be attached.                                                                                                                                                                                                                                                                                                                                                                              |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | device          | No              | String          | Indicates the disk device name.                                                                                                                                                                                                                                                                                                                                                                                                                          |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   |                 |                 |                 | .. note::                                                                                                                                                                                                                                                                                                                                                                                                                                                |
   |                 |                 |                 |                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   |                 |                 |                 |    -  The new disk device name cannot be the same as an existing one.                                                                                                                                                                                                                                                                                                                                                                                    |
   |                 |                 |                 |    -  This parameter is mandatory for Xen ECSs. Set the parameter value to **/dev/sda** for the system disks of such ECSs and to **/dev/sd**\ *x* for data disks, where *x* is a letter in alphabetical order. For example, if there are two data disks, set the device names of the two data disks to **/dev/sdb** and **/dev/sdc**, respectively. If you set a device name starting with **/dev/vd**, the system uses **/dev/sd** by default.          |
   |                 |                 |                 |    -  For KVM ECSs, set the parameter value to **/dev/vda** for system disks. The device names for data disks of KVM ECSs are optional. If the device names of data disks are required, set them in alphabetical order. For example, if there are two data disks, set the device names of the two data disks to **/dev/vdb** and **/dev/vdc**, respectively. If you set a device name starting with **/dev/sd**, the system uses **/dev/vd** by default. |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

For details, see :ref:`Responses (Task) <en-us_topic_0022067714>`.

Example Request
---------------

.. code-block:: text

   POST https://{endpoint}/v1/{project_id}/batchaction/attachvolumes/{volume_id}

.. code-block::

   {
       "serverinfo": [
           {
               "server_id": "a26887c6-c47b-4654-abb5-dfadf7d3f803",
               "device": "/dev/sdb"
           },
           {
               "server_id": "a26887c6-c47b-4654-abb5-dfadf7d3fa05",
               "device": "/dev/sdb"
           }
       ]
   }

Example Response
----------------

.. code-block::

   {
       "job_id": "70a599e0-31e7-49b7-b260-868f441e862b"
   }

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.

Error Codes
-----------

See :ref:`Error Codes <en-us_topic_0022067717>`.
