:original_name: aom_02_0926.html

.. _aom_02_0926:

Creating an Alarm Action Rule
=============================

Prerequisites
-------------

-  A topic has been created.
-  A topic policy has been set.
-  A subscriber, that is, an email or SMS message recipient has been added to the topic.

Precaution
----------

You can create a maximum of 1000 alarm action rules. If this number has been reached, delete unnecessary rules.

Procedure
---------

#. Log in to the AOM console. In the navigation pane, choose **Alarm Center** > **Alarm Action Rules**. On the displayed page, click **Create** in the upper left corner.

#. Set parameters such as **Rule Name** and **Action Type**.


   .. figure:: /_static/images/en-us_image_0000001462367929.png
      :alt: **Figure 1** Creating an alarm action rule

      **Figure 1** Creating an alarm action rule

   .. table:: **Table 1** Parameters for configuring an alarm action rule

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                   |
      +===================================+===============================================================================================================================================================================+
      | Rule Name                         | Name of an action rule. Enter 3 to 36 characters, and do not start or end with an underscore (_). Only digits, letters, and underscores are allowed.                          |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Description of the action rule.                                                                                                                                               |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Action Type                       | Type of action that is associated with the SMN topic and message template. Select your desired action from the drop-down list. Currently, only **Notification** is supported. |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Topic                             | SMN topic. Select your desired topic from the drop-down list.                                                                                                                 |
      |                                   |                                                                                                                                                                               |
      |                                   | If there is no topic you want to select, create one on the SMN console.                                                                                                       |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Message Template                  | Notification message template. Select your desired template from the drop-down list.                                                                                          |
      |                                   |                                                                                                                                                                               |
      |                                   | If there is no message template you want to select, create one by referring to :ref:`Creating a Message Template <aom_02_0927>`.                                              |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

3. Click **OK**.

More Operations
---------------

After an alarm action rule is created, you can perform operations described in :ref:`Table 2 <aom_02_0926__en-us_topic_0000001164001658_en-us_topic_0169698264_table14918185010104>`.

.. _aom_02_0926__en-us_topic_0000001164001658_en-us_topic_0169698264_table14918185010104:

.. table:: **Table 2** Related operations

   +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                          | Description                                                                                                                                               |
   +====================================+===========================================================================================================================================================+
   | Modifying an alarm action rule     | Click **Edit** in the **Operation** column.                                                                                                               |
   +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Deleting an alarm action rule      | -  To delete a single rule, click **Delete** in the **Operation** column in the row that contains the rule, and then click **Yes** on the displayed page. |
   |                                    | -  To delete one or more rules, select them, click **Delete** above the rule list, and then click **Yes** on the displayed page.                          |
   |                                    |                                                                                                                                                           |
   |                                    |    .. note::                                                                                                                                              |
   |                                    |                                                                                                                                                           |
   |                                    |       Before deleting an alarm action rule, you need to delete the alarm rule bound to the action rule.                                                   |
   +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Searching for an alarm action rule | Enter a rule name in the search box in the upper right corner and click |image1|.                                                                         |
   +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001410807236.png
