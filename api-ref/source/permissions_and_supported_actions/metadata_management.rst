:original_name: en-us_topic_0103071516.html

.. _en-us_topic_0103071516:

Metadata Management
===================

+----------------------------------------------------------------------+--------------------------------------------------------------+---------------------------------+-----------------+-------------+--------------------+
| Permission                                                           | API                                                          | Action                          | Dependencies    | IAM Project | Enterprise Project |
+======================================================================+==============================================================+=================================+=================+=============+====================+
| Querying ECS metadata (native OpenStack API)                         | GET /v2.1/{project_id}/servers/{server_id}/metadata          | ecs:servers:listMetadata        | ``-``           | Supported   | Not supported      |
+----------------------------------------------------------------------+--------------------------------------------------------------+---------------------------------+-----------------+-------------+--------------------+
| Querying metadata of an ECS key (native OpenStack API)               | GET /v2.1/{project_id}/servers/{server_id}/metadata/{key}    | ecs:servers:getMetadata         | ecs:servers:get | Supported   | Not supported      |
+----------------------------------------------------------------------+--------------------------------------------------------------+---------------------------------+-----------------+-------------+--------------------+
| Deleting specified ECS metadata (native OpenStack API)               | DELETE /v2.1/{project_id}/servers/{server_id}/metadata/{key} | ecs:servers:setMetadata         | ``-``           | Supported   | Not supported      |
+----------------------------------------------------------------------+--------------------------------------------------------------+---------------------------------+-----------------+-------------+--------------------+
| Modifying the key value in metadata of an ECS (native OpenStack API) | PUT /v2.1/{project_id}/servers/{server_id}/metadata/{key}    | ecs:servers:setMetadata         | ``-``           | Supported   | Not supported      |
+----------------------------------------------------------------------+--------------------------------------------------------------+---------------------------------+-----------------+-------------+--------------------+
| Updating ECS metadata (native OpenStack API)                         | POST /v2.1/{project_id}/servers/{server_id}/metadata         | ecs:servers:setMetadata         | ``-``           | Supported   | Not supported      |
+----------------------------------------------------------------------+--------------------------------------------------------------+---------------------------------+-----------------+-------------+--------------------+
| Configuring ECS metadata (native OpenStack API)                      | PUT /v2.1/{project_id}/servers/{server_id}/metadata          | ecs:servers:setMetadata         | ecs:servers:get | Supported   | Not supported      |
+----------------------------------------------------------------------+--------------------------------------------------------------+---------------------------------+-----------------+-------------+--------------------+
| Updating ECS metadata                                                | POST /v1/{project_id}/cloudservers/{server_id}/metadata      | ecs:cloudServers:updateMetadata | ``-``           | Supported   | Supported          |
+----------------------------------------------------------------------+--------------------------------------------------------------+---------------------------------+-----------------+-------------+--------------------+
