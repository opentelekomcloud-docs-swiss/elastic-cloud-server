:original_name: en-us_topic_0065820826.html

.. _en-us_topic_0065820826:

Querying a Specified Tag for an ECS
===================================

This API is used to query whether an ECS has a specified tag.

You are required to use the HTTP header **X-OpenStack-Nova-API-Version: 2.26** to specify the microversion on the client.

URI
---

GET /v2.1/{project_id}/servers/{server_id}/tags/{tag}

:ref:`Table 1 <en-us_topic_0065820826__en-us_topic_0057972841_table32475667>` describes the parameters in the URI.

.. _en-us_topic_0065820826__en-us_topic_0057972841_table32475667:

.. table:: **Table 1** Parameter description

   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory             | Description                                                                                                |
   +=======================+=======================+============================================================================================================+
   | project_id            | Yes                   | Specifies the project ID.                                                                                  |
   |                       |                       |                                                                                                            |
   |                       |                       | For details about how to obtain the ID, see :ref:`Obtaining a Project ID <en-us_topic_0022670701>`.        |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------+
   | server_id             | Yes                   | Specifies the ECS ID.                                                                                      |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------+
   | tag                   | Yes                   | Specifies the key of the tag to be queried. If no key is specified, all tags of the ECS will be displayed. |
   +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------+

Request
-------

None

Response
--------

None

Example Request
---------------

Query whether an ECS has a specified tag.

.. code-block:: text

   GET https://{endpoint}/v2.1/{project_id}/servers/{server_id}/tags/{tag}

Example Response
----------------

None

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.
