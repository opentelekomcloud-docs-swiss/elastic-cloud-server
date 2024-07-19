:original_name: en-us_topic_0124306065.html

.. _en-us_topic_0124306065:

Creating an ECS
===============

Scenarios
---------

This section describes how to create an ECS by calling APIs. For details, see :ref:`Calling APIs <en-us_topic_0124306061>`.

An ECS can be created using a disk or image. This section uses an image as an example to describe how to create an ECS.

Involved APIs
-------------

Creating an ECS involves viewing flavors and AZs as well as creating EVS disks. The following APIs are required:

-  :ref:`Querying Details About ECS Flavors <en-us_topic_0124306065__li15843552537>`: Determine the flavor of the ECS to be created.
-  :ref:`Querying Image Details <en-us_topic_0124306065__li1285212380536>`: Determine the image based on which the ECS is to be created.
-  :ref:`Querying Networks <en-us_topic_0124306065__li123521935105519>`: Determine the network configuration of the ECS.
-  :ref:`Creating and Importing an SSH Key Pair <en-us_topic_0124306065__li123521935105519>`: Set the login mode to **Key pair**.
-  :ref:`Creating an ECS <en-us_topic_0124306065__li1320313439275>`: Create an ECS authenticated using a key pair.
-  :ref:`Querying Details About an ECS <en-us_topic_0124306065__li44614293347>`: Verify that the ECS has been created.

Procedure
---------

#. .. _en-us_topic_0124306065__li15843552537:

   Determine the ECS flavor.

   a. View ECS flavors.

      -  API

         URI format: GET /v2.1/{project_id}/flavors/detail{?minDisk,minRam,is_public,sort_key,sort_dir}

         The fields following the question mark (?) are optional, which are used for querying ECS flavors. For details, see :ref:`Querying Details About ECS Flavors <en-us_topic_0020212658>`.

      -  Example request

         GET https://*{endpoint}*/v2.1/74610f3a5ad941998e91f076297ecf27/flavors/detail

         Obtain *{endpoint}* from the administrator.

      -  Example response

         .. code-block::

            {
              "flavors": [
                {
                  "name": "c1.2xlarge",
                  "links": [
                    {
                      "href": "https://xxx/v2.1/74610f3a5ad941998e91f076297ecf27/flavors/c1.2xlarge",
                      "rel": "self"
                    },
                    {
                      "href": "https://xxx/74610f3a5ad941998e91f076297ecf27/flavors/c1.2xlarge",
                      "rel": "bookmark"
                    }
                  ],
                  "ram": 8192,
                  "OS-FLV-DISABLED:disabled": false,
                  "vcpus": 8,
                  "swap": "",
                  "os-flavor-access:is_public": true,
                  "rxtx_factor": 1,
                  "OS-FLV-EXT-DATA:ephemeral": 0,
                  "disk": 0,
                  "id": "c1.2xlarge"
                }
            ]
            }

   b. Select a flavor based on site requirements and record the flavor ID.

