:original_name: en-us_topic_0093492522.html

.. _en-us_topic_0093492522:

Expanding the Capacity of an EVS Disk
=====================================

Scenarios
---------

You can expand the disk capacity if the disk space is insufficient. The capacities of both system disks and data disks can be expanded.

Procedure
---------

The capacity of an EVS disk can be expanded in either of the following ways:

-  Create an EVS disk and attach it to an ECS.

-  Expand the capacity of an existing EVS disk. The capacities of both system disks and data disks can be expanded.

   You can expand the disk capacities when the EVS disks are in the **In-use** or **Available** state.

   -  Expanding an **In-use** EVS disk means expanding the capacity of an EVS disk that has been attached to an ECS. Only certain OSs support the expansion of **In-use** EVS disks. For details, see "Expanding an In-use EVS Disk" in *Elastic Volume Service User Guide*.
   -  Expanding an **Available** EVS disk means expanding the capacity of an EVS disk that has not been attached to any ECS. For details, see "Expanding an Available EVS Disk" in *Elastic Volume Service User Guide*.

.. note::

   After the disk capacity is expanded, only the storage capacity of the EVS disk is expanded. To use the added storage space, you also need to log in to the ECS and extend the partition and file system.
