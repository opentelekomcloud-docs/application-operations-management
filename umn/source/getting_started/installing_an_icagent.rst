:original_name: aom_00_0003.html

.. _aom_00_0003:

Installing an ICAgent
=====================

This section describes how to install an ICAgent on an ECS and monitor its resources on the AOM console.

Prerequisites
-------------

-  You have created an ECS.
-  You have :ref:`obtained an AK/SK <aom_03_0015>`.
-  The time of the local browser must be consistent with that of the ECS.


Installing an ICAgent
---------------------

#. Log in to the AOM console. In the navigation pane, choose **Configuration Management** > **Agent Management**.

#. Select **Other: custom hosts**, and click **Install ICAgent**.

#. .. _aom_00_0003__li98461642151219:

   Click **Copy Command** to copy the installation command.

#. Log in to the ECS remotely.

   Specifically, log in to the ECS console, click **Remote Login** in the **Operation** column of the target ECS, and then log in to the ECS as the **root** user.

#. Run the ICAgent installation command.

   On the ECS page, click **Copy & Paste**. On the page that is displayed, press **Ctrl+V** to paste the ICAgent installation command obtained in :ref:`3 <aom_00_0003__li98461642151219>`, and click **Send** to send the command to the CLI, as shown in the following figure. In the CLI, press **Enter** to run the ICAgent installation command.

   If the message "ICAgent install success" is displayed, the ICAgent is successfully installed in the **/opt/oss/servicemgr/** directory. Wait for a while and go back to the **Agent Management** page to check whether the ICAgent status of the ECS is **Running**.

   -  If the ICAgent status is **Running**, the ICAgent is successfully installed.
   -  If the ICAgent status is **Offline**, view details. The AK/SK or ECS agency may be incorrect. In this case, obtain the correct AK/SK or reconfigure the ECS agency, and then reinstall the ICAgent.

#. On the AOM console, monitor the ECS.

   After the ICAgent is installed, wait for about 1-2 minutes. Then, in the navigation pane, choose **Overview** > **O&M** to monitor the ECS.
