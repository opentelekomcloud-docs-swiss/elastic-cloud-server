:original_name: en-us_topic_0065817713.html

.. _en-us_topic_0065817713:

Querying ECS Metadata
=====================

Function
--------

This API is used to query ECS metadata.

URI
---

GET /v2.1/{project_id}/servers/{server_id}/metadata

:ref:`Table 1 <en-us_topic_0065817713__en-us_topic_0057973165_table32475667>` describes the parameters in the URI.

.. _en-us_topic_0065817713__en-us_topic_0057973165_table32475667:

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

.. note::

   Pagination query is not supported.

Request
-------

None

Response
--------

:ref:`Table 2 <en-us_topic_0065817713__en-us_topic_0057973165_table48538422>` describes the response parameters.

.. _en-us_topic_0065817713__en-us_topic_0057973165_table48538422:

.. table:: **Table 2** Response parameters

   +-----------+-----------+--------+-----------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                         |
   +===========+===========+========+=====================================================+
   | metadata  | Yes       | Object | Specifies the user-defined metadata key-value pair. |
   +-----------+-----------+--------+-----------------------------------------------------+

Example Request
---------------

Query metadata details of a specified ECS.

.. code-block:: text

   GET https://{endpoint}/v2.1/9c53a566cb3443ab910cf0daebca90c4/servers/998af54b-5762-4041-abc1-f98a2c27b3a2/metadata

Example Response
----------------

.. code-block::

   {
       "metadata": {
           "wj": "True"
       }
   }

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.