#. .. _en-us_topic_0124306065__li1285212380536:

   Determine the image.

   a. View images.

      -  API

         URI format: GET /v2.1/{project_id}/images/detail

         For details, see :ref:`Querying Image Details (Discarded) <en-us_topic_0065817696>`.

      -  Example request

         GET https://*{endpoint}*/v2.1/74610f3a5ad941998e91f076297ecf27/images/detail

         Obtain *{endpoint}* from the administrator.

      -  Example response

         .. code-block::

            {
              "images": [
                {
                  "OS-EXT-IMG-SIZE:size": 0,
                  "metadata": {
                    "__os_type": "Linux",
                    "hw_vif_multiqueue_enabled": "true",
                    "__imagetype": "gold",
                    "__quick_start": "true",
                    "virtual_env_type": "FusionCompute",
                    "__support_xen": "true",
                    "__support_kvm": "true",
                    "__image_source_type": "uds",
                    "__platform": "EulerOS",
                    "__os_version": "EulerOS 2.2 64bit",
                    "__os_bit": "64",
                    "__isregistered": "false"
                  },
                  "created": "2018-05-14T06:13:50Z",
                  "minRam": 0,
                  "name": "DBS-MySQL-Image_2.1.3.3",
                  "progress": 100,
                  "links": [
                    {
                      "rel": "self",
                      "href": "https://None/v2.1/74610f3a5ad941998e91f076297ecf27/images/11e8f727-d439-4ed1-b3b8-33f46c0379c4"
                    },
                    {
                      "rel": "bookmark",
                      "href": "https://None/74610f3a5ad941998e91f076297ecf27/images/11e8f727-d439-4ed1-b3b8-33f46c0379c4"
                    },
                    {
                      "rel": "alternate",
                      "href": "https://None/images/11e8f727-d439-4ed1-b3b8-33f46c0379c4",
                      "type": "application/vnd.openstack.image"
                    }
                  ],
                  "id": "11e8f727-d439-4ed1-b3b8-33f46c0379c4",
                  "updated": "2018-05-14T06:13:52Z",
                  "minDisk": 40,
                  "status": "ACTIVE"
                }
              ]
            }

   b. Select an image based on site requirements and record the image ID.

#. .. _en-us_topic_0124306065__li123521935105519:

   Determine the network configuration.

   a. View networks.

      -  API

         URI format: GET /v2.1/{project_id}/os-networks

         For details, see :ref:`Querying Networks <en-us_topic_0031169828>`.

      -  Example request

         GET https://*{endpoint}*/v2.1/74610f3a5ad941998e91f076297ecf27/os-networks

         Obtain *{endpoint}* from the administrator.

      -  Example response

         .. code-block::

            {
              "networks": [
                {
                  "id": "07a9557d-4256-48ae-847c-415a9c8f7ff6",
                  "label": "b_tt3_td1b",
                  "broadcast": null,
                  "cidr": null,
                  "dns1": null,
                  "dns2": null,
                  "gateway": null,
                  "netmask": null,
                  "cidr_v6": null,
                  "gateway_v6": null,
                  "netmask_v6": null
                }
              ]
            }

   b. Select a network based on site requirements and record the network ID.

