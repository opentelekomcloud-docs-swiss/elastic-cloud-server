:original_name: en-us_topic_0161341998.html

.. _en-us_topic_0161341998:

Password Management
===================

+-------------------------------------------------------------------------------------------+---------------------------------------------------------------------+---------------------------------+--------------+-------------+--------------------+
| Permission                                                                                | API                                                                 | Action                          | Dependencies | IAM Project | Enterprise Project |
+===========================================================================================+=====================================================================+=================================+==============+=============+====================+
| Resetting the password for logging in to an ECS with a few clicks for enterprise projects | PUT /v1/{project_id}/cloudservers/{server_id}/os-reset-password     | ecs:cloudServers:resetServerPwd | ``-``        | Supported   | Supported          |
+-------------------------------------------------------------------------------------------+---------------------------------------------------------------------+---------------------------------+--------------+-------------+--------------------+
| Displaying whether an ECS supports password reset                                         | GET /v1/{project_id}/cloudservers/{server_id}/os-resetpwd-flag      | ecs:cloudServers:get            | ``-``        | Supported   | Supported          |
+-------------------------------------------------------------------------------------------+---------------------------------------------------------------------+---------------------------------+--------------+-------------+--------------------+
| Obtaining the password for logging in to a Windows ECS                                    | GET /v1/{project_id}/cloudservers/{server_id}/os-server-password    | ecs:cloudServers:get            | ``-``        | Supported   | Supported          |
+-------------------------------------------------------------------------------------------+---------------------------------------------------------------------+---------------------------------+--------------+-------------+--------------------+
| Deleting the password for logging in to a Windows ECS                                     | DELETE /v1/{project_id}/cloudservers/{server_id}/os-server-password | ecs:cloudServers:deletePassword | ``-``        | Supported   | Supported          |
+-------------------------------------------------------------------------------------------+---------------------------------------------------------------------+---------------------------------+--------------+-------------+--------------------+
| Resetting the password for logging in to an ECS with a few clicks                         | PUT /v2.1/{project_id}/servers/{server_id}/os-reset-password        | ecs:cloudServers:resetServerPwd | ``-``        | Supported   | Not supported      |
+-------------------------------------------------------------------------------------------+---------------------------------------------------------------------+---------------------------------+--------------+-------------+--------------------+
| Obtaining the password for logging in to a Windows ECS (native OpenStack)                 | GET /v2.1/{project_id}/servers/{server_id}/os-server-password       | ecs:serverPasswords:manage      | ``-``        | Supported   | Not supported      |
+-------------------------------------------------------------------------------------------+---------------------------------------------------------------------+---------------------------------+--------------+-------------+--------------------+
| Deleting the password for logging in to a Windows ECS (native OpenStack)                  | DELETE /v2.1/{project_id}/servers/{server_id}/os-server-password    | ecs:serverPasswords:manage      | ``-``        | Supported   | Not supported      |
+-------------------------------------------------------------------------------------------+---------------------------------------------------------------------+---------------------------------+--------------+-------------+--------------------+
