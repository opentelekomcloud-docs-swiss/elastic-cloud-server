:original_name: en-us_topic_0065820822.html

.. _en-us_topic_0065820822:

Querying Tags of an ECS
=======================

This API is used to query all tags of an ECS.

You are required to use the HTTP header **X-OpenStack-Nova-API-Version: 2.26** to specify the microversion on the client.

URI
---

GET /v2.1/{project_id}/servers/{server_id}/tags

:ref:`Table 1 <en-us_topic_0065820822__en-us_topic_0057972837_table32475667>` describes the parameters in the URI.

.. _en-us_topic_0065820822__en-us_topic_0057972837_table32475667:

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

None

Response
--------

:ref:`Table 2 <en-us_topic_0065820822__en-us_topic_0057972838_table28387752>` describes the response parameters.

.. _en-us_topic_0065820822__en-us_topic_0057972838_table28387752:

.. table:: **Table 2** Response parameters

   ========= ================ ===================
   Parameter Type             Description
   ========= ================ ===================
   tags      Array of strings Specifies ECS tags.
   ========= ================ ===================

Example Request
---------------

.. code-block:: text

   GET https://{endpoint}/v2.1/{project_id}/servers/{server_id}/tags

Example Response
----------------

Example response

.. code-block::

   {
       "tags": ["baz=xyy", "foo", "qux"]
   }

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.
