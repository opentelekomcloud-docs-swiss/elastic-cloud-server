:original_name: en-us_topic_0092494943.html

.. _en-us_topic_0092494943:

Login Overview (Windows)
========================

Constraints
-----------

-  Only a running ECS can be logged in to.
-  Login usernames, passwords, and constraints vary depending on OSs running on the ECSs created using a public image.
-  If an ECS uses key pair authentication, use the password obtaining function available on the management console to decrypt the private key used during ECS creation to obtain a password.

Login Modes
-----------

You can choose from a variety of login modes based on your local OS type.

.. table:: **Table 1** Windows login modes

   +-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
   | ECS OS          | Local OS        | Connection Method                                                                                                                                           | Requirement                                |
   +=================+=================+=============================================================================================================================================================+============================================+
   | Windows         | Windows         | Use MSTSC.                                                                                                                                                  | The target ECS needs to have an EIP bound. |
   |                 |                 |                                                                                                                                                             |                                            |
   |                 |                 | Click **Start** on the local computer. In the **Search programs and files** text box, enter **mstsc** to open the **Remote Desktop Connection** dialog box. |                                            |
   |                 |                 |                                                                                                                                                             |                                            |
   |                 |                 | For details, see :ref:`Logging In to a Windows ECS Using MSTSC <en-us_topic_0017955381>`.                                                                   |                                            |
   +-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
   |                 | Linux           | Install a remote connection tool, for example, rdesktop.                                                                                                    |                                            |
   |                 |                 |                                                                                                                                                             |                                            |
   |                 |                 | For details, see :ref:`Logging In to a Windows ECS from a Linux Computer <en-us_topic_0275383051>`.                                                         |                                            |
   +-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
   |                 | Windows         | Through the management console.                                                                                                                             | No EIP is required.                        |
   |                 |                 |                                                                                                                                                             |                                            |
   |                 |                 | For details, see :ref:`Logging In to a Windows ECS Using VNC <en-us_topic_0027268511>`.                                                                     |                                            |
   +-----------------+-----------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+--------------------------------------------+
