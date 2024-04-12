:original_name: aom_02_0017.html

.. _aom_02_0017:

Metric Monitoring
=================

The **Metric Monitoring** page displays metric data of each resource. You can monitor metric values and trends in real time, and create threshold rules for desired metrics. In this way, you can monitor services in real time and perform data correlation analysis.

Procedure
---------

#. In the navigation pane, choose **Monitoring** > **Metric Monitoring**.

#. Then, click **Add Metric** and select **Dimension** or **Resource** for **Add By**. Select up to 12 metrics to monitor.

#. Set metric parameters according to :ref:`Table 1 <aom_02_0017__en-us_topic_0263893547_d0e3947>`, view the metric graph in the upper part of the page, and analyze metric data from multiple dimensions.

   .. _aom_02_0017__en-us_topic_0263893547_d0e3947:

   .. table:: **Table 1** Metric parameters

      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                            |
      +===================================+========================================================================================================================================================================+
      | Statistical Mode                  | Method used to measure metrics. Options: **Average**, **Minimum**, **Maximum**, **Sum**, and **SampleCount**.                                                          |
      |                                   |                                                                                                                                                                        |
      |                                   | .. note::                                                                                                                                                              |
      |                                   |                                                                                                                                                                        |
      |                                   |    The number of samples equals to the count of data points.                                                                                                           |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Statistical Cycle                 | Interval at which metric data is collected.                                                                                                                            |
      |                                   |                                                                                                                                                                        |
      |                                   | The statistical cycles that are available for you to select vary according to the time range.                                                                          |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Time Range                        | Time range in which metric data is collected. Options: **Last 30 minutes**, **Last 1 hour**, **Last 6 hours**, **Last 1 day**, **Last 1 week**, and **Custom**.        |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Refresh Frequency                 | Interval at which the metric data is refreshed. Options: **Refresh manually**, **30 seconds auto refresh**, **1 minute auto refresh**, and **5 minutes auto refresh**. |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

More Operations
---------------

You can also perform the operations listed in :ref:`Table 2 <aom_02_0017__en-us_topic_0263893547_table1679219139498>`.

.. _aom_02_0017__en-us_topic_0263893547_table1679219139498:

.. table:: **Table 2** Related operations

   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                         | Description                                                                                                                                                                                                                                               |
   +===================================+===========================================================================================================================================================================================================================================================+
   | Hiding/Showing metric data        | After selecting a metric, click |image1| in the **Operation** column to hide the metric data in the current graph. To show the metric data again, click |image2| in the **Operation** column. |image3| and |image4| indicate the statuses of metric data. |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Adding an alarm rule for a metric | After selecting a metric, click |image5| in the **Operation** column to create an alarm rule for it.                                                                                                                                                      |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Copying metric data               | After selecting a metric, click |image6| in the **Operation** column to copy the metric data.                                                                                                                                                             |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Deleting one or more metrics      | -  To delete a metric, click |image7| in the **Operation** column.                                                                                                                                                                                        |
   |                                   | -  To delete one or more metrics, select them and click **Delete** above the metric list.                                                                                                                                                                 |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Exporting a monitoring report     | Click **Export Report** to export a metric graph as a CSV file to your local PC.                                                                                                                                                                          |
   +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001410950444.png
.. |image2| image:: /_static/images/en-us_image_0000001461628997.png
.. |image3| image:: /_static/images/en-us_image_0000001411110332.png
.. |image4| image:: /_static/images/en-us_image_0000001461509173.png
.. |image5| image:: /_static/images/en-us_image_0000001461868817.png
.. |image6| image:: /_static/images/en-us_image_0000001411429104.png
.. |image7| image:: /_static/images/en-us_image_0000001461509265.png
