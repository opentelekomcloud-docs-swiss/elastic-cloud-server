:original_name: en-us_topic_0142523658.html

.. _en-us_topic_0142523658:

Modifying ECSs in a Batch
=========================

Function
--------

This API is used to modify ECSs in a batch.

Only ECS names can be changed in a batch, and the maximum number is 1000 at a time.

URI
---

PUT /v1/{project_id}/cloudservers/server-name

:ref:`Table 1 <en-us_topic_0142523658__table32475667>` lists the URI parameters.

.. _en-us_topic_0142523658__table32475667:

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

:ref:`Table 2 <en-us_topic_0142523658__table41782128362>` describes the request parameters.

.. _en-us_topic_0142523658__table41782128362:

.. table:: **Table 2** Request parameters

   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type             | Mandatory       | Description                                                                                                                                                                                                                                                                                                         |
   +=================+==================+=================+=====================================================================================================================================================================================================================================================================================================================+
   | name            | String           | Yes             | Specifies the changed name of the ECSs.                                                                                                                                                                                                                                                                             |
   |                 |                  |                 |                                                                                                                                                                                                                                                                                                                     |
   |                 |                  |                 | The rules are as follows:                                                                                                                                                                                                                                                                                           |
   |                 |                  |                 |                                                                                                                                                                                                                                                                                                                     |
   |                 |                  |                 | Consists of a maximum of 64 characters, including uppercase letters, lowercase letters, digits, hyphens (-), and underscores (_).                                                                                                                                                                                   |
   |                 |                  |                 |                                                                                                                                                                                                                                                                                                                     |
   |                 |                  |                 | After you change ECS names in a batch, the system does not automatically add a digital suffix to the changed names. For example, there are three ECSs, **test_0001**, **test_0002**, and **test_0003**. After their names are changed to **develop** in a batch, their changed names are all **develop**.           |
   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dry_run         | Boolean          | No              | Specifies whether to check the request and change ECS names.                                                                                                                                                                                                                                                        |
   |                 |                  |                 |                                                                                                                                                                                                                                                                                                                     |
   |                 |                  |                 | **true**: indicates that only the name change request is sent and the names of the ECSs will not be changed. Check items include mandatory parameters, request format, and service restrictions. If the check fails, the system returns an error. If the check result is as expected, the system properly responds. |
   |                 |                  |                 |                                                                                                                                                                                                                                                                                                                     |
   |                 |                  |                 | See :ref:`Responses (Batch Operation) <en-us_topic_0142195139>`.                                                                                                                                                                                                                                                    |
   |                 |                  |                 |                                                                                                                                                                                                                                                                                                                     |
   |                 |                  |                 | **false**: indicates that the name change request is sent and the ECS names will be changed if the check result is as expected.                                                                                                                                                                                     |
   |                 |                  |                 |                                                                                                                                                                                                                                                                                                                     |
   |                 |                  |                 | The default value is **false**.                                                                                                                                                                                                                                                                                     |
   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | servers         | Array of objects | Yes             | Specifies the IDs of the target ECSs. For details, see :ref:`Table 3 <en-us_topic_0142523658__table18857142453714>`.                                                                                                                                                                                                |
   +-----------------+------------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _en-us_topic_0142523658__table18857142453714:

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

.. code-block:: text

   PUT https://{endpoint}/v1/{project_id}/cloudservers/server-name

.. code-block::

   {
      "name": "new-server-name",
      "dry_run": false,
      "servers": [
                  {
                    "id":"260a0917-f7df-4b25-93ac-950da6c6b5d6"
                  },
                  {
                    "id":"f6d8df1a-e257-48e2-b617-1dd92ced8c20"
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
