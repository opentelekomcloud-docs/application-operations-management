:original_name: aom_02_1035.html

.. _aom_02_1035:

Creating Threshold Rules
========================

To use threshold rules, customize threshold conditions first. If a metric value meets a threshold condition, AOM generates a threshold alarm. If no metric data is reported, AOM generates an insufficient data event.

AOM is interconnected with Simple Message Notification (SMN). After you :ref:`set a notification policy <aom_02_1035__en-us_topic_0141087247_li7359182111811>` on the SMN console, notifications are sent by email or Short Message Service (SMS) message if the threshold rule status (**Exceeded**, **OK**, or **Insufficient**) changes. In this way, you can identify and handle exceptions at the earliest time.

Precautions
-----------

-  You can create a maximum of 1000 threshold rules. To create more rules when the maximum number is reached, delete unnecessary rules.

-  .. _aom_02_1035__en-us_topic_0141087247_li7359182111811:

   Setting a notification policy

   To send notifications by email or SMS message if the threshold rule status (**Exceeded**, **OK**, or **Insufficient**) changes, set a notification policy on the SMN console according to the following procedure. If you do not need to receive notifications by email or SMS message, skip the following operations. Procedure:

   #. Create a topic by referring to `Creating a Topic <https://docs.otc.t-systems.com/en-us/usermanual/smn/en-us_topic_0043961401.html>`__.

   #. Set a topic policy by referring to `Configuring Topic Policies <https://docs.otc.t-systems.com/en-us/usermanual/smn/en-us_topic_0043394891.html>`__.

      Select **apm** for **Services that can publish messages to this topic**. Otherwise, notifications cannot be sent.

   #. Add a subscriber (email or SMS message recipient) for the topic by referring to `Adding a Subscription <https://docs.otc.t-systems.com/en-us/usermanual/smn/en-us_topic_0043961402.html>`__.


Creating Threshold Rules
------------------------

#. Log in to the management console.

#. Under **Application**, click **Application Operations Management**.

#. In the navigation pane, choose **Alarm Center** > **Threshold Rules**. Then, click **Add Threshold Rule** in the upper right corner.

#. Create a threshold rule.

   a. Select resources: Enter a threshold rule name, select a resource type, select the resources to be monitored from the resource tree, and click **Next**.

      .. note::

         -  You can select a maximum of 10 resources from the resource tree.

         -  When multiple resources are selected, multiple threshold rules will be created after the creation is complete. Each resource is monitored by a threshold rule. A rule name consists of the threshold rule name you enter in the **Threshold Name** text box, and a sequence number ranging from 0 to 99. The earlier a resource is selected, the smaller its sequence number.

            For example, enter **Monitor_Host_cpuUsage** in the **Threshold Name** text box and select the **aom-1** host and then the **aom-2** host from the resource tree. In this way, threshold rules **Monitor_Host_cpuUsage0** and **Monitor_Host_cpuUsage1** will be generated. The former monitors the **aom-1** host while the latter monitors the **aom-2** host.


      .. figure:: /_static/images/en-us_image_0297183034.png
         :alt: **Figure 1** Selecting resources

         **Figure 1** Selecting resources

   b. Customize a threshold. Specifically, select the metric to be monitored, and set parameters such as **Threshold Condition**, **Consecutive Period (s)**, **Alarm Severity**, **Statistic**, and **Send Notification**.

      .. note::

         -  **Threshold Condition**: Trigger condition of a threshold alarm. A threshold condition consists of two parts: determination condition (>=, <=, >, or <) and threshold value. For example, if **Threshold Condition** is set to **> 85** and an actual metric value exceeds 85, a threshold alarm will be generated.

         -  **Consecutive Period (s)**: If a metric value meets the threshold condition for a specified number of consecutive periods, a threshold alarm will be generated.

         -  **Statistic**: Method used to measure metrics.

         -  **Statistical Period**: Interval at which metric data is collected. The system collects a data point every minute to determine the status of the threshold rule.

         -  **Send Notification**: Whether to send a notification by email or SMS message if the threshold rule status (**Exceeded**, **OK**, or **Insufficient**) changes.

            -  If you need to receive notifications by email or SMS message, select **Yes**, :ref:`set a notification policy <aom_02_1035__en-us_topic_0141087247_li7359182111811>`, select the created topic, and select a trigger condition.
            -  If you do not need to receive notifications by email or SMS message, select **No**.

         -  **Trigger Condition**: Condition for sending notifications.

            You can select multiple trigger conditions for a threshold rule. For example, to receive notifications if the threshold status changes to **Exceeded**, select **Threshold crossing**. To receive notifications upon any threshold status change, select all trigger conditions.


      .. figure:: /_static/images/en-us_image_0000001415472973.png
         :alt: **Figure 2** Customizing a threshold

         **Figure 2** Customizing a threshold

#. Click **Submit**. As shown in the following figure, multiple threshold rules are created. Each resource is monitored by an independent rule.

   If the CPU usage of a host exceeds 85%, a threshold alarm is generated on the alarm page. You can choose **Alarm Center** > **Alarms** in the navigation pane to view the alarm. If the host meets the preset notification policy, an email or SMS message will be sent to the specified recipient.


   .. figure:: /_static/images/en-us_image_0297183036.png
      :alt: **Figure 3** Threshold rules

      **Figure 3** Threshold rules

Related Operations
------------------

After creating a threshold rule, you can also perform the operations described in :ref:`Table 1 <aom_02_1035__en-us_topic_0141087247_table289773015816>`.

.. _aom_02_1035__en-us_topic_0141087247_table289773015816:

.. table:: **Table 1** Related operations

   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                         | Description                                                                                                                                   |
   +===================================+===============================================================================================================================================+
   | Modify a threshold rule           | Click **Modify** in the **Operation** column.                                                                                                 |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
   | Delete a threshold rule           | -  To delete a threshold rule, click **Delete** in the **Operation** column.                                                                  |
   |                                   | -  To delete one or more threshold rules, select them and click **Delete** above the threshold rule list.                                     |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
   | Search for a threshold rule       | Enter a keyword of the threshold rule name in the search box in the upper right corner and click |image1|.                                    |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
   | View a threshold rule             | Click |image2| next to a threshold rule to view its details.                                                                                  |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
   | View an alarm                     | If the metric value of a resource meets a threshold condition in the specified number of consecutive periods, a threshold alarm will be sent. |
   |                                   |                                                                                                                                               |
   |                                   | In the navigation pane, choose **Alarm Center** > **Alarms** to view the alarm.                                                               |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
   | View an event                     | During the configured consecutive periods, if no metric data of a resource is reported, an insufficient data event will be sent.              |
   |                                   |                                                                                                                                               |
   |                                   | In the navigation pane, choose **Alarm Center** > **Events** to view the event.                                                               |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0297183037.png
.. |image2| image:: /_static/images/en-us_image_0297183038.png
