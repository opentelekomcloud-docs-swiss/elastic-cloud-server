:original_name: en-us_topic_0163572589.html

.. _en-us_topic_0163572589:

Step 1: Configure Basic Settings
================================

Accessing the ECS Creation Page
-------------------------------

#. Log in to the management console.

#. Under **Computing**, click **Elastic Cloud Server**.

#. Click **Create ECS**.

   The page for creating ECSs is displayed.

Basic Settings
--------------

#. Select an AZ.

   An AZ is a physical location that uses independent power supply and networks. AZs in the same region can communicate with each other over an intranet.

   -  To enhance application availability, create ECSs in different AZs.
   -  To shorten network latency, create ECSs in the same AZ.

#. Set **DeH**.

   This configuration is optional. This parameter is available only when you click **Create ECS** on the **Dedicated Host** page. It is unavailable when you click **Create ECS** on the **Elastic Cloud Server** page.

   DeH refers to physical server resources dedicated for a specified user. You can deploy ECSs on DeHs for better isolation, security, and performance of your ECSs. You can continue using your existing server software licenses of ECSs on DeHs to reduce costs. For more details, see *Dedicated Host User Guide*.

   .. note::

      If you select a SUSE-SAP public image when creating an ECS on a DeH, you will be billed for the license.

#. Set **Specifications**.

   The cloud platform provides various ECS types for different application scenarios. You can choose from existing ECS types and flavors in the list. Alternatively, you can enter a flavor or specify vCPUs and memory size to search for the flavor suited to your needs.

   .. note::

      Before selecting an ECS type, familiarize yourself with various ECS types listed in :ref:`ECS Types <en-us_topic_0035470096>`.

#. Select an image.

   -  Public image

      A public image is a standard, widely used image. It contains an OS and preinstalled public applications and is available to all users. You can configure the runtime environment or software in the public image as needed.

      If you select a SUSE-SAP public image, you will be billed for the license.

   -  Private image

      A private image is an image available only to the user who created it. It contains an OS, preinstalled public applications, and the user's private applications. You can use a private image to create multiple ECSs in a batch, reducing the time for configuring ECSs repeatedly.

      You can also select an encrypted image. For more information about encrypted images, see *Image Management Service User Guide*.

      .. note::

         -  If you use a full-ECS image to create an ECS, the EVS disks associated with the full-ECS image do not support the function of creating disks using a data disk image.

         -  If a full-ECS image is in **Normal** state and the system displays message "Available in AZ\ *x*", the full-ECS image can be used to create ECSs in this AZ only, and the encryption attributes of the system and data disks of the created ECSs are the same as those of the system and data disks specified in the full-ECS image. The SCSI, encryption, and sharing attribute settings of the system and data disks cannot be modified during ECS creation.

         -  If a full-ECS image is in **Normal** state but the system does not display message "Available in AZ\ *x*", the full-ECS image can be used to create ECSs in the entire region, and the encryption attributes of the system and data disks of the created ECSs are the same as those of the system and data disks specified in the full-ECS image. Additionally, the data encryption settings of the system disk, and the SCSI, sharing attribute, and data encryption settings of data disks can be modified during ECS creation.

         -  To ensure that NIC multi-queue is enabled on an ECS created using a private image, configure NIC multi-queue when creating such a private image. NIC multi-queue routes NIC interrupt requests among multiple vCPUs for higher network packets per second (PPS) and bandwidth.

            For details, see "How Do I Set NIC Multi-Queue Feature of an Image?"

   -  Shared image

      A shared image is a private image shared by another user.

#. Set **System Disk** and **Data Disk** if required.

   -  System disk

      For details about the disk types supported by ECSs, see :ref:`EVS Disks <en-us_topic_0030828256>`.

      -  If the image based on which an ECS is created is not encrypted, the system disk of the ECS is not encrypted. If the image based on which an ECS is created is encrypted, the system disk of the ECS is automatically encrypted. For details, see :ref:`(Optional) Encryption-related parameters <en-us_topic_0163572589__en-us_topic_0144542112_li3286101316615>`.
      -  **Encryption**: indicates that the system disk is encrypted if you select this option. For details, see :ref:`(Optional) Encryption-related parameters <en-us_topic_0163572589__en-us_topic_0144542112_li3286101316615>`.

   -  Data disk

      You can create multiple data disks for an ECS and enable required functions for each data disk. During the creation process, you can add a maximum of 23 data disks for each ECS and customize the disk size as needed.

      Click **Show** |image1| and set the following functions if required:

      -  **SCSI**: indicates that the device type of the data disk is SCSI if you select this option. For more information about SCSI disks and ECSs that can have SCSI disks attached, see :ref:`EVS Disks <en-us_topic_0030828256>`.
      -  **Share**: indicates that the EVS disk is sharable if you select this option. Such an EVS disk can be attached to multiple ECSs.
      -  **Encryption**: indicates that the data disk is encrypted if you select this option. For details, see :ref:`(Optional) Encryption-related parameters <en-us_topic_0163572589__en-us_topic_0144542112_li3286101316615>`.

   -  .. _en-us_topic_0163572589__en-us_topic_0144542112_li3286101316615:

      (Optional) Encryption-related parameters

      To enable encryption, click **Create Xrole** to grant KMS access permissions to EVS. If you have the granting permission, grant KMS access permissions to EVS. If you do not have the granting permission, contact the user who has the Security Administrator permissions to grant KMS access permissions. For details, see :ref:`Can All Users Use the Encryption Feature? <en-us_topic_0047272493>`

      -  **Encryption**: indicates that the EVS disk has been encrypted.
      -  **Create Xrole**: assigns KMS access permissions to EVS to obtain KMS keys. After the permissions are assigned, follow-up operations do not require assigning permissions again.
      -  **Xrole Name**: set to **EVSAccessKMS**, which means that permissions have been assigned to EVS to obtain KMS keys for encrypting or decrypting EVS disks.
      -  **KMS Key Name**: specifies the name of the key used by the encrypted EVS disk. You can select an existing key, or click **Create KMS Key** and create a new one on the KMS console. The default value is **evs/default**.
      -  **KMS Key ID**: specifies the ID of the key used by the encrypted data disk.

#. Click **Next: Configure Network**.

.. |image1| image:: /_static/images/en-us_image_0000001208978003.png
