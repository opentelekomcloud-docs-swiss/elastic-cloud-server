:original_name: en-us_topic_0077841398.html

.. _en-us_topic_0077841398:

Reinstalling an ECS OS (Using an Image Without Cloud-Init Installed)
====================================================================

Function
--------

This API is used to reinstall an ECS OS.

After this API is called, the system uninstalls the system disk, uses the original image to create a system disk, and attaches it to the ECS. In this way, the OS is reinstalled.

This API supports the images without Cloud-Init or Cloudbase-Init installed. Otherwise, use the API described in :ref:`Reinstalling an ECS OS (Using an Image with Cloud-Init Installed) <en-us_topic_0067876349>`.

Constraints
-----------

-  You cannot reinstall OS on an ECS that does not have the system disk.
-  You are not allowed to perform other operations when reinstalling the OS. Otherwise, reinstalling the OS will fail.

URI
---

POST /v1/{project_id}/cloudservers/{server_id}/reinstallos

:ref:`Table 1 <en-us_topic_0077841398__table55945983>` describes the parameters in the URI.

.. _en-us_topic_0077841398__table55945983:

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

:ref:`Table 2 <en-us_topic_0077841398__table2840889>` describes the request parameters.

.. _en-us_topic_0077841398__table2840889:

.. table:: **Table 2** Request parameters

   +--------------+-----------+--------+---------------------------------------------------------------------------------------------+
   | Parameter    | Mandatory | Type   | Description                                                                                 |
   +==============+===========+========+=============================================================================================+
   | os-reinstall | Yes       | Object | Reinstall the ECS. For details, see :ref:`Table 3 <en-us_topic_0077841398__table32200631>`. |
   +--------------+-----------+--------+---------------------------------------------------------------------------------------------+

.. _en-us_topic_0077841398__table32200631:

.. table:: **Table 3** **os-reinstall** field description

   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                  |
   +=================+=================+=================+==============================================================================================================================================================================================+
   | keyname         | Yes             | String          | Specifies the key name.                                                                                                                                                                      |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | userid          | Yes             | String          | Specifies the user ID.                                                                                                                                                                       |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | metadata        | No              | Object          | Specifies the metadata of the ECS for which the OS is to be reinstalled.                                                                                                                     |
   |                 |                 |                 |                                                                                                                                                                                              |
   |                 |                 |                 | For more information, see :ref:`Table 4 <en-us_topic_0077841398__table9120223>`.                                                                                                             |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | mode            | No              | String          | Specifies whether the ECS supports OS reinstallation when the ECS is running.                                                                                                                |
   |                 |                 |                 |                                                                                                                                                                                              |
   |                 |                 |                 | If the parameter value is **withStopServer**, the ECS supports OS reinstallation when the ECS is running. In such a case, the system automatically stops the ECS before reinstalling its OS. |
   +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _en-us_topic_0077841398__table9120223:

.. table:: **Table 4** **metadata** field description

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                             |
   +=================+=================+=================+=========================================================================================================================================================+
   | BYOL            | No              | String          | Specifies whether a user has the license of an image.                                                                                                   |
   |                 |                 |                 |                                                                                                                                                         |
   |                 |                 |                 | -  If this parameter is set to **true**, the license file delivered with the image is used, indicating that BYOL is used.                               |
   |                 |                 |                 | -  If this parameter is set to a value other than **true**, BYOL is not used, and the license file provided by the cloud service platform must be used. |
   |                 |                 |                 |                                                                                                                                                         |
   |                 |                 |                 | The default value is not **true**, indicating that BYOL is not used.                                                                                    |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

For details, see :ref:`Responses (Task) <en-us_topic_0022067714>`.

Example Request
---------------

.. code-block:: text

   POST https://{endpoint}/v1/{project_id}/cloudservers/{server_id}/reinstallos

.. code-block::

   {
       "os-reinstall": {
           "keyname": "KeyPair-350b",
           "userid": "7e25b1da389f4697a79df3a0e5bd494e"
       }
   }

Example Response
----------------

See :ref:`Responses (Task) <en-us_topic_0022067714>`.

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
