:original_name: aom_02_0039.html

.. _aom_02_0039:

Configuring VM Log Collection Paths
===================================

AOM can collect and display VM logs. VM refers to an Elastic Cloud Server (ECS) running Linux. Before collecting logs, configure a log collection path according to the following procedure.

Prerequisites
-------------

You have installed the ICAgent on a VM according to :ref:`Installing the ICAgent <aom_02_2012>`.

Precautions
-----------

-  The ICAgent collects **\*.log**, **\*.trace**, and **\*.out** log files only. For example, **/opt/yilu/work/xig/debug_cpu.log**.
-  Ensure that an absolute path of the log directory or file is configured and the path exists. For example, **/opt/yilu/work/xig** or **/opt/yilu/work/xig/debug_cpu.log**.
-  The ICAgent does not collect log files from subdirectories. For example, the ICAgent does not collect log files from the **/opt/yilu/work/xig/debug** subdirectory of **/opt/yilu/work/xig**.
-  A maximum of 20 log collection paths can be configured for a VM.
-  For ECSs in the same resource set, only the latest log collection configuration in the system will be used. AOM and LTS log collection configurations cannot take effect at the same time. For example, if you configure log collection paths in AOM for ECSs, the previous LTS collection configurations of all ECSs under the resource set become invalid.

Procedure
---------

#. Log in to the management console.

#. Under **Application**, click **Application Operations Management**.

#. In the navigation pane, choose **Log Management** > **Path Configuration**.

#. In the VM list, click **Configure** in the **Operation** column to configure one or more log collection paths for a VM.

   You can use the paths automatically identified by the ICAgent or manually configure paths.

   -  **Using the paths automatically identified by the ICAgent**

      The ICAgent automatically scans the log files of your VM, and displays all the log files that have file handles and are suffixed with **.log**, **.trace**, or **.out** on the page.

      You can click |image1| in the **Operation** column to add a path automatically identified by the ICAgent to the log collection path list. To configure multiple paths, repeat this operation.


      .. figure:: /_static/images/en-us_image_0297092742.png
         :alt: **Figure 1** Using the paths automatically identified by the ICAgent

         **Figure 1** Using the paths automatically identified by the ICAgent

   -  **Manually configuring log collection paths**

      If the paths automatically identified by the ICAgent cannot meet your requirements, enter a log directory or file (for example, **/opt/yilu/work/xig/debug_cpu.log**) in the **Log Collection Path** text box, and then click |image2| to add the path to the log collection path list. To configure multiple paths, repeat this operation.


      .. figure:: /_static/images/en-us_image_0297092743.png
         :alt: **Figure 2** Manually configuring log collection paths

         **Figure 2** Manually configuring log collection paths

#. Click **OK**.

   After a log collection path is configured, the ICAgent collects log files from the configured path. The collection takes about 1 minute. After log files are collected, choose **Log Management** > **Log Files** in the navigation pane and then click the **Host** tab to view the collected log files.

.. |image1| image:: /_static/images/en-us_image_0227418562.png
.. |image2| image:: /_static/images/en-us_image_0227418562.png
