:original_name: en-us_topic_0093492518.html

.. _en-us_topic_0093492518:

Adding a NIC
============

Scenarios
---------

If your ECS requires multiple network interfaces, you can add them to your ECS.

Procedure
---------

#. Log in to the management console.

#. Click |image1| in the upper left corner and select your region and project.

#. Under **Computing**, click **Elastic Cloud Server**.

#. Click the name of the ECS to which you want to add a NIC.

   The page providing details about the ECS is displayed.

#. On the **NICs** tab, click **Add NIC**.

#. Set the subnet and security group for the NIC to be added.

   -  **Security Group**: You can select multiple security groups. In such a case, the access rules of all the selected security groups will apply to the ECS.
   -  **Subnet**: specifies the subnet which the network interface to be added belongs to.
   -  **New Private IP Address**: If you want to add a network interface with a specified IP address, enter an IP address into the **New Private IP Address** field. I

#. Click **OK**.

Follow-up Procedure
-------------------

Some OSs cannot identify newly added NICs. In this case, you need to manually activate the NICs. The following uses Ubuntu as an example to show how to activate NICs. Operations may vary depending on the operating system. You can refer to the corresponding OS documentation for assistance.

#. Locate the row containing the target ECS and click **Remote Login** in the **Operation** column.

   Log in to the ECS.

#. .. _en-us_topic_0093492518__li595089165210:

   Run the following command to view the NIC name:

   **ifconfig -a**

   In this example, the NIC name is **eth2**.

#. Run the following command to switch to the target directory:

   **cd /etc/network**

#. Run the following command to open the **interfaces** file:

   **vi interfaces**

#. Add the following information to the **interfaces** file:

   **auto** *eth2*

   **iface** *eth2* **inet dhcp**

#. Run the following command to save and exit the **interfaces** file:

   **:wq**

#. Run either the **ifup eth**\ **X** command or the **/etc/init.d/networking restart** command to make the newly added NIC take effect.

   *X* in the preceding command indicates the serial number of the network interface, for example, **ifup eth2**.

#. Run the following command to check whether the NIC name obtained in step :ref:`2 <en-us_topic_0093492518__li595089165210>` is displayed in the command output:

   **ifconfig**

   For example, check whether **eth2** is displayed in the command output.

   -  If yes, the newly added NIC has been activated. No further action is required.
   -  If no, the newly added NIC failed to be activated. Go to step :ref:`9 <en-us_topic_0093492518__li1695469165210>`.

#. .. _en-us_topic_0093492518__li1695469165210:

   Log in to the management console. Locate the row containing the target ECS, click **More** in the **Operation** column, and select **Restart**.

#. Run **ifconfig** again to check whether the NIC name obtained in step :ref:`2 <en-us_topic_0093492518__li595089165210>` is displayed in the command output:

   -  If yes, no further action is required.
   -  If no, contact the administrator.

.. |image1| image:: /_static/images/en-us_image_0210779229.png
