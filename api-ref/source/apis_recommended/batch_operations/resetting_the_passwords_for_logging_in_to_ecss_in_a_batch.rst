:original_name: en-us_topic_0142258122.html

.. _en-us_topic_0142258122:

Resetting the Passwords for Logging In to ECSs in a Batch
=========================================================

Function
--------

This API is used to reset the passwords of the ECS management account, **root** or **Administrator**, in a batch.

Constraints
-----------

-  Before using this API, you must install password reset plug-ins. For instructions about how to download and install the password reset plug-ins, see "Installing One-Click Password Reset Plug-ins" in *Elastic Cloud Server User Guide*.
-  After the request for resetting the password is issued, this API does not report an error if executing the script failed.
-  A new password takes effect after the ECS is started or restarted.
-  This API allows you to reset passwords when the target ECSs are running or stopped.

URI
---

PUT /v1/{project_id}/cloudservers/os-reset-passwords

:ref:`Table 1 <en-us_topic_0142258122__table32475667>` lists the URI parameters.

.. _en-us_topic_0142258122__table32475667:

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

:ref:`Table 2 <en-us_topic_0142258122__table41782128362>` describes the request parameters.

.. _en-us_topic_0142258122__table41782128362:

.. table:: **Table 2** Request parameters

   +-----------------+------------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type             | Mandatory       | Description                                                                                                                                                                                                                                                                                                                                |
   +=================+==================+=================+============================================================================================================================================================================================================================================================================================================================================+
   | new_password    | String           | Yes             | Specifies the new password.                                                                                                                                                                                                                                                                                                                |
   |                 |                  |                 |                                                                                                                                                                                                                                                                                                                                            |
   |                 |                  |                 | This field is mandatory only if **dry_run** is set to **false**.                                                                                                                                                                                                                                                                           |
   |                 |                  |                 |                                                                                                                                                                                                                                                                                                                                            |
   |                 |                  |                 | A new password must comply with the following rules:                                                                                                                                                                                                                                                                                       |
   |                 |                  |                 |                                                                                                                                                                                                                                                                                                                                            |
   |                 |                  |                 | -  Contain 8 to 26 characters.                                                                                                                                                                                                                                                                                                             |
   |                 |                  |                 | -  Contains at least three of the following character types: uppercase letters, lowercase letters, digits, and special characters (``!@%-_=+[]:./?``).                                                                                                                                                                                     |
   |                 |                  |                 | -  Cannot contain the username or the username spelled backwards.                                                                                                                                                                                                                                                                          |
   |                 |                  |                 | -  For a Windows ECS, the password cannot contain the username, the username spelled backwards., or more than two consecutive characters in the username.                                                                                                                                                                                  |
   +-----------------+------------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dry_run         | Boolean          | No              | Specifies whether to check the request and reset ECS passwords.                                                                                                                                                                                                                                                                            |
   |                 |                  |                 |                                                                                                                                                                                                                                                                                                                                            |
   |                 |                  |                 | -  **true**: indicates that only the password reset request is sent and the passwords for logging in to the ECSs will not be reset. Check items include mandatory parameters, request format, and service restrictions. If the check fails, the system returns an error. If the check result is as expected, the system properly responds. |
   |                 |                  |                 | -  **false**: indicates that only the password reset request is sent and the passwords for logging in to the ECSs will be reset if the check result is as expected.                                                                                                                                                                        |
   |                 |                  |                 |                                                                                                                                                                                                                                                                                                                                            |
   |                 |                  |                 | The default value is **false**.                                                                                                                                                                                                                                                                                                            |
   +-----------------+------------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | servers         | Array of objects | Yes             | Specifies the IDs of the target ECSs. For details, see :ref:`Table 3 <en-us_topic_0142258122__table18857142453714>`.                                                                                                                                                                                                                       |
   +-----------------+------------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _en-us_topic_0142258122__table18857142453714:

.. table:: **Table 3** **servers** field description

   ========= ====== ========= =====================
   Parameter Type   Mandatory Description
   ========= ====== ========= =====================
   id        String Yes       Specifies the ECS ID.
   ========= ====== ========= =====================

Response
--------

See :ref:`Responses (Batch Operation) <en-us_topic_0142195139>`.

Example Request
---------------

.. note::

   The password in the request is used as an example. Do not copy it for use.

.. code-block:: text

   PUT https://{endpoint}/v1/{project_id}/cloudservers/os-reset-passwords

.. code-block::

   {
       "new_password": "YNbUwp!dUc9MClnv",
       "dry_run": true,
       "servers": [
                   {
                     "id":"1bd0eb17-4466-4c15-a9ce-87727ad311b5"
                   },
                   {
                     "id":"fd6b6e9d-64a1-40fa-b7dc-f491be42fdd2"
                   }
                  ]
   }

Example Response
----------------

See :ref:`Responses (Batch Operation) <en-us_topic_0142195139>`.

.. code-block::

   {
       "response": [
                     {
                       "id": "616fb98f-46ca-475e-917e-2563e5a8cd19"
                      },
                     {
                       "id": "516fb98f-46ca-475e-917e-2563e5a8cd12"
                      }
                    ]
   }

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.

Error Codes
-----------

See :ref:`Error Codes <en-us_topic_0022067717>`.
