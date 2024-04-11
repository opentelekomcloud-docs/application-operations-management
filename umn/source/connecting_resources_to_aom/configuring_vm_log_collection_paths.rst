:original_name: aom_02_0039.html

.. _aom_02_0039:

Configuring VM Log Collection Paths
===================================

AOM can collect and display VM logs. VM refers to an Elastic Cloud Server (ECS) or a Bare Metal Server (BMS) running Linux. To use this function, first configure a log collection path according to the following procedure.

Prerequisites
-------------

-  Ensure that your VMs are ECSs or BMSs running Linux.
-  You have installed an ICAgent on a VM according to :ref:`Installing an ICAgent <aom_02_0012>`. Wait for about 5 minutes after the installation is complete. Then you can view the VM in the VM list on the **Path Configuration** page.

Precautions
-----------

-  If you specify a directory, all **.log**, **.trace**, and **.out** text log files in this directory are collected by default. If you specify a log file, only this file is collected. The specified file must be a text file. Other types of log files, such as binary log files, cannot be collected.
-  Ensure that an absolute path of a log directory or file is configured and the path exists. For example, **/opt/yilu/work/xig** or **/opt/yilu/work/xig/debug_cpu.log**.
-  The ICAgent does not collect log files from subdirectories. For example, the ICAgent does not collect log files from the **/opt/yilu/work/xig/debug** subdirectory of **/opt/yilu/work/xig**.
-  A maximum of 20 log collection paths can be configured for a VM.
-  If the difference between the last modification time of a log file and the current time exceeds 12 hours, the log file will not be collected.
-  For ECSs in the same resource set, logs will be collected based on the latest log collection configuration. AOM and LTS log collection configurations cannot take effect at the same time. For example, if you configure log collection paths in AOM for ECSs, the previous LTS collection configurations of all ECSs under the resource set become invalid.

Configuring Log Collection Paths for a Single VM Through the Console
--------------------------------------------------------------------

#. Log in to the AOM console. In the navigation pane, choose **Log** > **Path Configuration**. The **Host Log** tab page is displayed.

#. In the VM list, click **Configure** in the **Operation** column to configure one or more log collection paths for a VM.

   You can use the paths automatically identified by the ICAgent or manually configure paths.

   -  **Using the Paths Automatically Identified by the ICAgent**

      The ICAgent automatically scans the log files of your VM, and displays all the **.log**, **.trace**, or **.out** log files with handles and their paths on the page.

      You can click |image1| in the **Operation** column to add a path automatically identified by the ICAgent to the log collection path list. To configure multiple paths, repeat this operation.


      .. figure:: /_static/images/en-us_image_0000001410647264.png
         :alt: **Figure 1** Using the paths automatically identified by the ICAgent

         **Figure 1** Using the paths automatically identified by the ICAgent

   -  **Manually Configuring Log Collection Paths**

      If the paths automatically identified by the ICAgent cannot meet your requirements, enter a log directory or file (such as **/opt/yilu/work/xig/debug_cpu.log** or **/opt/yilu/work/xig/*.log**) in the **Log Collection Path** text box, and then click |image2| to add the path to the log collection path list. To configure multiple paths, repeat this operation.


      .. figure:: /_static/images/en-us_image_0000001410327528.png
         :alt: **Figure 2** Manually configuring log collection paths

         **Figure 2** Manually configuring log collection paths

#. Click **OK**.

Configuring Log Collection Paths for Multiple VMs in Batches Through the Console
--------------------------------------------------------------------------------

You can configure log collection paths for multiple VMs in batches. When your service is deployed on multiple VMs, you can configure log collection paths in batches to reduce workload.

#. Log in to the AOM console. In the navigation pane, choose **Log** > **Path Configuration**. The **Host Log** tab page is displayed.

#. Configure one or more log collection paths for multiple VMs in batches.

   Select one or more VMs in the list, click **Batch Configure**, and enter a log directory or file (for example, **/opt/yilu/work/xig/debug_cpu.log**) in the **Log Collection Path** text box.


   .. figure:: /_static/images/en-us_image_0000001412205042.png
      :alt: **Figure 3** Configuring log collection paths in batches

      **Figure 3** Configuring log collection paths in batches

   .. note::

      If you configure log collection paths for your VM and then configure log collection paths in batches, new paths will be added to the existing path list.

#. Click **OK**.

   In the VM list, click |image3| in the **Log Collection Path** column to view the configured log collection paths of the VM.

Viewing VM Logs
---------------

After the log collection paths are configured, the ICAgent collects log files from them. This operation takes about 1 minute to complete. After collecting logs, you can perform the following operations:

-  **Viewing VM Log Files**

   In the navigation pane, choose **Log** > **Log Files**. Click the **Host** tab to view the collected log files. For details, see :ref:`Viewing Log Files <aom_02_0010>`.

-  **Viewing and Analyzing VM logs**

   In the navigation pane, choose **Log** > **Log Search**. Click the **Host** tab to view and analyze the collected logs by time range, keyword, and context. For details, see :ref:`Searching for Logs <aom_02_0009>`.

.. |image1| image:: /_static/images/en-us_image_0263893495.png
.. |image2| image:: /_static/images/en-us_image_0263893495.png
.. |image3| image:: /_static/images/en-us_image_0263893507.png
