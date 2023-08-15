:original_name: en-us_topic_0103072348.html

.. _en-us_topic_0103072348:

Image Management
================

+------------------------------------------+----------------------------------------------------+-------------------------+----------------------+-------------+--------------------+
| Permission                               | API                                                | Action                  | Dependencies         | IAM Project | Enterprise Project |
+==========================================+====================================================+=========================+======================+=============+====================+
| Creating an image (native OpenStack API) | POST /v2.1/{project_id}/servers/{server_id}/action | ecs:servers:createImage | evs:volumes:get      | Supported   | Not supported      |
|                                          |                                                    |                         |                      |             |                    |
|                                          |                                                    |                         | evs:snapshots:create |             |                    |
|                                          |                                                    |                         |                      |             |                    |
|                                          |                                                    |                         | ims:images:create    |             |                    |
|                                          |                                                    |                         |                      |             |                    |
|                                          |                                                    |                         | ims:images:get       |             |                    |
|                                          |                                                    |                         |                      |             |                    |
|                                          |                                                    |                         | ims:images:list      |             |                    |
|                                          |                                                    |                         |                      |             |                    |
|                                          |                                                    |                         | ims:images:update    |             |                    |
|                                          |                                                    |                         |                      |             |                    |
|                                          |                                                    |                         | ims:images:delete    |             |                    |
+------------------------------------------+----------------------------------------------------+-------------------------+----------------------+-------------+--------------------+
