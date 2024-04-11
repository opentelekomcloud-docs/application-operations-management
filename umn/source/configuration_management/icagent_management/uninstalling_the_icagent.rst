:original_name: aom_02_0014.html

.. _aom_02_0014:

Uninstalling the ICAgent
========================

If the ICAgent on a server is uninstalled, server O&M will be affected, making AOM functions unavailable. Exercise caution when performing this operation.

You can uninstall the ICAgent using either of the following methods:

-  :ref:`Uninstalling the ICAgent on the AOM Console <aom_02_0014__en-us_topic_0263893549_section13185626133716>`: applies to the scenario where the ICAgent has been installed and needs to be uninstalled.
-  :ref:`Uninstalling the ICAgent by Logging In to the Server <aom_02_0014__en-us_topic_0263893549_section1218782615374>`: applies to the scenario where the ICAgent fails to be installed and needs to be uninstalled.
-  :ref:`Remotely Uninstalling the ICAgent <aom_02_0014__en-us_topic_0263893549_section76581424194316>`: applies to the scenario where the ICAgent has been installed and needs to be remotely uninstalled.
-  :ref:`Uninstalling the ICAgent in Batches <aom_02_0014__en-us_topic_0263893549_section19497111135712>`: applies to the scenario where the ICAgent has been installed and needs to be uninstalled in batches.

.. _aom_02_0014__en-us_topic_0263893549_section13185626133716:

Uninstalling the ICAgent on the AOM Console
-------------------------------------------

#. In the navigation pane, choose **Configuration Management** > **Agent Management**.

#. Select **Other: custom hosts** from the drop-down list on the right of the page.

#. Select one or more servers where the ICAgent is to be uninstalled, and click **Uninstall ICAgent**. In the **Uninstall ICAgent** dialog box, click **OK**.

   The uninstallation takes about 1 minute to complete. When the ICAgent status changes from **Uninstalling** to **Uninstall**, the ICAgent has been uninstalled.

.. _aom_02_0014__en-us_topic_0263893549_section1218782615374:

Uninstalling the ICAgent by Logging In to the Server
----------------------------------------------------

#. Log in as the **root** user to the server where the ICAgent is to be uninstalled.

#. Run the following command to uninstall the ICAgent:

   **bash /opt/oss/servicemgr/ICAgent/bin/manual/uninstall.sh;**

#. If the message **ICAgent uninstall success** is displayed, the ICAgent has been uninstalled.

.. _aom_02_0014__en-us_topic_0263893549_section76581424194316:

Remotely Uninstalling the ICAgent
---------------------------------

In addition to the preceding method, you can use a method similar to :ref:`Inherited Installation <aom_02_0012__en-us_topic_0263893607_section490015619361>` to remotely uninstall the ICAgent.

#. Run the following command (**x.x.x.x** indicates the server IP address) on the server where the ICAgent has been installed:

   **bash /opt/oss/servicemgr/ICAgent/bin/remoteUninstall/remote_uninstall.sh -ip x.x.x.x**

#. Enter the password of the **root** user as prompted.

   .. note::

      -  If both the expect tool and the ICAgent have been installed on the server, the ICAgent will be uninstalled from the remote server after the preceding command is executed. If the ICAgent has been installed on the server, but the Expect tool has not, enter the information as prompted for installation.
      -  Ensure that the **root** user can run the **SSH** or **SCP** command on the server where the ICAgent has been installed to remotely communicate with the server where the ICAgent is to be uninstalled.
      -  If the message **ICAgent uninstall success** is displayed, the ICAgent has been uninstalled. After the ICAgent has been uninstalled, choose **Configuration Management** > **Agent Management** to view the ICAgent status.

.. _aom_02_0014__en-us_topic_0263893549_section19497111135712:

Uninstalling the ICAgent in Batches
-----------------------------------

If the ICAgent has been installed on a server and the **ICProbeAgent.zip** installation package exists in the **/opt/ICAgent/** directory of this server, use this method to uninstall the ICAgent from multiple remote servers in batches with a few clicks.

.. important::

   The servers must belong to the same Virtual Private Cloud (VPC) and network segment.

**Prerequisites**

The IP addresses and passwords of all servers from which the ICAgent is to be uninstalled have been collected, sorted in the **iplist.cfg** file, and uploaded to the **/opt/ICAgent/** directory on the server where the ICAgent has been installed. The following is an example of the **iplist.cfg** file, where IP addresses and passwords are separated by spaces.

*192.168.0.109 password* (Set the password as required.)

*192.168.0.39 password* (Set the password as required.)

.. note::

   -  Because the **iplist.cfg** file contains sensitive information, you are advised to clear the information in time.

   -  If the passwords of all servers are the same, list IP addresses in the **iplist.cfg** file and enter the password during execution. If the password of an IP address is different from those of other IP addresses, enter the password next to this IP address.
   -  You need to press **Enter** at the end of each line in the **iplist.cfg** file.

**Procedure**

#. Run the following command on the server where the ICAgent has been installed:

   **bash /opt/oss/servicemgr/ICAgent/bin/remoteUninstall/remote_uninstall.sh -batchModeConfig /opt/ICAgent/iplist.cfg**

   Enter the default password of the **root** user as prompted. If the passwords of all IP addresses have been configured in the **iplist.cfg** file, press **Enter** to skip this step. Otherwise, enter the default password.

   .. code-block::

      batch uninstall begin
      Please input default passwd:
      send cmd to 192.168.0.109
      send cmd to 192.168.0.39
      2 tasks running, please wait...
      End of uninstall agent: 192.168.0.109
      End of uninstall agent: 192.168.0.39
      All hosts uninstall icagent finish.

   Wait until the message **All hosts uninstall icagent finish.** is displayed, which indicates that the ICAgent has been uninstalled from all the hosts listed in the configuration file.

#. After the ICAgent has been uninstalled, choose **Configuration Management** > **Agent Management** to view the ICAgent status.