#. Set the login mode to **Key pair**.

   a. Create a key pair.

      -  API

         URI format: POST /v2.1/{project_id}/os-keypairs

         For details, see :ref:`Creating and Importing an SSH Key Pair <en-us_topic_0020212678>`.

      -  Example request

         POST https://*{endpoint}*/v2.1/74610f3a5ad941998e91f076297ecf27/os-keypairs

         Obtain *{endpoint}* from the administrator.

         Body:

         .. code-block::

            {
                "keypair": {
                    "type": "ssh",
                    "name": "demo1",
                    "user_id": "fake"
                }
            }

      -  Example response

         .. code-block::

            {
              "keypair": {
                "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCrR5Gcwlh5ih7JOvzIUuQxS5qzWWPMYHeDXkDKSQ9W5pumOV05SiO3WCswnaQ5xMdOl31mNiHtwlwq9dJi7X6jJBB2shT******************************************************************************************************************************************************************************************************************************************************************************************************* Generated-by-Nova\n",
                "private_key": "-----BEGIN RSA PRIVATE KEY-----\nMIIEogIBAAKCAQEAq0eRnMJYeYoeyTr8yFLkMUuas1ljzGB3g15AykkPVuabpjld\nOUojt1grMJ2kOcTHTpd9ZjYh7cJcKvXSYu1+oyQQdrIUw/tNBuVrsJAWxVOAi77d\nQeOLtDVImkyd+TQL1tv+F76V5vTsIkNweYHumWOxLIt/FJ4fqZG4T5GMTQQivMqD\npaI0IVrO+Wm3cWQYvNdf/EcC3DYhYqHANkRsbUYwXaREnI/tU1PjnH2XUJ69ABWz\ntdc+8sXyMoMMM1U4FLiTWzGyh0rUKkW5JXzJR2OEQT0IG+0Tf2Glyk0El0/OJPg/\ncZQzaO1o+H8DiUzs/7Pz72yDqo0R7fQ+mOCCn***********************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************\n-----END RSA PRIVATE KEY-----\n",
                "user_id": "f79791beca3c48159ac2553fff22e166",
                "name": "demo1",
                "fingerprint": "57:a7:a2:ed:5f:aa:e7:**:**:**:**:**:**:**:**:**"
              }
            }

   b. Import the key pair.

      -  API

         URI format: POST /v2.1/{project_id}/os-keypairs

         For details, see :ref:`Creating and Importing an SSH Key Pair <en-us_topic_0020212678>`.

      -  Example request

         POST https://*{endpoint}*/v2.1/74610f3a5ad941998e91f076297ecf27/os-keypairs

         Obtain *{endpoint}* from the administrator.

         Body:

         .. code-block::

            {
                "keypair": {
                    "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDY8wMTdBYiJgi62o6eShoOlSKx3CZ3cE6PHisDblfK3Y0Bg7EHV7iV9c74pqsrIhK0xuGUuO1NxDQWbkwLTPN4F9Iy5CI********************************************************************************************************************************************************************************************************************************************************* Generated-by-Nova\n",
                    "type": "ssh",
                    "name": "demo2",
                    "user_id": "fake"
                }
            }

      -  Example response

         .. code-block::

            {
              "keypair": {
                "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDY8wMTdBYiJgi62o6eShoOlSKx3CZ3cE6PHisDblfK3Y0Bg7EHV7iV9c74pqsrIhK0xuGUuO1NxDQWbkwLTPN4F9Iy5CI********************************************************************************************************************************************************************************************************************************************************* Generated-by-Nova\n",
                "user_id": "f79791beca3c48159ac2553fff22e166",
                "name": "demo2",
                "fingerprint": "dd:44:45:49:d9:f6:4f:**:**:**:**:**:**:**:**:**"
              }
            }

   c. Record the name in the response body, for example, **demo2**.

#. .. _en-us_topic_0124306065__li1320313439275:

   Create an ECS authenticated using the key pair.

   -  API

      URI format: POST /v2.1/{project_id}/servers

      For details about API constraints and request parameters, see :ref:`Creating an ECS <en-us_topic_0068473331>`.

      .. note::

         In this example, the ECS is created using a specified image.

         -  In **block_device_mapping_v2**, set **source_type** to **image**, **uuid** to the image ID, **destination_type** to **volume**, and **boot_index** to **0**.
         -  The **volume_size** must be greater than or equal to the minimum value specified in the image metadata.

   -  Example request

      POST https://*{endpoint}*/v2.1/74610f3a5ad941998e91f076297ecf27/servers

      Obtain *{endpoint}* from the administrator.

      Body:

      .. code-block::

         {
             "server": {
                 "flavorRef": "c1.large",
                 "name": "zttestvm1",
                 "block_device_mapping_v2": [{
                     "source_type": "image",
                     "destination_type": "volume",
                     "volume_type": "SSD",
                     "volume_size": "40",
                     "delete_on_termination": "true",
                     "uuid": "11e8f727-d439-4ed1-b3b8-33f46c0379c4",
                     "boot_index": "0"
                 }],
                 "networks": [{
                     "uuid": "fb68519f-a7c0-476e-98d4-2e4cf6de6def"
                 }],
                 "key_name": "demo2",
                 "availability_zone": "az_test_01"
             }
         }

   -  Example response

      .. code-block::

         {
           "server": {
             "security_groups": [
               {
                 "name": "default"
               }
             ],
             "OS-DCF:diskConfig": "MANUAL",
             "links": [
               {
                 "rel": "self",
                 "href": "https://None/v2.1/74610f3a5ad941998e91f076297ecf27/servers/6d311127-bce1-48db-bf0f-cac9f8f7f077"
               },
               {
                 "rel": "bookmark",
                 "href": "https://None/74610f3a5ad941998e91f076297ecf27/servers/6d311127-bce1-48db-bf0f-cac9f8f7f077"
               }
             ],
             "id": "6d311127-bce1-48db-bf0f-cac9f8f7f077",
             "adminPass": "**********"
           }
         }

