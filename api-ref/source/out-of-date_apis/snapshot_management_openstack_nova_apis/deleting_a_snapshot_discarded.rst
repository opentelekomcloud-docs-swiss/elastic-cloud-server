:original_name: en-us_topic_0065817727.html

.. _en-us_topic_0065817727:

Deleting a Snapshot (Discarded)
===============================

Function
--------

This API is used to delete a volume snapshot.

This API has been discarded. Use the EVS API "Deleting an EVS Snapshot (OpenStack Cinder API v2)".

URI
---

DELETE /v2.1/{project_id}/os-snapshots/{snapshot_id}

:ref:`Table 1 <en-us_topic_0065817727__en-us_topic_0057973217_table2814978410562>` describes the parameters in the URI.

.. _en-us_topic_0065817727__en-us_topic_0057973217_table2814978410562:

.. table:: **Table 1** Parameter description

   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | Parameter             | Mandatory             | Description                                                                                         |
   +=======================+=======================+=====================================================================================================+
   | project_id            | Yes                   | Specifies the project ID.                                                                           |
   |                       |                       |                                                                                                     |
   |                       |                       | For details about how to obtain the ID, see :ref:`Obtaining a Project ID <en-us_topic_0022670701>`. |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+
   | snapshot_id           | Yes                   | Specifies the volume snapshot ID.                                                                   |
   +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------+

Request
-------

None

Response
--------

None

Example Request
---------------

.. code-block:: text

   DELETE https://{endpoint}/v2.1/d6c277ba8820452e83df36f33c9fa561/os-snapshots/74bfbbdd-7af5-4ed5-81b2-0aed668441d6

Example Response
----------------

None

Returned Values
---------------

See :ref:`Returned Values for General Requests <en-us_topic_0022067716>`.
