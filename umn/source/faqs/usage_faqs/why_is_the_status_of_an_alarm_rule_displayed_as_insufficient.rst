:original_name: aom_03_0022.html

.. _aom_03_0022:

Why Is the Status of an Alarm Rule Displayed as "Insufficient"?
===============================================================

When you create an alarm rule for a resource, its data reported to AOM may be insufficient, as shown in the following figure.


.. figure:: /_static/images/en-us_image_0000001412030430.png
   :alt: **Figure 1** Viewing the rule status

   **Figure 1** Viewing the rule status

Possible causes:

#. The data reporting latency is too large. That is, the difference between the latest data reporting time of the line graph and the current time is greater than one threshold reporting period, which can be set to 1 minute or 5 minutes. If no data is obtained within such a period, a message indicating insufficient data is displayed.
#. If a metric is deleted or the host to which the metric belongs does not exist but the threshold rule still exists, a message indicating insufficient data is displayed.