#. .. _en-us_topic_0124306065__li44614293347:

   Verify the ECS creation.

   -  API

      URI format: GET /v2.1/{project_id}/servers/{server_id}

      For details, see :ref:`Querying Details About an ECS <en-us_topic_0020212690>`.

   -  Example request

      GET https://*{endpoint}*/v2.1/74610f3a5ad941998e91f076297ecf27/servers/0c71c0da-8852-4c56-a1d1-3a9b9bcb6da6

      where,

      **0c71c0da-8852-4c56-a1d1-3a9b9bcb6da6** is the UUID of the created ECS.

      Obtain *{endpoint}* from the administrator.

   -  Example response

      .. code-block::

         {
           "server": {
             "tenant_id": "74610f3a5ad941998e91f076297ecf27",
             "addresses": {
               "2a6f4aa6-d93e-45f5-a8cb-b030dbf8cd68": [
                 {
                   "OS-EXT-IPS-MAC:mac_addr": "fa:16:3e:88:01:1b",
                   "OS-EXT-IPS:type": "fixed",
                   "addr": "192.168.2.192",
                   "version": 4
                 }
               ]
             },
             "metadata": {},
             "OS-EXT-STS:task_state": null,
             "OS-DCF:diskConfig": "MANUAL",
             "OS-EXT-AZ:availability_zone":  "az_test_01",
             "links": [
               {
                 "rel": "self",
                 "href": "https://None/v2.1/74610f3a5ad941998e91f076297ecf27/servers/0c71c0da-8852-4c56-a1d1-3a9b9bcb6da6"
               },
               {
                 "rel": "bookmark",
                 "href": "https://None/74610f3a5ad941998e91f076297ecf27/servers/0c71c0da-8852-4c56-a1d1-3a9b9bcb6da6"
               }
             ],
             "OS-EXT-STS:power_state": 1,
             "id": "0c71c0da-8852-4c56-a1d1-3a9b9bcb6da6",
             "os-extended-volumes:volumes_attached": [
               {
                 "id": "b551445a-e749-4d53-932a-638a455cb6c3"
               }
             ],
             "OS-EXT-SRV-ATTR:host": "pod1_test_01",
             "image": {
               "links": [
                 {
                   "rel": "bookmark",
                   "href": "https://None/74610f3a5ad941998e91f076297ecf27/images/11e8f727-d439-4ed1-b3b8-33f46c0379c4"
                 }
               ],
               "id": "11e8f727-d439-4ed1-b3b8-33f46c0379c4"
             },
             "OS-SRV-USG:terminated_at": null,
             "accessIPv4": "",
             "accessIPv6": "",
             "created": "2018-05-25T01:47:11Z",
             "hostId": "b2792bef989888d2df1f51bff81de5ac58a4117f4e9ec3059c1a0410",
             "OS-EXT-SRV-ATTR:hypervisor_hostname": "nova001@36",
             "key_name": null,
             "flavor": {
               "links": [
                 {
                   "rel": "bookmark",
                   "href": "https://None/74610f3a5ad941998e91f076297ecf27/flavors/c1.large"
                 }
               ],
               "id": "c1.large"
             },
             "security_groups": [
               {
                 "name": "default"
               }
             ],
             "config_drive": "",
             "OS-EXT-STS:vm_state": "active",
             "OS-EXT-SRV-ATTR:instance_name": "instance-001883cd",
             "user_id": "f79791beca3c48159ac2553fff22e166",
             "name": "zttestvm1",
             "progress": 0,
             "OS-SRV-USG:launched_at": "2018-05-25T01:47:55.755922",
             "updated": "2018-05-25T01:47:55Z",
             "status": "ACTIVE"
           }
         }
