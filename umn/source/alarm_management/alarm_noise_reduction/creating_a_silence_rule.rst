:original_name: aom_02_0954.html

.. _aom_02_0954:

Creating a Silence Rule
=======================

You can shield alarm notifications in a specified period. A silence rule takes effect immediately after it is created.


Creating a Silence Rule
-----------------------

You can create up to 100 silence rules.

#. In the navigation pane, choose **Alarm Center** > **Alarm Noise Reduction**.

#. On the **Silence Rules** tab page, click **Create** and set parameters such as the rule name and silence condition.


   .. figure:: /_static/images/en-us_image_0000001472254649.png
      :alt: **Figure 1** Creating a silence rule

      **Figure 1** Creating a silence rule

   .. table:: **Table 1** Setting a silence rule

      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Category              | Parameter             | Description                                                                                                                                                                                                                                                                                                                 |
      +=======================+=======================+=============================================================================================================================================================================================================================================================================================================================+
      | ``-``                 | Rule Name             | Silence rule name, which can contain up to 100 characters and cannot start or end with an underscore (_). Only letters, digits, and underscores are allowed.                                                                                                                                                                |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Description           | Silence rule description, which can contain up to 1024 characters.                                                                                                                                                                                                                                                          |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Silence rules         | Silence Condition     | Any alarm notifications that meet the silence condition will be shielded.                                                                                                                                                                                                                                                   |
      |                       |                       |                                                                                                                                                                                                                                                                                                                             |
      |                       |                       | You can create up to 10 parallel conditions under **Silence Condition**, and up to 10 serial conditions under each parallel condition. Serial conditions are in the AND relationship whereas parallel conditions are in the OR relationship. An alarm must meet all serial conditions under one of the parallel conditions. |
      |                       |                       |                                                                                                                                                                                                                                                                                                                             |
      |                       |                       | For a serial condition, if **Alarm Severity** is set to **Critical**, critical alarms are shielded.                                                                                                                                                                                                                         |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Silence Time          | Time when alarm notifications are shielded. There are two options:                                                                                                                                                                                                                                                          |
      |                       |                       |                                                                                                                                                                                                                                                                                                                             |
      |                       |                       | -  Fixed time: Alarm notifications are shielded only in a specified period.                                                                                                                                                                                                                                                 |
      |                       |                       | -  Cycle time: Alarm notifications are shielded periodically.                                                                                                                                                                                                                                                               |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Time Zone/Language    | Time zone and language for which alarm notifications are shielded. The time zone and language configured in **Preferences** are selected by default. You can change them as required.                                                                                                                                       |
      +-----------------------+-----------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **Create Now**.

More Operations
---------------

After creating a silence rule, perform the operations listed in :ref:`Table 2 <aom_02_0954__en-us_topic_0000001216560092_en-us_topic_0169698264_table14918185010104>` if needed.

.. _aom_02_0954__en-us_topic_0000001216560092_en-us_topic_0169698264_table14918185010104:

.. table:: **Table 2** Related operations

   +-----------------------------------+-------------------------------------------------------------------------------------------------------------+
   | Operation                         | Description                                                                                                 |
   +===================================+=============================================================================================================+
   | Modifying a silence rule          | Click **Modify** in the **Operation** column.                                                               |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------+
   | Deleting a silence rule           | -  To delete a single rule, click **Delete** in the **Operation** column in the row that contains the rule. |
   |                                   | -  To delete one or more rules, select them and click **Delete** above the rule list.                       |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------+
   | Searching for a silence rule      | Enter a rule name in the search box in the upper right corner and click |image1|.                           |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001261759905.png
