:original_name: aom_02_0113.html

.. _aom_02_0113:

Alarm Tags and Annotations
==========================

When creating alarm rules, you can set alarm tags and annotations. Tags are attributes that can be used to identify alarms. They are applied to the alarm noise reduction scenario. Annotations are attributes that cannot be used to identify alarms. They are applied to scenarios such as alarm notification and message templates.

Alarm Tags
----------

-  Alarm tags can apply to grouping rules, suppression rules, and silence rules. The alarm management system manages alarms and notifications based on the tags.
-  Each tag is in "key:value" format and can be customized. The key and value can contain only letters, digits, and underscores (_) and cannot start with an underscore (_). You can create up to 10 custom tags.
-  If you set a tag when creating an alarm rule, the tag is automatically added as an alarm attribute when an alarm is triggered.
-  In the message template, the **$event.metadata.key1** variable specifies the tag. For details, see :ref:`Table 1 <aom_02_0927__en-us_topic_0000001209600139_table08437353016>`.

Alarm Annotations
-----------------

-  Annotations are attributes that cannot be used to identify alarms. They are applied to scenarios such as alarm notification and message templates.
-  Each annotation is in "key:value" format and can be customized. The key and value can contain only letters, digits, and underscores (_) and cannot start with an underscore (_). You can create up to 10 custom annotations.
-  In the message template, the **$event.annotations.key2** variable specifies the annotation. For details, see :ref:`Table 1 <aom_02_0927__en-us_topic_0000001209600139_table08437353016>`.
