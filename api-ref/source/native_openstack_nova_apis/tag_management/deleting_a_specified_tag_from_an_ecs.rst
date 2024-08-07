:original_name: en-us_topic_0065820827.html

.. _en-us_topic_0065820827:

Deleting a Specified Tag from an ECS
====================================

This API is used to delete a specified tag from an ECS.

You are required to use the HTTP header **X-OpenStack-Nova-API-Version: 2.26** to specify the microversion on the client.

Constraints
-----------

-  The tag contains a maximum of 80 characters.
-  If a tag contains non-URL-safe characters, perform URL encoding.

URI
---

DELETE /v2.1/{project_id}/servers/{server_id}/tags/{tag}

:ref:`Table 1 <en-us_topic_0065820827__en-us_topic_0057972842_table536172734712>` describes the parameters in the URI.

.. _en-us_topic_0065820827__en-us_topic_0057972842_table536172734712:

.. table:: **Table 1** Parameter description

   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory             | Description                                                                                              |
   +=======================+=======================+==========================================================================================================+
   | project_id            | Yes                   | Specifies the project ID.                                                                                |
   |                       |                       |                                                                                                          |
   |                       |                       | For details about how to obtain the ID, see :ref:`Obtaining a Project ID <en-us_topic_0022670701>`.      |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------+
   | server_id             | Yes                   | Specifies the ECS ID.                                                                                    |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------+
   | tag                   | Yes                   | Specifies the key of the tag to be deleted. If no key is specified, all tags of the ECS will be deleted. |
   +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------+

Request
-------

None

Response
--------

None

Example Request
---------------

Delete a specified tag from a specified ECS.

.. code-block:: text

   DELETE https://{endpoint}/v2.1/{project_id}/servers/{server_id}/tags/{tag}

Example Response
----------------

None

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.
