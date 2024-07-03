:original_name: aom_02_0953.html

.. _aom_02_0953:

Creating a Suppression Rule
===========================

By using suppression rules, you can suppress or block notifications related to specific alarms. For example, when a major alarm is generated, less severe alarms can be suppressed. Another example, when a node is faulty, all other alarms of the processes or containers on this node can be suppressed.

Precautions
-----------

If the source alarm corresponding to the suppression condition is cleared before the alarm notification is sent, the suppression rule becomes invalid. For the suppressed object (alarm suppressed by the source alarm), the alarm notification can still be sent as usual.

You can create up to 100 suppression rules.


Creating a Suppression Rule
---------------------------

#. In the navigation pane, choose **Alarm Center** > **Alarm Noise Reduction**.

#. On the **Suppression Rules** tab page, click **Create** and set parameters such as the rule name and root alarm.


   .. figure:: /_static/images/en-us_image_0000001461819281.png
      :alt: **Figure 1** Creating a suppression rule

      **Figure 1** Creating a suppression rule

   .. table:: **Table 1** Setting a suppression rule

      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Category              | Parameter             | Description                                                                                                                                                                                                                                                                                                            |
      +=======================+=======================+========================================================================================================================================================================================================================================================================================================================+
      | ``-``                 | Rule Name             | Suppression rule name, which can contain up to 100 characters and cannot start or end with an underscore (_). Only letters, digits, and underscores are allowed.                                                                                                                                                       |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Description           | Suppression rule description, which can contain up to 1024 characters.                                                                                                                                                                                                                                                 |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Suppression rules     | Source Alarm          | Alarm that triggers suppression.                                                                                                                                                                                                                                                                                       |
      |                       |                       |                                                                                                                                                                                                                                                                                                                        |
      |                       |                       | You can create up to 10 parallel conditions under **Source Alarm**, and up to 10 serial conditions under each parallel condition. Serial conditions are in the AND relationship whereas parallel conditions are in the OR relationship. An alarm must meet all serial conditions under one of the parallel conditions. |
      |                       |                       |                                                                                                                                                                                                                                                                                                                        |
      |                       |                       | For a serial condition, if **Alarm Severity** is set to **Critical**, critical alarms are filtered out as the root alarms.                                                                                                                                                                                             |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Suppressed Alarm      | Alarm that is suppressed by the root alarm.                                                                                                                                                                                                                                                                            |
      |                       |                       |                                                                                                                                                                                                                                                                                                                        |
      |                       |                       | Set parameters for the suppressed alarm in the same way that you set parameters for the source alarm.                                                                                                                                                                                                                  |
      |                       |                       |                                                                                                                                                                                                                                                                                                                        |
      |                       |                       | If **Serial Condition** of **Source Alarm** is set to **Critical** and that of **Suppressed Alarm** is set to **Warning**, warnings will be suppressed when critical alarms are generated.                                                                                                                             |
      +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. After you finish setting the parameters, click **Create Now**.

   After a suppression rule is created, it will take effect for all alarms that are grouped.

More Operations
---------------

After creating a suppression rule, perform the operations listed in :ref:`Table 2 <aom_02_0953__en-us_topic_0000001261759891_en-us_topic_0169698264_table14918185010104>` if needed.

.. _aom_02_0953__en-us_topic_0000001261759891_en-us_topic_0169698264_table14918185010104:

.. table:: **Table 2** Related operations

   +-----------------------------------+-------------------------------------------------------------------------------------------------------------+
   | Operation                         | Description                                                                                                 |
   +===================================+=============================================================================================================+
   | Modifying a suppression rule      | Click **Modify** in the **Operation** column.                                                               |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------+
   | Deleting a suppression rule       | -  To delete a single rule, click **Delete** in the **Operation** column in the row that contains the rule. |
   |                                   | -  To delete one or more rules, select them and click **Delete** above the rule list.                       |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------+
   | Searching for a suppression rule  | Enter a rule name in the search box in the upper right corner and click |image1|.                           |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001261639913.png
