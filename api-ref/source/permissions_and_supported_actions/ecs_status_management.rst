:original_name: en-us_topic_0103071511.html

.. _en-us_topic_0103071511:

ECS Status Management
=====================

+---------------------------------------------------------------+------------------------------------------------------------+---------------------------+--------------------+-------------+--------------------+
| Permission                                                    | API                                                        | Action                    | Dependencies       | IAM Project | Enterprise Project |
+===============================================================+============================================================+===========================+====================+=============+====================+
| Changing an ECS OS                                            | POST /v2/{project_id}/cloudservers/{server_id}/changeos    | ecs:cloudServers:changeOS | ``-``              | Supported   | Supported          |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               | POST /v1/{project_id}/cloudservers/{server_id}/changeos    |                           |                    |             |                    |
+---------------------------------------------------------------+------------------------------------------------------------+---------------------------+--------------------+-------------+--------------------+
| Reinstalling an ECS OS                                        | POST /v2/{project_id}/cloudservers/{server_id}/reinstallos | ecs:cloudServers:rebuild  | ``-``              | Supported   | Supported          |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               | POST /v1/{project_id}/cloudservers/{server_id}/reinstallos |                           |                    |             |                    |
+---------------------------------------------------------------+------------------------------------------------------------+---------------------------+--------------------+-------------+--------------------+
| Modifying the specifications of an ECS                        | POST /v1/{project_id}/cloudservers/{server_id}/resize      | ecs:cloudServers:resize   | ``-``              | Supported   | Supported          |
+---------------------------------------------------------------+------------------------------------------------------------+---------------------------+--------------------+-------------+--------------------+
| Starting an ECS (native OpenStack API)                        | POST /v2.1/{project_id}/servers/{server_id}/action         | ecs:servers:start         | ecs:servers:list   | Supported   | Not supported      |
+---------------------------------------------------------------+------------------------------------------------------------+---------------------------+--------------------+-------------+--------------------+
| Stopping an ECS (native OpenStack API)                        | POST /v2.1/{project_id}/servers/{server_id}/action         | ecs:servers:stop          | ecs:servers:list   | Supported   | Not supported      |
+---------------------------------------------------------------+------------------------------------------------------------+---------------------------+--------------------+-------------+--------------------+
| Restarting an ECS (native OpenStack API)                      | POST /v2.1/{project_id}/servers/{server_id}/action         | ecs:servers:reboot        | ecs:servers:list   | Supported   | Not supported      |
+---------------------------------------------------------------+------------------------------------------------------------+---------------------------+--------------------+-------------+--------------------+
| Modifying the specifications of an ECS (native OpenStack API) | POST /v2.1/{project_id}/servers/{server_id}/action         | ecs:servers:resize        | ecs:servers:list   | Supported   | Not supported      |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               |                                                            |                           | ecs:flavors:get    |             |                    |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               |                                                            |                           | ims:images:get     |             |                    |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               |                                                            |                           | evs:volumes:list   |             |                    |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               |                                                            |                           | evs:volumes:create |             |                    |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               |                                                            |                           | evs:volumes:get    |             |                    |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               |                                                            |                           | evs:volumes:attach |             |                    |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               |                                                            |                           | evs:volumes:detach |             |                    |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               |                                                            |                           | evs:volumes:manage |             |                    |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               |                                                            |                           | vpc:ports:get      |             |                    |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               |                                                            |                           | vpc:ports:update   |             |                    |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               |                                                            |                           | vpc:ports:create   |             |                    |
|                                                               |                                                            |                           |                    |             |                    |
|                                                               |                                                            |                           | vpc:ports:delete   |             |                    |
+---------------------------------------------------------------+------------------------------------------------------------+---------------------------+--------------------+-------------+--------------------+
| Locking an ECS (native OpenStack API)                         | POST /v2.1/{project_id}/servers/{server_id}/action         | ecs:servers:lock          | ecs:servers:list   | Supported   | Not supported      |
+---------------------------------------------------------------+------------------------------------------------------------+---------------------------+--------------------+-------------+--------------------+
| Unlocking an ECS (native OpenStack API)                       | POST /v2.1/{project_id}/servers/{server_id}/action         | ecs:servers:unlock        | ecs:servers:list   | Supported   | Not supported      |
+---------------------------------------------------------------+------------------------------------------------------------+---------------------------+--------------------+-------------+--------------------+
