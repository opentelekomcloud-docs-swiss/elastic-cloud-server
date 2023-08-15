:original_name: en-us_topic_0103072349.html

.. _en-us_topic_0103072349:

Floating IP Address Management
==============================

+---------------------------------------------------------------------+------------------------------------------------------------+---------------------------+------------------------+-------------+--------------------+
| Permission                                                          | API                                                        | Action                    | Dependencies           | IAM Project | Enterprise Project |
+=====================================================================+============================================================+===========================+========================+=============+====================+
| Allocating a floating IP address (native OpenStack API)             | POST /v2.1/{project_id}/os-floating-ips                    | ecs:serverFloatingIps:use | vpc:floatingIps:get    | Supported   | Not supported      |
|                                                                     |                                                            |                           |                        |             |                    |
|                                                                     |                                                            |                           | vpc:floatingIps:create |             |                    |
|                                                                     |                                                            |                           |                        |             |                    |
|                                                                     |                                                            |                           | vpc:floatingIps:update |             |                    |
|                                                                     |                                                            |                           |                        |             |                    |
|                                                                     |                                                            |                           | vpc:ports:get          |             |                    |
+---------------------------------------------------------------------+------------------------------------------------------------+---------------------------+------------------------+-------------+--------------------+
| Querying floating IP addresses (native OpenStack API)               | GET /v2.1/{project_id}/os-floating-ips                     | ecs:serverFloatingIps:use | vpc:floatingIps:get    | Supported   | Not supported      |
|                                                                     |                                                            |                           |                        |             |                    |
|                                                                     |                                                            |                           | vpc:ports:get          |             |                    |
+---------------------------------------------------------------------+------------------------------------------------------------+---------------------------+------------------------+-------------+--------------------+
| Querying details about floating IP addresses (native OpenStack API) | GET /v2.1/{project_id}/os-floating-ips/{floating_ip_id}    | ecs:serverFloatingIps:use | vpc:floatingIps:get    | Supported   | Not supported      |
|                                                                     |                                                            |                           |                        |             |                    |
|                                                                     |                                                            |                           | vpc:ports:get          |             |                    |
+---------------------------------------------------------------------+------------------------------------------------------------+---------------------------+------------------------+-------------+--------------------+
| Releasing a floating IP address (native OpenStack API)              | DELETE /v2.1/{project_id}/os-floating-ips/{floating_ip_id} | ecs:serverFloatingIps:use | vpc:floatingIps:get    | Supported   | Not supported      |
|                                                                     |                                                            |                           |                        |             |                    |
|                                                                     |                                                            |                           | vpc:floatingIps:delete |             |                    |
|                                                                     |                                                            |                           |                        |             |                    |
|                                                                     |                                                            |                           | vpc:floatingIps:update |             |                    |
|                                                                     |                                                            |                           |                        |             |                    |
|                                                                     |                                                            |                           | vpc:ports:get          |             |                    |
+---------------------------------------------------------------------+------------------------------------------------------------+---------------------------+------------------------+-------------+--------------------+
