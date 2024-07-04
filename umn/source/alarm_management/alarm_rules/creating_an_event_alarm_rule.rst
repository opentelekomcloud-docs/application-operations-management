:original_name: aom_02_0061.html

.. _aom_02_0061:

Creating an Event Alarm Rule
============================

You can set event conditions for services by setting event alarm rules. When the resource data meets an event condition, an event alarm is generated.

Precautions
-----------

If you want to receive email or SMS notifications when the resource data meets the event condition, set an alarm action rule according to :ref:`Creating an Alarm Action Rule <aom_02_0926>`.

Procedure
---------

#. Log in to the AOM console. In the navigation pane, choose **Alarm Center** > **Alarm Rules**. Then, click **Create Alarm Rule** in the upper right corner.

#. Set an event alarm rule.

   a. Set basic information such as the rule name and description.


      .. figure:: /_static/images/en-us_image_0000001461323461.png
         :alt: **Figure 1** Setting basic information

         **Figure 1** Setting basic information

   b. Set details about the rule.

      #. Set **Rule Type** to **Event alarm**.

      #. Set the alarm source, trigger object, and trigger policy.

         .. table:: **Table 1** Alarm rule parameters

            +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            | Parameter                         | Description                                                                                                                                                                                                                                  |
            +===================================+==============================================================================================================================================================================================================================================+
            | Alarm Source                      | Name of the service for which an event alarm is reported. You can select a service from the service list.                                                                                                                                    |
            +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            | Trigger Object                    | Select criteria to filter service events. You can select **Notification Type**, **Event Name**, **Alarm Severity**, **Custom Attributes**, **Namespace**, or **Cluster Name** as the filter criterion. One or more criteria can be selected. |
            +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            | Trigger Policy                    | Policy for triggering event alarms.                                                                                                                                                                                                          |
            |                                   |                                                                                                                                                                                                                                              |
            |                                   | -  **Accumulated Triggering**: An alarm action rule is triggered when the accumulated number of times you preset is reached in a monitoring period.                                                                                          |
            |                                   | -  **Immediate Triggering**: An alarm is generated immediately when the filter criterion is met.                                                                                                                                             |
            +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+


         .. figure:: /_static/images/en-us_image_0000001410883828.png
            :alt: **Figure 2** Setting an alarm rule

            **Figure 2** Setting an alarm rule

   c. Set an alarm notification policy. There are two alarm notification modes.

      -  **Direct Alarm Reporting**: An alarm is directly sent when the alarm condition is met.

         You need to configure whether to enable an alarm action rule. After this function is enabled, the system sends alarm notifications based on the associated SMN topic and message template. If the existing alarm action rules cannot meet your requirements, click **Create Rule** to create one. For details, see :ref:`Creating an Alarm Action Rule <aom_02_0926>`.


         .. figure:: /_static/images/en-us_image_0000001462893469.png
            :alt: **Figure 3** Selecting the direct alarm reporting mode

            **Figure 3** Selecting the direct alarm reporting mode

      -  **Alarm Noise Reduction**: Alarms are sent only after being processed based on noise reduction rules, preventing alarm storms.

         Select a grouping rule from the drop-down list. If existing grouping rules cannot meet your requirements, click **Create Rule** to create one. For details, see :ref:`Creating a Grouping Rule <aom_02_0952>`.


         .. figure:: /_static/images/en-us_image_0000001413081586.png
            :alt: **Figure 4** Selecting the alarm noise reduction mode

            **Figure 4** Selecting the alarm noise reduction mode

#. Click **Create Now**. An event alarm rule is created, as shown in the following figure.

   This rule monitors critical alarm events of AOM. When a service event meets the preset notification policy, the system sends an alarm notification to specified personnel by email or SMS.


   .. figure:: /_static/images/en-us_image_0000001462896701.png
      :alt: **Figure 5** Event alarm rule

      **Figure 5** Event alarm rule

Related Operations
------------------

After creating an event alarm rule, perform the operations listed in :ref:`Table 2 <aom_02_0061__en-us_topic_0263893589_en-us_topic_0169698491_table289773015816>` if needed.

.. _aom_02_0061__en-us_topic_0263893589_en-us_topic_0169698491_table289773015816:

.. table:: **Table 2** Related operations

   +------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                                | Description                                                                                                                                                 |
   +==========================================+=============================================================================================================================================================+
   | Editing an event alarm rule              | Click **Edit** in the **Operation** column.                                                                                                                 |
   +------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Deleting event alarm rules               | -  To delete an event alarm rule, click **Delete** in the **Operation** column.                                                                             |
   |                                          | -  To delete one or more event alarm rules, select the check boxes before them and click **Delete** above the rule list.                                    |
   +------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Starting or stopping an event alarm rule | Click **Start** or **Stop** in the **Operation** column.                                                                                                    |
   +------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Searching for an event alarm rule        | You can search for a rule by rule name, description, or metric name. Simply enter a keyword in the search box in the upper right corner and click |image1|. |
   +------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001233445193.png
