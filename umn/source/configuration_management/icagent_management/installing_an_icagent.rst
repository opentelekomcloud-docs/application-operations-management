:original_name: aom_02_0012.html

.. _aom_02_0012:

Installing an ICAgent
=====================

ICAgents collect metrics, logs, and application performance data in real time. For hosts purchased from the ECS or BMS console, you need to manually install the ICAgent. For hosts purchased from the CCE console, the ICAgent is automatically installed.

.. note::

   AOM and LTS use the same ICAgent functions. All metric data collected by ICAgents will be reported to AOM for analysis and processing. However, for logs, only those matching the latest log collection configuration in the system will be collected.

   For example, if you configure log collection paths in AOM for ECSs, the previous LTS collection configurations of all ECSs under the resource set become invalid.

The following table describes the ICAgent status.

.. table:: **Table 1** ICAgent status

   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Status              | Description                                                                                                                                                                                                         |
   +=====================+=====================================================================================================================================================================================================================+
   | Running             | The ICAgent is running properly.                                                                                                                                                                                    |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Uninstalled         | The ICAgent is not installed. For details about how to install an ICAgent, see :ref:`Installing an ICAgent <aom_02_0012>`.                                                                                          |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Installing          | The ICAgent is being installed. This operation takes about 1 minute to complete.                                                                                                                                    |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Installation failed | Failed to install the ICAgent. Uninstall the ICAgent according to :ref:`Uninstalling the ICAgent by Logging In to the Server <aom_02_0014__en-us_topic_0263893549_section1218782615374>` and then install it again. |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Upgrading           | The ICAgent is being upgraded. This operation takes about 1 minute to complete.                                                                                                                                     |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Upgrade failed      | Failed to upgrade the ICAgent. Uninstall the ICAgent according to :ref:`Uninstalling the ICAgent by Logging In to the Server <aom_02_0014__en-us_topic_0263893549_section1218782615374>` and then install it again. |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Offline             | The ICAgent is abnormal due to network problems. Check and restore the network.                                                                                                                                     |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Abnormal            | The ICAgent is abnormal. Contact technical support.                                                                                                                                                                 |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Prerequisites
-------------

Before installing an ICAgent, ensure that the time and time zone of the local browser are consistent with those of the server. If multiple servers are deployed, ensure that the local browser and multiple servers use the same time zone and time. Otherwise, metric data of applications and servers displayed on the UI may be incorrect.

Installation Methods
--------------------

There are two methods to install an ICAgent. Note that the two methods are not applicable to container nodes created using CCE. For container nodes, you do not need to manually install an ICAgent. Instead, you only need to perform certain operations when creating clusters or deploying applications.

For details, see :ref:`Table 2 <aom_02_0012__en-us_topic_0263893607_td567fa2f6ccc421ca2e6a4b8a51ee8c6>`.

.. _aom_02_0012__en-us_topic_0263893607_td567fa2f6ccc421ca2e6a4b8a51ee8c6:

.. table:: **Table 2** Installation methods

   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Method                            | Scenario                                                                                                                                                                                                                                     |
   +===================================+==============================================================================================================================================================================================================================================+
   | Initial installation              | This method is used when the following condition is met:                                                                                                                                                                                     |
   |                                   |                                                                                                                                                                                                                                              |
   |                                   | An ICAgent has never been installed on your server.                                                                                                                                                                                          |
   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Inherited installation            | This method is used when the following conditions are met:                                                                                                                                                                                   |
   |                                   |                                                                                                                                                                                                                                              |
   |                                   | You need to install ICAgents on multiple servers. An ICAgent has been installed on one of the servers. All the servers are in the same VPC. If the servers are not in the same VPC, bind EIPs to them before using this installation method. |
   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Initial Installation
--------------------

After you apply for a server and install an ICAgent for the first time, perform the following operations:

#. Obtain an Access Key ID/Secret Access Key (AK/SK).

   -  If you have obtained the AK/SK, skip this step.
   -  If you have not obtained an AK/SK, :ref:`obtain them first <aom_03_0015>`.

#. In the navigation pane, choose **Configuration Management** > **Agent Management**.

#. Select **Other: custom hosts**, and click **Install ICAgent**.

#. Click **Copy Command** to copy the installation command.

#. Use a remote login tool to log in to the target server as the **root** user, and run the following command to disable historical record collection:

   **set +o history**

#. Run the copied installation command and enter the obtained AK and SK as prompted.

