:original_name: en-us_topic_0103071521.html

.. _en-us_topic_0103071521:

Tag Management
==============

+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
| Permission                                                  | API                                                        | Action               | Dependencies    | IAM Project | Enterprise Project |
+=============================================================+============================================================+======================+=================+=============+====================+
| Adding or deleting tags to or from an ECS in a batch        | POST /v1/{project_id}/cloudservers/{server_id}/tags/action | ecs:cloudServers:put | ``-``           | Supported   | Supported          |
+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
| Querying project tags                                       | GET /v1/{project_id}/cloudservers/tags                     | ecs:cloudServers:lis | ``-``           | Supported   | Supported          |
+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
| Querying tags of an ECS                                     | GET /v1/{project_id}/cloudservers/{server_id}/tags         | ecs:cloudServers:get | ``-``           | Supported   | Supported          |
+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
| Adding tags in a batch                                      | POST /v1/{project_id}/servers/{server_id}/tags/action      | ecs:servers:setTags  | ``-``           | Supported   | Not supported      |
|                                                             |                                                            |                      |                 |             |                    |
| Deleting Tags in a Batch                                    |                                                            |                      |                 |             |                    |
+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
| Querying ECSs by tag                                        | POST /v1/{project_id}/servers/resource_instances/action    | ecs:servers:getTags  | ``-``           | Supported   | Not supported      |
+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
| Querying project tags                                       | GET /v1/{project_id}/servers/tags                          | ecs:servers:getTags  | ``-``           | Supported   | Not supported      |
+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
| Querying tags of an ECS                                     | GET /v1/{project_id}/servers/{server_id}/tags              | ecs:servers:getTags  | ``-``           | Supported   | Not supported      |
+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
| Querying tags of a specified ECS (native OpenStack API)     | GET /v2.1/{project_id}/servers/{server_id}/tags            | ecs:servers:getTags  | ecs:servers:get | Supported   | Not supported      |
+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
| Adding a tag to an ECS (native OpenStack API)               | PUT /v2.1/{project_id}/servers/{server_id}/tags/{tag}      | ecs:servers:setTags  | ecs:servers:get | Supported   | Not supported      |
+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
| Creating an ECS tag (native OpenStack API)                  | PUT /v2.1/{project_id}/servers/{server_id}/tags            | ecs:servers:setTags  | ecs:servers:get | Supported   | Not supported      |
+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
| Deleting a specified tag from an ECS (native OpenStack API) | DELETE /v2.1/{project_id}/servers/{server_id}/tags/{tag}   | ecs:servers:setTags  | ecs:servers:get | Supported   | Not supported      |
+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
| Querying an ECS tag (native OpenStack API)                  | GET /v2.1/{project_id}/servers/{server_id}/tags/{tag}      | ecs:servers:getTags  | ecs:servers:get | Supported   | Not supported      |
+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
| Deleting all ECS tags (native OpenStack API)                | DELETE /v2.1/{project_id}/servers/{server_id}/tags         | ecs:servers:setTags  | ecs:servers:get | Supported   | Not supported      |
+-------------------------------------------------------------+------------------------------------------------------------+----------------------+-----------------+-------------+--------------------+
