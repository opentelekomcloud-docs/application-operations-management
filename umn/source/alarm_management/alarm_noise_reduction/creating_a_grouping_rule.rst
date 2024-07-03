:original_name: aom_02_0952.html

.. _aom_02_0952:

Creating a Grouping Rule
========================

You can filter alarm subsets and then group them based on the grouping conditions. Alarms in the same group are aggregated to trigger one notification.

As shown in :ref:`Figure 1 <aom_02_0952__en-us_topic_0000001261559953_fig1394511614160>`, when **Alarm Severity** under **Grouping Condition** is set to **Critical**, the system filters out the critical alarms, and then combines these alarms based on the specified mode. The combined alarms can then be associated with an action rule for sending notifications.

.. _aom_02_0952__en-us_topic_0000001261559953_fig1394511614160:

.. figure:: /_static/images/en-us_image_0000001404765705.png
   :alt: **Figure 1** Grouping process

   **Figure 1** Grouping process


Creating a Grouping Rule
------------------------

You can create up to 100 grouping rules.

#. In the navigation pane, choose **Alarm Center** > **Alarm Noise Reduction**.

#. On the **Grouping Rules** tab page, click **Create** and set parameters such as the rule name and grouping condition. For details, see :ref:`Table 1 <aom_02_0952__en-us_topic_0000001261559953_table169384396812>`.


   .. figure:: /_static/images/en-us_image_0000001412095554.png
      :alt: **Figure 2** Creating a grouping rule

      **Figure 2** Creating a grouping rule

   .. _aom_02_0952__en-us_topic_0000001261559953_table169384396812:

   .. table:: **Table 1** Setting a grouping rule

      +-----------------------+---------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Category              | Parameter                 | Description                                                                                                                                                                                                                                                            |
      +=======================+===========================+========================================================================================================================================================================================================================================================================+
      | ``-``                 | Rule Name                 | Grouping rule name, which can contain up to 100 characters and cannot start or end with an underscore (_). Only letters, digits, and underscores are allowed.                                                                                                          |
      +-----------------------+---------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Description               | Grouping rule description, which can contain up to 1024 characters.                                                                                                                                                                                                    |
      +-----------------------+---------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Grouping rules        | Grouping Condition        | Conditions set to filter alarms. After alarms are filtered out, you can set alarm action rules for them.                                                                                                                                                               |
      |                       |                           |                                                                                                                                                                                                                                                                        |
      |                       |                           | You can create a maximum of 10 parallel conditions, each of which can contain up to 10 serial conditions. One or more :ref:`alarm action rules <aom_02_0925>` can be set for each parallel condition.                                                                  |
      |                       |                           |                                                                                                                                                                                                                                                                        |
      |                       |                           | Serial conditions are in the AND relationship whereas parallel conditions are in the OR relationship. An alarm must meet all serial conditions under one of the parallel conditions.                                                                                   |
      |                       |                           |                                                                                                                                                                                                                                                                        |
      |                       |                           | For example, if two serial conditions (that is, **Alarm Severity** = **Critical** and **Provider** = **AOM**) are set under a parallel condition, critical AOM alarms are filtered out, and notification actions are performed based on the alarm action rule you set. |
      +-----------------------+---------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Combination rules     | Combine Notifications     | Notifications for alarms with certain fields to be the same will be combined.                                                                                                                                                                                          |
      |                       |                           |                                                                                                                                                                                                                                                                        |
      |                       |                           | Notifications can be combined:                                                                                                                                                                                                                                         |
      |                       |                           |                                                                                                                                                                                                                                                                        |
      |                       |                           | -  By alarm source                                                                                                                                                                                                                                                     |
      |                       |                           | -  By alarm source + severity                                                                                                                                                                                                                                          |
      |                       |                           | -  By alarm source + all tags                                                                                                                                                                                                                                          |
      +-----------------------+---------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Initial Wait Time         | Interval for sending an alarm notification after alarms are combined for the first time. It is recommended that the time be set to seconds to prevent alarm storms.                                                                                                    |
      |                       |                           |                                                                                                                                                                                                                                                                        |
      |                       |                           | Value range: 0s to 10 minutes. Recommended: 15s.                                                                                                                                                                                                                       |
      +-----------------------+---------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Batch Processing Interval | Waiting time for sending an alarm notification after the combined alarm data changes. It is recommended that the time be set to minutes. If you want to receive alarm notifications as soon as possible, set the time to seconds.                                      |
      |                       |                           |                                                                                                                                                                                                                                                                        |
      |                       |                           | The change here refers to a new alarm or an alarm status change.                                                                                                                                                                                                       |
      |                       |                           |                                                                                                                                                                                                                                                                        |
      |                       |                           | Value range: 5s to 30 minutes. Recommended: 60s.                                                                                                                                                                                                                       |
      +-----------------------+---------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Repeat Interval           | Waiting time for sending an alarm notification after the combined alarm data becomes duplicate. It is recommended that the time be set to hours.                                                                                                                       |
      |                       |                           |                                                                                                                                                                                                                                                                        |
      |                       |                           | Duplication means that no new alarm is generated and no alarm status is changed while other attributes (such as titles and content) are changed.                                                                                                                       |
      |                       |                           |                                                                                                                                                                                                                                                                        |
      |                       |                           | Value range: 1 minute to 15 days. Recommended: 1 hour.                                                                                                                                                                                                                 |
      +-----------------------+---------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **Create Now**.

More Operations
---------------

After creating a grouping rule, perform the operations listed in :ref:`Table 2 <aom_02_0952__en-us_topic_0000001261559953_en-us_topic_0169698264_table14918185010104>` if needed.

.. _aom_02_0952__en-us_topic_0000001261559953_en-us_topic_0169698264_table14918185010104:

.. table:: **Table 2** Related operations

   +-----------------------------------+-------------------------------------------------------------------------------------------------------------+
   | Operation                         | Description                                                                                                 |
   +===================================+=============================================================================================================+
   | Modifying a grouping rule         | Click **Modify** in the **Operation** column.                                                               |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------+
   | Deleting a grouping rule          | -  To delete a single rule, click **Delete** in the **Operation** column in the row that contains the rule. |
   |                                   | -  To delete one or more rules, select them and click **Delete** above the rule list.                       |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------+
   | Searching for a grouping rule     | Enter a rule name in the search box in the upper right corner and click |image1|.                           |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001261759895.png