#. After the ICAgent is installed, run the following command to enable historical record collection:

   **set -o history**

   .. note::

      -  If the message **ICAgent install success** is displayed, the ICAgent has been installed in the **/opt/oss/servicemgr/** directory. After the ICAgent has been installed, choose **Configuration Management** > **Agent Management** to view the ICAgent status.
      -  If the ICAgent fails to be installed, uninstall the ICAgent according to :ref:`Uninstalling the ICAgent by Logging In to the Server <aom_02_0014__en-us_topic_0263893549_section1218782615374>` and then install it again. If the problem persists, contact technical support.

.. _aom_02_0012__en-us_topic_0263893607_section490015619361:

Inherited Installation
----------------------

If an ICAgent has been installed on a server and the **ICProbeAgent.zip** installation package exists in the **/opt/ICAgent/** directory of this server, use this method to install an ICAgent on a remote server with a few clicks.

#. Run the following command (**x.x.x.x** indicates the server IP address) on the server where an ICAgent has been installed:

   **bash /opt/oss/servicemgr/ICAgent/bin/remoteInstall/remote_install.sh -ip** **x.x.x.x**

#. Enter the password of the **root** user as prompted.

   .. note::

      -  Inherited installation is not supported when ICAgents are installed using an IAM agency.
      -  If both the expect tool and the ICAgent have been installed on the server, an ICAgent will be installed on the remote server after the preceding command is executed. If an ICAgent has been installed on the server, but the Expect tool has not, enter the information as prompted for installation.
      -  Ensure that the **root** user can run the **SSH** or **SCP** command on the server where an ICAgent has been installed to remotely communicate with the server where an ICAgent is to be installed.
      -  If the message **ICAgent install success** is displayed, the ICAgent has been installed in the **/opt/oss/servicemgr/** directory. After the ICAgent has been installed, choose **Configuration Management** > **Agent Management** to view the ICAgent status.
      -  If the ICAgent fails to be installed, uninstall the ICAgent according to :ref:`Uninstalling the ICAgent by Logging In to the Server <aom_02_0014__en-us_topic_0263893549_section1218782615374>` and then install it again. If the problem persists, contact technical support.

Inherited Batch Installation
----------------------------

If an ICAgent has been installed on a server and the **ICProbeAgent.zip** installation package exists in the **/opt/ICAgent/** directory of this server, use this method to install ICAgents on multiple remote servers with a few clicks.

.. important::

   #. Ensure that you can run the **SSH** and **SCP** commands on the server where an ICAgent has been installed to communicate with the remote servers where an ICAgent is to be installed.
   #. If you have installed an ICAgent in a server through an agency, you also need to set an agency for other servers where an ICAgent is to be installed.
   #. Batch installation scripts depend on Python versions. You are advised to implement batch installation on hosts running Python 3.x.
   #. Press **Enter** at the end of each line in the **iplist.cfg** file.

**Prerequisites**

The IP addresses and passwords of all servers on which an ICAgent is to be installed have been collected, sorted in the **iplist.cfg** file, and uploaded to the **/opt/ICAgent/** directory on the server where an ICAgent has been installed. The following is an example of the **iplist.cfg** file, where IP addresses and passwords are separated by spaces.

*192.168.0.109 password* (Set the password as required.)

*192.168.0.39 password* (Set the password as required.)

.. note::

   -  Because the **iplist.cfg** file contains sensitive information, you are advised to clear the information in time.

   -  If the passwords of all servers are the same, list IP addresses in the **iplist.cfg** file and enter the password during execution. If the password of an IP address is different from those of other IP addresses, enter the password next to this IP address.
   -  Batch installation depends on Python 3.x. If the system displays a message indicating that Python cannot be found during the installation, install Python and try again.
   -  Before the installation, check whether the Python command file exists. If the file does not exist, create a soft link.

**Procedure**

#. Run the following command on the server where an ICAgent has been installed:

   **bash /opt/oss/servicemgr/ICAgent/bin/remoteInstall/remote_install.sh -batchModeConfig /opt/ICAgent/iplist.cfg**

   Enter the preset password of the **root** user as prompted. If the passwords of all IP addresses have been configured in the **iplist.cfg** file, press **Enter** to skip this step. Otherwise, enter the preset password.

   .. code-block::

      batch install begin
      Please input default passwd:
      send cmd to 192.168.0.109
      send cmd to 192.168.0.39
      2 tasks running, please wait...
      2 tasks running, please wait...
      2 tasks running, please wait...
      End of install agent: 192.168.0.39
      End of install agent: 192.168.0.109
      All hosts install icagent finish.

   Wait until the message **All hosts install icagent finish.** is displayed, which indicates that the ICAgent has been installed on all the hosts listed in the configuration file.

#. After the ICAgent has been installed, choose **Configuration Management** > **Agent Management** to view the ICAgent status.
