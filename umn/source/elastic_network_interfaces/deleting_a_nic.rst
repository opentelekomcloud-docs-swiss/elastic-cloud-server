:original_name: en-us_topic_0093492519.html

.. _en-us_topic_0093492519:

Deleting a NIC
==============

Scenarios
---------

An ECS can have a maximum of 12 NICs, including a primary NIC that cannot be deleted. This section describes how to delete an extension NIC.

.. caution::

   Deleting a NIC may cause network interruptions. Evaluate the impact in advance and exercise caution when performing this operation.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select your region and project.

#. Under **Computing**, click **Elastic Cloud Server**.

#. In the ECS list, click the name of the ECS from which you want to delete a NIC

   The page providing details about the ECS is displayed.

#. Click the **NICs** tab. Then, click **Delete** in the row of the target network interface.

   .. note::

      You are not allowed to delete the primary ECS network interface. By default, the primary ECS network interface is the first network interface displayed in the network interface list.

#. In the displayed dialog box, click **Yes**.

   .. note::

      Certain ECSs do not support NIC deletion when they are running. For details, see the GUI display. To delete a NIC from such an ECS, stop the ECS first.

.. |image1| image:: /_static/images/en-us_image_0093507592.png
