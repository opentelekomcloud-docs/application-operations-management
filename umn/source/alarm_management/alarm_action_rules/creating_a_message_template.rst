:original_name: aom_02_0927.html

.. _aom_02_0927:

Creating a Message Template
===========================

You can create message templates to customize notifications. When a preset notification rule is triggered, notifications can be sent to specified personnel by emails, SMS, voice calls, HTTP, or HTTPS. If no message template is created, the default message template will be used.


Creating a Message Template
---------------------------

#. Log in to the AOM console and choose **Alarm Center** > **Alarm Action Rules** in the navigation pane. On the displayed page, click the **Message Templates** tab.
#. On the **Message Templates** page, click **Create**.

   a. Enter a template name.

   b. Enter a template description.

   c. Select a language.

   d. Customize the template content. (Default fields are automatically filled when a message template is created.)

      .. note::

         -  You can create up to 100 message templates. If this number has been reached, delete unnecessary templates.
         -  There are two default message templates. If you do not customize any message template, notifications will be sent based on default templates. The default templates cannot be deleted or edited.
         -  In addition to default fields, the message template also allows you to add custom fields. You need to define values for custom fields for event alarm reporting. For details about the parameters, see the alarm reporting structs in the following message template.
         -  Custom fields support the JSONPath format. Example: **$event.metadata.case1** or **$event.metadata.case[0]**.
         -  In the upper right corner of the **Body** area, click **Add Variables** to add required variables.
         -  If you select **Email**, you can click **Preview** to view the final effect. On the **Preview** page, change the message topic if necessary.

      .. _aom_02_0927__en-us_topic_0000001209600139_table08437353016:

      .. table:: **Table 1** Variables in the default message template

         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+
         | Variable            | Description                                                                                  | Definition                        |
         +=====================+==============================================================================================+===================================+
         | OTC account         | Account used to log in to the management console.                                            | ${domain_name}                    |
         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+
         | Notification Type   | Type selected when a notification rule is created, which can be **Alarm** or **Event**.      | ${event_type}                     |
         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+
         | Severity            | Alarm or event severity, which can be **Critical**, **Major**, **Minor**, or **Warning**.    | ${event_severity}                 |
         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+
         | Name                | Name of the alarm or event that triggers the notification rule.                              | $event.metadata.event_name        |
         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+
         | Occurred            | Time when the alarm or event is triggered.                                                   | ${starts_at}                      |
         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+
         | Source              | Name of the service corresponding to the alarm or event that triggers the notification rule. | $event.metadata.resource_provider |
         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+
         | Resource Type       | Type of the resource selected when you customize a threshold rule or define alarm reporting. | $event.metadata.resource_type     |
         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+
         | Resource Identifier | Resource that triggers the alarm or event.                                                   | ${resources}                      |
         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+
         | Custom tag          | Extended tag.                                                                                | $event.metadata.key1              |
         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+
         | Possible Cause      | Cause of the alarm. For non-custom reporting, "NA" is displayed.                             | ${alarm_probableCause_zh}         |
         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+
         | Additional Info     | Additional alarm description, such as the metric name and alarm rule status change.          | ${message}                        |
         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+
         | Suggestion          | Suggestion on how to handle the alarm. For non-custom reporting, "NA" is displayed.          | ${alarm_fix_suggestion_zh}        |
         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+
         | Custom annotation   | Extended annotation.                                                                         | $event.annotations.key2           |
         +---------------------+----------------------------------------------------------------------------------------------+-----------------------------------+

      Alarm reporting structs corresponding to the message template

      .. code-block::

         {
             "event": {
                 "starts_at": 1579420868000,       //${starts_at}
                         "ends_at": 1579420868000,
                 "timeout": 60000,
                 "resource_group_id": "5680587ab6*******755c543c1f",
                 "metadata": {
                     "event_name": "test",         //${metadata.event_name}
                     "event_severity": "Major",    //${metadata.event_severity}
                     "event_type": "alarm",        //${metadata.event_type}
                     "resource_provider": "ecs",   //${metadata.resource_provider}
                     "resource_type": "vm",        //${metadata.resource_type}
                     "resource_id": "ecs123",
                     "key1": "Custom field"          //$event.metadata.key1
                 },
                 "annotations": {
                     "alarm_probableCause_zh_cn": "possible cause",     //${annotations.alarm_probableCause_zh}
                     "alarm_fix_suggestion_zh_cn": "fix suggestion",    //${annotations.alarm_fix_suggestion_zh}
                     "key2": "Custom field"    //$event.annotations.key2
                 }
             }
         }

   e. Click **Confirm**. The message template is created.

More Operations
---------------

After creating a message template, you can perform the operations listed in :ref:`Table 2 <aom_02_0927__en-us_topic_0000001209600139_en-us_topic_0169698264_table14918185010104>`.

.. _aom_02_0927__en-us_topic_0000001209600139_en-us_topic_0169698264_table14918185010104:

.. table:: **Table 2** Related operations

   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                         | Description                                                                                                                                                               |
   +===================================+===========================================================================================================================================================================+
   | Editing a message template        | Click **Edit** in the **Operation** column.                                                                                                                               |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Copying a message template        | Click **Copy** in the **Operation** column.                                                                                                                               |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Deleting a message template       | -  To delete a single message template, click **Delete** in the **Operation** column in the row that contains the template, and then click **Yes** on the displayed page. |
   |                                   | -  To delete one or more message templates, select them, and click **Delete** above the template list, and then click **Yes** on the displayed page.                      |
   |                                   |                                                                                                                                                                           |
   |                                   |    .. note::                                                                                                                                                              |
   |                                   |                                                                                                                                                                           |
   |                                   |       Before deleting a message template, you need to delete the alarm action rules bound to it.                                                                          |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Searching for a message template  | Enter a template name in the search box in the upper right corner and click |image1|.                                                                                     |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001411990512.png
