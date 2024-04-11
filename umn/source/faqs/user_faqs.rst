:original_name: aom_03_0021.html

.. _aom_03_0021:

User FAQs
=========

Why Is Monitoring Data Not Displayed in Real Time on the AOM Page After Resources Are Created?
----------------------------------------------------------------------------------------------

After you create resources such as hosts, applications, components, and processes, the ICAgent reports their monitoring data every 10 minutes. Only when a report period ends, can monitoring data be displayed on the AOM page.

Why Is the Resource Status Displayed as Normal on the AOM Page After Resources Are Deleted?
-------------------------------------------------------------------------------------------

After you delete a resource such as a host or workload from a Cloud Container Engine (CCE) cluster, the resource status is still **Normal** on the **Host Monitoring** or **Container Monitoring** page of AOM. This is normal. The status of the deleted resource will be changed to **Deleted** 30 minutes later.

What Can I Do If the ICAgent Fails to Be Upgraded?
--------------------------------------------------

In the custom cluster scenario, if the ICAgent fails to be upgraded, log in to the VM node and directly run the ICAgent installation command again.

Because the ICAgent supports overwriting installation, directly reinstall the ICAgent without uninstallation.

What Types of Log Files Can Be Collected?
-----------------------------------------

If you specify a directory, all **.log**, **.trace**, and **.out** log files in this directory are collected by default. If you specify a log file, only this file is collected. The specified file must be a text file. Other types of log files, such as binary log files, cannot be collected.

Does the ICAgent Consume Lots of Resources Such as Memory and CPU?
------------------------------------------------------------------

-  AOM collects basic metrics, including CPU and memory of VMs, containers, and processes.

   **Resource consumption**: The resource consumption of the ICAgent is related to the number of containers and processes. In normal service traffic, the ICAgent consumes about 30 MB memory and 3% single-core CPU.

   **Usage restriction**: Ensure that the number of containers running on a single node is less than 1000.

   **Protection mechanism**:

   -  The ICAgent consumes a maximum of two CPU cores.
   -  When the memory consumed by the ICAgent exceeds min {4 GB, node physical memory/2}, AOM restarts the ICAgent for protection.

      .. note::

         Min {4 GB, node physical memory/2} indicates the smaller value between 4 GB and node physical memory/2.

-  AOM also collects log files, including syslog, standard container output, user configuration path, and container mounting files.

   **Resource consumption**: The resource consumption of the ICAgent is closely related to the log volume, number of files, network bandwidth, and backend service processing capability.

How Does AOM Obtain a Custom Host IP Address on the Agent Management Page?
--------------------------------------------------------------------------

By default, AOM traverses all NICs on the VM and obtains the IP addresses of the Ethernet, bond, and wireless NICs based on priorities in descending order. To ensure that AOM obtains the IP address of a specific NIC, set the **IC_NET_CARD=Desired NIC name** environment variable when starting the ICAgent.

**Example:**

#. Add **export IC_NET_CARD=eth2** to **/etc/profile**.

#. Run the **source /etc/profile** command to make the environment variable effective in the shell.

#. Go to the **/opt/oss/servicemgr/ICAgent/bin/manual/** directory, and stop and then restart the ICAgent.

   **bash mstop.sh**

   **bash mstart.sh**

#. Check whether the environment variable is properly transferred to the application.

   **strings /proc/{icagentprocid}/envrion \| grep IC_NET_CARD**

.. note::

   -  If the IP address displayed on ICAgent is **127.0.0.1**, the ICAgent may fail to obtain the local IP address during startup. This problem may occur when a VM is powered off and then restarted. To solve the problem, you only need to restart the ICAgent.
   -  If the IP address of your host changes (for example, a new IP address is allocated during renewal), the original IP address may be displayed on the agent management page. To solve the problem, you only need to restart the ICAgent.

What Can I Do If the ICAgent Fails to Be Installed in the Windows Environment and the "SERVICE STOP" Message Is Displayed?
--------------------------------------------------------------------------------------------------------------------------

**Symptom**: The ICAgent fails to be installed in the Windows environment and the "SERVICE STOP" message is displayed. No ICAgent task exists in the task manager. No ICAgent service exists in the system service list. When the **sc query icagent** command is executed, a message is displayed, indicating that no ICAgent is found.

**Cause**: Antivirus software, such as 360 Total Security, blocks registration of the ICAgent service.

**Solution**:

#. Check whether antivirus software, such as 360 Total Security, is running.
#. First close the antivirus software and install the ICAgent again.

.. note::

   In the Windows environment, manually add log collection paths. The ICAgent can collect **.log**, **.trace**, and **.out** files, but does not collect binary files or Windows system logs.

What Can I Do If the ICAgent Is Successfully Installed on ECS but Its Status Is Abnormal on the Agent Management Page?
----------------------------------------------------------------------------------------------------------------------

The AK/SK is incorrect, or no agency is set when **Installation Mode** is set to **Create Agency**. Perform operations according to and install the ICAgent again.
