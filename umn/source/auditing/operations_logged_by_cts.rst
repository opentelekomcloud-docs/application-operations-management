:original_name: aom_02_0115.html

.. _aom_02_0115:

Operations Logged by CTS
========================

AOM is a one-stop O&M platform that monitors applications and resources in real time. By analyzing dozens of metrics and correlation between alarms and logs, AOM helps O&M personnel quickly locate faults.

You can use AOM to comprehensively monitor and uniformly manage servers, storage, networks, web containers, and applications hosted in Docker and Kubernetes. This effectively prevents problems and helps O&M personnel locate faults in minutes, reducing O&M costs. Also, AOM provides unified APIs to interconnect in-house monitoring systems or report systems. Unlike traditional monitoring systems, AOM monitors services by applications. It meets enterprises' requirements for high efficiency and fast iteration, provides effective IT support for their services, and protects and optimizes their IT assets, enabling enterprises to achieve strategic goals and maximize value. With CTS, you can record operations associated with AOM for future query, audit, and backtracking.

.. note::

   **pe** traces actually record AOM operations, but these operations are performed through CCE.

.. table:: **Table 1** Operations logged by CTS

   +------------------------------------------------------------------+--------------------+------------------------+
   | Operation                                                        | Resource Type      | Event Name             |
   +==================================================================+====================+========================+
   | Creating a dashboard                                             | ams                | add-view-action        |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Modifying a dashboard                                            | ams                | update-view-action     |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Deleting a dashboard                                             | ams                | deleteDashboard        |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Creating a threshold                                             | ams                | addThreshold           |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Modifying a threshold                                            | ams                | updateThreshold        |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Deleting a threshold                                             | ams                | deleteThreshold        |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Deleting a subscription rule                                     | apminventory       | deleteSubscribeRule    |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Modifying a subscription rule name                               | apminventory       | updateSubscribeName    |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Creating a subscription rule                                     | apminventory       | createSubscribeRule    |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Deleting a threshold rule                                        | threshold_rules_v2 | deleteOneAlarmById     |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Deleting threshold rules in batches                              | threshold_rules_v2 | deleteAlarmRules       |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Modifying a threshold rule                                       | threshold_rules_v2 | updateAlarm            |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Creating a threshold rule                                        | threshold_rules_v2 | addAlarmForDT          |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Installing a collector                                           | icmgr              | icagentInstall         |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Upgrading a collector                                            | icmgr              | icagentUpgrade         |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Upgrading a probe                                                | icmgr              | pinPointUpgrade        |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Uninstalling a collector                                         | icmgr              | IcagentUninstall       |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Setting metric and log collection                                | icmgr              | metricAndLogSwitches   |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Delivering configuration                                         | icmgr              | webIcAgentEvent        |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Clearing an alarm                                                | pushEvents         | clearEvents            |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Creating or modifying an application discovery rule              | apminventory       | addOrUpdateAppRules    |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Deleting an application discovery rule                           | apminventory       | deleteAppRules         |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Modifying the alias or tag of an application, host, or component | apminventory       | updateInventoryTag     |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Creating a policy group                                          | pe                 | createPolicyGroup      |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Deleting a policy group                                          | pe                 | deletePolicyGroup      |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Updating a policy group                                          | pe                 | updatePolicyGroup      |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Enabling a policy group                                          | pe                 | enablePolicyGroup      |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Disabling a policy group                                         | pe                 | disablePolicyGroup     |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Creating a policy                                                | pe                 | createPolicy           |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Deleting a policy                                                | pe                 | deletePolicy           |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Updating a policy                                                | pe                 | updatePolicy           |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Enabling a policy                                                | pe                 | enablePolicy           |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Disabling a policy                                               | pe                 | disablePolicy          |
   +------------------------------------------------------------------+--------------------+------------------------+
   | Updating the aging period                                        | als                | updateLogStorgeSetting |
   +------------------------------------------------------------------+--------------------+------------------------+
