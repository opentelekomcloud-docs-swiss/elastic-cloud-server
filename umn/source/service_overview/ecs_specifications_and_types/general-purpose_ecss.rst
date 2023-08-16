:original_name: en-us_topic_0035470101.html

.. _en-us_topic_0035470101:

General-Purpose ECSs
====================

Overview
--------

General-purpose ECSs provide a balance of compute, memory, and network resources and a baseline level of vCPU performance with the ability to burst above the baseline. These ECSs are suitable for applications with general workloads, such as web servers, enterprise R&D, and small-scale databases.

Scenarios
---------

-  Applications

   General-purpose ECSs are suitable for applications that have no special requirements on vCPUs, memory, disk capacities, or bandwidth, but have high requirements on security and reliability. The initial investment and maintenance costs are low.

-  Application scenarios

   Enterprise website deployment, enterprise office environment setup, enterprise R&D and testing activities, web servers, R&D and testing environments, and small-scale databases

Specifications
--------------

.. table:: **Table 1** S3 ECS specifications

   +--------------+---------+---------+------------------------+----------+-----------------+----------------+
   | Flavor       | vCPUs   | Memory  | Max./Assured Bandwidth | Max. PPS | Max. NIC Queues | Virtualization |
   |              |         |         |                        |          |                 |                |
   |              |         | (GiB)   | (Gbit/s)               | (10,000) |                 |                |
   +==============+=========+=========+========================+==========+=================+================+
   | s3.small.1   | 1       | 1       | 0.5/0.1                | 5        | 1               | KVM            |
   +--------------+---------+---------+------------------------+----------+-----------------+----------------+
   | s3.medium.2  | 1       | 2       | 0.5/0.1                | 5        | 1               | KVM            |
   +--------------+---------+---------+------------------------+----------+-----------------+----------------+
   | s3.large.2   | 2       | 4       | 0.8/0.2                | 10       | 1               | KVM            |
   +--------------+---------+---------+------------------------+----------+-----------------+----------------+
   | s3.xlarge.2  | 4       | 8       | 1.5/0.4                | 15       | 1               | KVM            |
   +--------------+---------+---------+------------------------+----------+-----------------+----------------+
   | s3.2xlarge.2 | 8       | 16      | 3/0.8                  | 20       | 2               | KVM            |
   +--------------+---------+---------+------------------------+----------+-----------------+----------------+
   | s3.4xlarge.2 | 16      | 32      | 4/1.5                  | 30       | 4               | KVM            |
   +--------------+---------+---------+------------------------+----------+-----------------+----------------+
   | s3.medium.4  | 1       | 4       | 0.5/0.1                | 5        | 1               | KVM            |
   +--------------+---------+---------+------------------------+----------+-----------------+----------------+
   | s3.large.4   | 2       | 8       | 0.8/0.2                | 10       | 1               | KVM            |
   +--------------+---------+---------+------------------------+----------+-----------------+----------------+
   | s3.xlarge.4  | 4       | 16      | 1.5/0.4                | 15       | 1               | KVM            |
   +--------------+---------+---------+------------------------+----------+-----------------+----------------+
   | s3.2xlarge.4 | 8       | 32      | 3/0.8                  | 20       | 2               | KVM            |
   +--------------+---------+---------+------------------------+----------+-----------------+----------------+
   | s3.4xlarge.4 | 16      | 64      | 4/1.5                  | 30       | 4               | KVM            |
   +--------------+---------+---------+------------------------+----------+-----------------+----------------+
