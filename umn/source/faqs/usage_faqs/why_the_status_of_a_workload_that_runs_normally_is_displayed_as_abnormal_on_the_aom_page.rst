:original_name: aom_03_0023.html

.. _aom_03_0023:

Why the Status of a Workload that Runs Normally Is Displayed as "Abnormal" on the AOM Page?
===========================================================================================

A workload runs normally on Cloud Container Engine (CCE), but its status is **Abnormal** on the AOM page.

Possible causes:

#. The ICAgent version is too old.

   ICAgent needs to be upgraded manually. If the ICAgent version is too old, the workload status may fail to be reported in time.

   If the displayed workload status is incorrect, first check whether the ICAgent is in the latest version on the **Agent Management** page.

#. The node time is not synchronized with the actual time.

   If the difference between the node time and the actual time is too large, the ICAgent fails to report metrics in time.

   If the displayed workload status is incorrect, check whether the node time is different from the actual time or check the NTP offset on the AOM page.
