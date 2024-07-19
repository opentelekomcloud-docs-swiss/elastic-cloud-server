:original_name: en-us_topic_0077841586.html

.. _en-us_topic_0077841586:

Changing an ECS OS (Using an Image Without Cloud-Init Installed)
================================================================

Function
--------

This API is used to change the OS of an ECS.

This API is an asynchronous API. After the OS change request is successfully delivered, a job ID is returned. This does not mean the OS change is complete. You need to call the API by referring to :ref:`Querying Task Execution Status <en-us_topic_0022225398>` to query the job status. The SUCCESS status indicates that the OS change is successful.

After this API is called, the system uninstalls the system disk, uses the new image to create a system disk, and attaches it to the ECS. In this way, the OS is changed.

This API supports the images without Cloud-Init or Cloudbase-Init installed. Otherwise, use the API described in :ref:`Changing an ECS OS (Using an Image with Cloud-Init Installed) <en-us_topic_0067876971>`.

Constraints
-----------

-  Only an ECS with a system disk supports changing OS.
-  You are not allowed to perform other operations when changing the OS. Otherwise, changing the OS will fail.

URI
---

POST /v1/{project_id}/cloudservers/{server_id}/changeos

:ref:`Table 1 <en-us_topic_0077841586__table55945983>` describes the parameters in the URI.

.. _en-us_topic_0077841586__table55945983:

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

:ref:`Table 2 <en-us_topic_0077841586__table2840889>` describes the request parameters.

.. _en-us_topic_0077841586__table2840889:

.. table:: **Table 2** Request parameters

   +-----------+-----------+--------+----------------------------------------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                                                        |
   +===========+===========+========+====================================================================================================+
   | os-change | Yes       | Object | Changes the OS of an ECS. For details, see :ref:`Table 3 <en-us_topic_0077841586__table32200631>`. |
   +-----------+-----------+--------+----------------------------------------------------------------------------------------------------+

.. _en-us_topic_0077841586__table32200631:

.. table:: **Table 3** **os-change** field description

   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                                                                                 |
   +=================+=================+=================+=============================================================================================================================================================================================================+
   | keyname         | Yes             | String          | Specifies the key name.                                                                                                                                                                                     |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | userid          | No              | String          | Specifies the user ID. When the **keyname** parameter is being specified, the value of this parameter is used preferentially. If this parameter is left blank, the user ID in the token is used by default. |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | imageid         | Yes             | String          | Specifies the ID of the new image in UUID format.                                                                                                                                                           |
   |                 |                 |                 |                                                                                                                                                                                                             |
   |                 |                 |                 | You can obtain the image ID from the console or by following the instructions provided in "Querying Images" in *Image Management Service API Reference*.                                                    |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | metadata        | No              | Object          | Specifies the metadata of the ECS for which the OS is to be changed.                                                                                                                                        |
   |                 |                 |                 |                                                                                                                                                                                                             |
   |                 |                 |                 | For more information, see :ref:`Table 4 <en-us_topic_0077841586__table9120223>`.                                                                                                                            |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | mode            | No              | String          | Specifies whether the ECS supports OS change when the ECS is running.                                                                                                                                       |
   |                 |                 |                 |                                                                                                                                                                                                             |
   |                 |                 |                 | If the parameter value is **withStopServer**, the ECS supports OS change when the ECS is running. In such a case, the system automatically stops the ECS before changing its OS.                            |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _en-us_topic_0077841586__table9120223:

.. table:: **Table 4** **metadata** field description

   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                                                                                     |
   +=================+=================+=================+=================================================================================================================================================+
   | BYOL            | No              | String          | Specifies whether a user has the license of an image.                                                                                           |
   |                 |                 |                 |                                                                                                                                                 |
   |                 |                 |                 | -  If this parameter is set to **true**, the license file delivered with the image is used, indicating that BYOL is used.                       |
   |                 |                 |                 | -  If this parameter is set to a value other than **true**, BYOL is not used, and the license file provided by the cloud platform must be used. |
   |                 |                 |                 |                                                                                                                                                 |
   |                 |                 |                 | The default value is not **true**, indicating that BYOL is not used.                                                                            |
   +-----------------+-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

For details, see :ref:`Responses (Task) <en-us_topic_0022067714>`.

Example Request
---------------

Change the OS and use the key pair for login authentication after the OS change.

.. code-block:: text

   POST https://{endpoint}/v1/{project_id}/cloudservers/{server_id}/changeos

   {
       "os-change": {
           "keyname": "KeyPair-350b",
           "userid": "7e25b1da389f4697a79df3a0e5bd494e",
           "imageid": "e215580f-73ad-429d-b6f2-5433947433b0",
           "mode": "withStopServer"
       }
   }

Example Response
----------------

See :ref:`Responses (Task) <en-us_topic_0022067714>`.

.. code-block::

   {
       "job_id": "ff80808288d41e1b018990260955686a"
   }

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.

Error Codes
-----------

See :ref:`Error Codes <en-us_topic_0022067717>`.
