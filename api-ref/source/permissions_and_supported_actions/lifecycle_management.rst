:original_name: en-us_topic_0103071510.html

.. _en-us_topic_0103071510:

Lifecycle Management
====================

+------------------------------------------------------+-----------------------------------------------+----------------------------+----------------------------+-------------+--------------------+
| Permission                                           | API                                           | Action                     | Dependencies               | IAM Project | Enterprise Project |
+======================================================+===============================================+============================+============================+=============+====================+
| Creating an ECS                                      | POST /v1/{project_id}/cloudservers            | -  Assigning a New EIP     | -  Assigning a New EIP     | Supported   | Supported          |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |    ecs:cloudServers:create |    vpc:publicIps:create    |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               | -  Using an Existing EIP   | -  Using an Existing EIP   |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |    ecs:cloudServers:create |    vpc:publicIps:update    |             |                    |
+------------------------------------------------------+-----------------------------------------------+----------------------------+----------------------------+-------------+--------------------+
| Deleting ECSs                                        | POST /v1/{project_id}/cloudservers/delete     | ecs:cloudServers:delete    | ``-``                      | Supported   | Supported          |
+------------------------------------------------------+-----------------------------------------------+----------------------------+----------------------------+-------------+--------------------+
| Displaying details about ECSs                        | GET /v1/{project_id}/cloudservers/detail      | ecs:cloudServers:list      | ``-``                      | Supported   | Supported          |
+------------------------------------------------------+-----------------------------------------------+----------------------------+----------------------------+-------------+--------------------+
| Displaying details about an ECS                      | GET /v1/{project_id}/cloudservers/{server_id} | ecs:cloudServers:get       | ``-``                      | Supported   | Supported          |
+------------------------------------------------------+-----------------------------------------------+----------------------------+----------------------------+-------------+--------------------+
| Modifying an ECS                                     | PUT /v1/{project_id}/cloudservers/{server_id} | ecs:cloudServers:put       | ``-``                      | Supported   | Supported          |
+------------------------------------------------------+-----------------------------------------------+----------------------------+----------------------------+-------------+--------------------+
| Querying details about ECSs (native OpenStack API)   | GET /v2.1/{project_id}/servers/detail         | ecs:servers:list           | ecs:servers:get            | Supported   | Not supported      |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | ecs:serverVolumes:use      |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | ecs:diskConfigs:use        |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | ecs:securityGroups:use     |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | ecs:serverKeypairs:get     |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:securityGroups:get     |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:securityGroupRules:get |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:networks:get           |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:subnets:get            |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:ports:get              |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:routers:get            |             |                    |
+------------------------------------------------------+-----------------------------------------------+----------------------------+----------------------------+-------------+--------------------+
| Querying ECSs (native OpenStack API)                 | GET /v2.1/{project_id}/servers                | ecs:servers:list           | ``-``                      | Supported   | Not supported      |
+------------------------------------------------------+-----------------------------------------------+----------------------------+----------------------------+-------------+--------------------+
| Querying details about an ECS (native OpenStack API) | GET /v2.1/{project_id}/servers/{server_id}    | ecs:servers:get            | ecs:serverVolumes:use      | Supported   | Not supported      |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | ecs:diskConfigs:use        |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | ecs:securityGroups:use     |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | ecs:serverKeypairs:get     |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:securityGroups:get     |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:securityGroupRules:get |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:networks:get           |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:subnets:get            |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:ports:get              |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:routers:get            |             |                    |
+------------------------------------------------------+-----------------------------------------------+----------------------------+----------------------------+-------------+--------------------+
| Creating an ECS (native OpenStack API)               | POST /v2.1/{project_id}/servers               | ecs:servers:create         | ecs:servers:get            | Supported   | Not supported      |
|                                                      |                                               |                            |                            |             |                    |
|                                                      | POST /v2.1/{project_id}/os-volumes_boot       |                            | ecs:serverInterfaces:use   |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | ecs:serverInterfaces:get   |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | ecs:flavors:get            |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | ecs:securityGroups:use     |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | evs:volumes:list           |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | evs:volumes:get            |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | evs:volumes:create         |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | evs:volumes:attach         |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | evs:volumes:manage         |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:securityGroups:get     |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:networks:get           |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:networks:update        |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:subnets:get            |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:subnets:update         |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:ports:create           |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:ports:update           |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:ports:get              |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:ports:delete           |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:networks:create        |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:subnets:create         |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:routers:get            |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | vpc:routers:update         |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | ims:images:list            |             |                    |
|                                                      |                                               |                            |                            |             |                    |
|                                                      |                                               |                            | ims:images:get             |             |                    |
+------------------------------------------------------+-----------------------------------------------+----------------------------+----------------------------+-------------+--------------------+
| Deleting an ECS (native OpenStack API)               | DELETE /v2.1/{project_id}/servers/{server_id} | ecs:servers:delete         | ``-``                      | Supported   | Not supported      |
+------------------------------------------------------+-----------------------------------------------+----------------------------+----------------------------+-------------+--------------------+
| Modifying an ECS (native OpenStack API)              | PUT /v2.1/{project_id}/servers/{server_id}    | ecs:servers:update         | ecs:servers:get            | Supported   | Not supported      |
+------------------------------------------------------+-----------------------------------------------+----------------------------+----------------------------+-------------+--------------------+
