:original_name: aom_02_0951.html

.. _aom_02_0951:

Overview
========

AOM supports alarm noise reduction. Alarms can be processed based on the alarm noise reduction rules to prevent notification storms.

Alarm noise reduction consists of four parts: grouping, deduplication, suppression, and silence.

AOM uses built-in deduplication rules. The service backend automatically deduplicates alarms. You do not need to manually create rules.


.. figure:: /_static/images/en-us_image_0000001353985836.png
   :alt: **Figure 1** Alarm noise reduction process

   **Figure 1** Alarm noise reduction process

You need to manually create grouping, suppression, and silence rules. For details, see the following description.

.. note::

   #. This module is used only for message notification. All triggered alarms and events can be viewed on the **Alarm List** and **Event List** pages.

   #. All conditions of alarm noise reduction rules are obtained from **metadata** in alarm structs. You can use the default fields or customize your own fields.

      .. code-block::

         {
             "starts_at" : 1579420868000,
             "ends_at" : 1579420868000,
             "timeout" : 60000,
             "resource_group_id" : "5680587ab6*******755c543c1f",
             "metadata" : {
               "event_name" : "test",
               "event_severity" : "Major",
               "event_type" : "alarm",
               "resource_provider" : "ecs",
               "resource_type" : "vm",
               "resource_id" : "ecs123" ,
               "key1" : "value1"   // Alarm tag configured when the alarm rule is created
          },
             "annotations" : {
                "alarm_probableCause_en_us": " Possible causes",
               "alarm_fix_suggestion_en_us": "Handling suggestion"
           }
         }
