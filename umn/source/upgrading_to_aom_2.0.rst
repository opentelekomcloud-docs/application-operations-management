:original_name: aom_02_0112.html

.. _aom_02_0112:

Upgrading to AOM 2.0
====================

This section describes how to migrate data from AOM 1.0 to AOM 2.0. Currently, only collector, and alarm rule upgrades are supported.

Functions
---------

-  :ref:`Collector Upgrade <aom_02_0112__en-us_topic_0000001632043553_section1967411301414>`

   After the collector is upgraded, the process discovery capability is enhanced and the collector can automatically adapt to functions related to CMDB, and monitoring center.

-  :ref:`Alarm Rule Upgrade <aom_02_0112__en-us_topic_0000001632043553_section19675181391416>`

   After alarm rules are upgraded, alarm rule data is smoothly switched from AOM 1.0 to AOM 2.0, and is automatically adapted to alarm rule functions of AOM 2.0.

.. _aom_02_0112__en-us_topic_0000001632043553_section1967411301414:

Collector Upgrade
-----------------

#. Log in to the AOM 1.0 console.
#. In the navigation pane, choose **Configuration Management** > **Agent Management**.
#. Select **Other: custom hosts** from the drop-down list on the right of the page.
#. Select a host and click **Upgrade ICAgent**.
#. Select a target AOM 2.0 version from the drop-down list and click **OK**.
#. Wait for the upgrade, which may take about 1 minute to complete. When the ICAgent status changes from **Updating** to **Running**, the ICAgent has been upgraded.

   .. note::

      If the ICAgent state is abnormal after the upgrade or the upgrade fails, log in to the node and run the installation command to reinstall the ICAgent. (The original configuration can be overwritten, so there is no need for you to uninstall the ICAgent.)

.. _aom_02_0112__en-us_topic_0000001632043553_section19675181391416:

Alarm Rule Upgrade
------------------

#. Log in to the AOM 1.0 console.
#. In the navigation pane on the left, choose **Alarm Center** > **Alarm Rules**.
#. Select one or more alarm rules and click **Migrate to AOM 2.0** above the rule list.

   .. important::

      -  Migration cannot be undone. Exercise caution when performing this operation.
      -  If the alarm rules to be migrated depend on alarm templates, these alarm templates will also be migrated.

4. In the displayed dialog box, click **Confirm**. The selected alarm rules will be migrated to AOM 2.0 in batches.
