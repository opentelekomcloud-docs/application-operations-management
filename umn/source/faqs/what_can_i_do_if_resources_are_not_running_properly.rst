:original_name: aom_02_1012.html

.. _aom_02_1012:

What Can I Do If Resources Are Not Running Properly?
====================================================

Resource statuses include **Normal**, **Warning**, **Abnormal**, **Deleted**, and **Silent**. **Warning**, **Abnormal**, and **Silent** indicate improper resource running. Analyze and rectify faults according to the following instructions.

Warning
-------

If a minor alarm or warning exists, the resource status is **Warning**.

Suggestion: Handle the alarm based on alarm details.

Abnormal
--------

If a critical or major alarm exists, the resource status is **Abnormal**.

Suggestion: Handle the alarm based on alarm details.

Silent
------

If the ICAgent fails to collect resource metrics, the resource status is **Silent**. The causes include but are not limited to:

-  **Cause 1: The ICAgent is abnormal.**

   Suggestion: In the navigation pane, choose **Agent Management**. On the page that is displayed, check the ICAgent status, as shown in :ref:`Figure 1 <aom_02_1012__fig753416484913>`. If the status is not **Running**, the ICAgent has been uninstalled or is abnormal. For details on how to solve the problem, see :ref:`Table 1 <aom_02_1012__table13223726125116>`.

   .. _aom_02_1012__table13223726125116:

   .. table:: **Table 1** ICAgent troubleshooting suggestions

      +---------------------+----------------------------------------------------------------------------------+
      | Status              | Suggestion                                                                       |
      +=====================+==================================================================================+
      | Uninstalled         | Install the ICAgent by referring to :ref:`Installing the ICAgent <aom_02_2012>`. |
      +---------------------+----------------------------------------------------------------------------------+
      | Installing          | Wait for about 1 minute to complete the ICAgent installation.                    |
      +---------------------+----------------------------------------------------------------------------------+
      | Installation failed | If the ICAgent fails to be installed, reinstall it.                              |
      +---------------------+----------------------------------------------------------------------------------+
      | Upgrading           | Wait for about 1 minute to complete the ICAgent upgrade.                         |
      +---------------------+----------------------------------------------------------------------------------+
      | Upgrade failed      | If the ICAgent fails to be upgraded, reinstall it.                               |
      +---------------------+----------------------------------------------------------------------------------+
      | Offline             | Check for network faults and rectify such faults.                                |
      +---------------------+----------------------------------------------------------------------------------+
      | Faulty              | Contact technical support.                                                       |
      +---------------------+----------------------------------------------------------------------------------+

   .. _aom_02_1012__fig753416484913:

   .. figure:: /_static/images/en-us_image_0297106347.png
      :alt: **Figure 1** Checking the ICAgent status

      **Figure 1** Checking the ICAgent status

-  **Cause 2: AOM cannot monitor the current resource.**

   Suggestion: Check whether your resources can be monitored by AOM. AOM can monitor hosts, Kubernetes containers, and user processes, but does not monitor system processes.

-  **Cause 3: The local time of the host is not synchronized with the NTP server time.**

   .. note::

      **NTP Sync Status**: indicates whether the local time of the host is synchronized with the NTP server time. The value can be **0** or **1**. **0** indicates the synchronized status while **1** indicates the asynchronized status.

   Suggestion: Choose **View Management** > **Metric Monitoring** and check the **NTP Sync Status** metric of the host. If the value of **NTP Sync Status** is **1**, the local time of the host is not synchronized with that of the NTP server. To solve the problem, perform synchronization.

-  **Cause 4: The resource is deleted or stopped.**

   Suggestions:

   -  On the ECS page, check whether the host is restarted, stopped, or deleted.
   -  On the Cloud Container Engine (CCE) page, check whether the component is stopped or deleted.
