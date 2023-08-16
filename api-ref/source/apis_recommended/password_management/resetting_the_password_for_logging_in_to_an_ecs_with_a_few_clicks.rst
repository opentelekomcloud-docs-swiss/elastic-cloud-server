:original_name: en-us_topic_0110109377.html

.. _en-us_topic_0110109377:

Resetting the Password for Logging In to an ECS with a Few Clicks
=================================================================

Function
--------

This API is used to reset the password of the ECS management account, **root** or **Administrator**.

Constraints
-----------

-  There is no password complexity check that meets security requirements. No error message is displayed after an insecure password is entered.
-  Before using this API, you must install password reset plug-ins. For instructions about how to download and install the password reset plug-ins, see "Installing One-Click Password Reset Plug-ins" in *Elastic Cloud Server User Guide*.
-  This API cannot detect whether the target ECS supports password reset.
-  If resetting the password for logging in to an ECS failed, this API will not report an error.
-  A new password takes effect after the ECS is started or restarted.
-  This API allows you to reset passwords when the target ECSs are running or stopped.

URI
---

PUT /v2.1/{project_id}/servers/{server_id}/os-reset-password

:ref:`Table 1 <en-us_topic_0110109377__table19484740133714>` describes the parameters in the URI.

.. _en-us_topic_0110109377__table19484740133714:

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

:ref:`Table 2 <en-us_topic_0110109377__table41782128362>` describes the request parameters.

.. _en-us_topic_0110109377__table41782128362:

.. table:: **Table 2** Request parameters

   +----------------+--------+-----------+----------------------------------------------------------------------------------------------------------------------+
   | Parameter      | Type   | Mandatory | Description                                                                                                          |
   +================+========+===========+======================================================================================================================+
   | reset-password | Object | Yes       | Specifies the reset-password details. For details, see :ref:`Table 3 <en-us_topic_0110109377__table18857142453714>`. |
   +----------------+--------+-----------+----------------------------------------------------------------------------------------------------------------------+

.. _en-us_topic_0110109377__table18857142453714:

.. table:: **Table 3** **reset-password** field description

   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                                                                                                      |
   +=================+=================+=================+==================================================================================================================================================+
   | new_password    | String          | Yes             | Specifies the new password for logging in to the ECS.                                                                                            |
   |                 |                 |                 |                                                                                                                                                  |
   |                 |                 |                 | This API does not check password security. Ensure that the password complexity complies with the password rules.                                 |
   |                 |                 |                 |                                                                                                                                                  |
   |                 |                 |                 | The password rules are as follows:                                                                                                               |
   |                 |                 |                 |                                                                                                                                                  |
   |                 |                 |                 | -  Consists of 8 to 26 characters.                                                                                                               |
   |                 |                 |                 | -  Must contain at least three of the following character types:                                                                                 |
   |                 |                 |                 |                                                                                                                                                  |
   |                 |                 |                 |    -  Uppercase letters                                                                                                                          |
   |                 |                 |                 |    -  Lowercase letters                                                                                                                          |
   |                 |                 |                 |    -  Digits                                                                                                                                     |
   |                 |                 |                 |    -  Special characters, including ``!@$%^-_=+[{}]:,./?``                                                                                       |
   |                 |                 |                 |                                                                                                                                                  |
   |                 |                 |                 | -  Cannot contain the username or the username in reverse.                                                                                       |
   |                 |                 |                 | -  Cannot contain more than two characters in the same sequence as they appear in the username. (This requirement applies only to Windows ECSs.) |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------+

Response
--------

None

Example Request
---------------

.. note::

   The password in the request is used as an example. Do not copy it for use.

.. code-block:: text

   PUT https://{endpoint}/v2.1/{project_id}/servers/{server_id}/os-reset-password

.. code-block::

   {
       "reset-password": {
           "new_password": "YNbUwp!dUc9MClnv"
       }
   }

Example Response
----------------

None

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.

Error Codes
-----------

See :ref:`Error Codes <en-us_topic_0022067717>`.
