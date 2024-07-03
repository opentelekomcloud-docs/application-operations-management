:original_name: aom_03_0010.html

.. _aom_03_0010:

What Can I Do If Resources Are Not Running Properly?
====================================================

The resource status includes **Normal**, **Warning**, **Alarm**, and **Silent**. **Warning**, **Alarm**, or **Silent** may result in resource exceptions. You can analyze and rectify exceptions based on the following suggestions.

Warning
-------

If a minor alarm or warning exists, the resource status is **Warning**.

Suggestion: Handle problems based on alarm details.

Alarm
-----

If a critical or major alarm exists, the resource status is **Alarm**.

Suggestion: Handle problems based on alarm details.

Silent
------

If the ICAgent fails to collect resource metrics, the resource status is **Silent**. The causes include but are not limited to:

-  **Cause 1: The ICAgent is abnormal.**

   Suggestion: In the navigation pane, choose **Configuration Management** > **Agent Management**. On the page that is displayed, check the ICAgent status. If the status is not **Running**, the ICAgent is not installed or abnormal. For details about how to solve the problem, see :ref:`Table 1 <aom_03_0010__table13223726125116>`.

   .. _aom_03_0010__table13223726125116:

   .. table:: **Table 1** ICAgent troubleshooting suggestions

      +---------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Status              | Suggestion                                                                                                                                               |
      +=====================+==========================================================================================================================================================+
      | Uninstalled         | :ref:`Install an ICAgent <aom_02_0012>`.                                                                                                                 |
      +---------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Installing          | Wait for 1 minute to install the ICAgent.                                                                                                                |
      +---------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Installation failed | :ref:`Uninstall the ICAgent by logging in to the server <aom_02_0014__en-us_topic_0263893549_section1218782615374>` and then install it again.           |
      +---------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Upgrading           | Wait for 1 minute to upgrade the ICAgent.                                                                                                                |
      +---------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Upgrade failed      | :ref:`Uninstall the ICAgent by logging in to the server <aom_02_0014__en-us_topic_0263893549_section1218782615374>` and then install it again.           |
      +---------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Offline             | The AK/SK is incorrect or port 30200 or 30201 is disconnected. Solve the issue according to :ref:`What Can I Do If an ICAgent Is Offline <aom_04_1100>`. |
      +---------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Faulty              | The ICAgent is abnormal. Contact technical support.                                                                                                      |
      +---------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------+

-  **Cause 2: AOM cannot monitor the current resource.**

   Suggestion: Check whether your resources can be monitored by AOM. Specifically, AOM can monitor hosts, Kubernetes containers, and user processes, but cannot monitor system processes.

-  **Cause 3: The resource is deleted or stopped.**

   Suggestion:

   -  On the ECS page, check whether the host is restarted, stopped, or deleted.
   -  On the CCE page, check whether the service is stopped or deleted.
   -  If an application discovery rule is disabled or deleted, the application discovered based on the rule will also be disabled or deleted. Check whether the application discovery rule is disabled or deleted on AOM.
