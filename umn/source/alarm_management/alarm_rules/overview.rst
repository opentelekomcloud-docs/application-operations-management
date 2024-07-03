:original_name: aom_02_0062.html

.. _aom_02_0062:

Overview
========

By setting alarms rules, you can define event conditions for services or threshold conditions for resource metrics. If the resource data of a service meets the event condition, an event alarm will be generated. If a metric value meets a threshold condition, a threshold alarm will be reported. If there is no metric data, an insufficient data event will be reported.

Alarm rules are classified into threshold rules and event alarm rules. Generally, threshold rules monitor the usage of resources such as hosts and components in real time. If there are too many resource usage alarms and notifications are sent too often, use an event alarm rule to identify a type of resource usage problems for simplified notification.

The total number of threshold rules and event alarm rules is 1000. If the number of alarm rules has reached the upper limit, delete unnecessary rules and create new ones.
