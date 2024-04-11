:original_name: aom_02_0041.html

.. _aom_02_0041:

O&M
===

The **O&M** page supports full-link, multi-layer, and one-stop O&M for resources, applications, and user experience. Specifically, this page displays the following types of cards: infrastructure monitoring, application monitoring, alarm statistics, host monitoring (CPU and memory), component monitoring (CPU and memory), container instance monitoring (CPU and memory), host monitoring (disk), host monitoring (network), cluster monitoring (CPU and memory), and cluster monitoring (disk) cards.

Infrastructure Monitoring Card
------------------------------


.. figure:: /_static/images/en-us_image_0000001471047065.png
   :alt: **Figure 1** Infrastructure monitoring

   **Figure 1** Infrastructure monitoring

This card mainly displays infrastructure metrics. You can select one or all clusters to view their details. When you select all clusters, the following information is displayed:

-  Host running status, CPU usage, and physical memory usage.
-  Trend graph of network traffic in the last 30 minutes. The values of each point in the graph respectively indicate the total downlink/uplink rates of all clusters in one minute. The values displayed above the trend graph respectively indicate the total downlink/uplink rates of all clusters at the latest time point.
-  Trend graph of CPU and memory usage in the last 30 minutes. The values of each point in the graph respectively indicate the average CPU and memory usage of all clusters in one minute. The values above the graph respectively indicate the average CPU and memory usage of all clusters at the latest time point.

Application Monitoring Card
---------------------------


.. figure:: /_static/images/en-us_image_0000001420570268.png
   :alt: **Figure 2** Application monitoring

   **Figure 2** Application monitoring

This card mainly displays application metrics:

#. Running status of applications, components, containers, and instances.
#. When you select an application, the following information is displayed:

   -  Trend graph of network traffic in the last 30 minutes. The values of each point in the graph respectively indicate the receive rate (BPS) and send rate (BPS) of the selected application in one minute. The values above the graph respectively indicate the receive rate (BPS) and send rate (BPS) of the selected application at the latest time point.
   -  Trend graph of CPU and memory usage in the last 30 minutes. The values of each point in the graph respectively indicate the CPU and memory usage of the selected application in one minute. The values above the graph respectively indicate the CPU and memory usage of the selected application at the latest time point.

Alarm Statistics Card
---------------------


.. figure:: /_static/images/en-us_image_0000001462784353.png
   :alt: **Figure 3** Alarm statistics

   **Figure 3** Alarm statistics

This card mainly displays alarms, log usage, threshold rules, and trends of alarms and hosts.

Component Monitoring (CPU and Memory) Card
------------------------------------------


.. figure:: /_static/images/en-us_image_0000001461502857.png
   :alt: **Figure 4** Component monitoring (CPU and memory)

   **Figure 4** Component monitoring (CPU and memory)

This card mainly displays:

-  The top 5 components with high CPU and memory usage in the last minute.
-  Trend graph of the CPU and memory usage of the selected component in the last hour. The values of each point in the graph respectively indicate the CPU and memory usage of the component in one minute.
-  CPU and memory usage of the selected component at the latest time point, which is displayed above the trend graph.
-  You can select **Hide system components** in the lower left corner.

Cluster Monitoring (Disk) Card
------------------------------


.. figure:: /_static/images/en-us_image_0000001411262784.png
   :alt: **Figure 5** Cluster monitoring (disk)

   **Figure 5** Cluster monitoring (disk)

Container Instance Monitoring (CPU and Memory) Card
---------------------------------------------------


.. figure:: /_static/images/en-us_image_0000001461281269.png
   :alt: **Figure 6** Container instance monitoring (CPU and memory)

   **Figure 6** Container instance monitoring (CPU and memory)

This card mainly displays:

-  The top 5 container instances with high CPU and memory usage in the last minute.
-  Trend graph of the CPU and memory usage of the selected container instance in the last hour. The values of each point in the graph respectively indicate the CPU and memory usage of the container instance in one minute.
-  CPU and memory usage of the selected container instance at the latest time point, which is displayed above the trend graph.
-  You can select **Hide system instances** in the lower left corner.

Host Monitoring (Disk) Card
---------------------------


.. figure:: /_static/images/en-us_image_0000001461822513.png
   :alt: **Figure 7** Host monitoring (disk)

   **Figure 7** Host monitoring (disk)

This card mainly displays:

-  The top 5 hosts with high disk read/write rate in the last minute.
-  Trend graph of the disk read/write rate of the selected host in the last hour. The values of each point in the graph respectively indicate the disk read/write rate of the selected host in one minute.
-  Disk read/write rate of the selected host at the latest time point, which is displayed above the trend graph.

Host Monitoring (Network) Card
------------------------------


.. figure:: /_static/images/en-us_image_0000001461862497.png
   :alt: **Figure 8** Host monitoring (network)

   **Figure 8** Host monitoring (network)

This card mainly displays:

-  The top 5 hosts with high send/receive rate in the last minute.
-  Trend graph of the send/receive rate of the selected host in the last hour. The values of each point in the graph respectively indicate the send/receive rate of the selected host in one minute.
-  Send/receive rate of the selected host at the latest time point, which is displayed above the trend graph.

Host Monitoring (CPU and Memory) Card
-------------------------------------


.. figure:: /_static/images/en-us_image_0000001411102964.png
   :alt: **Figure 9** Host monitoring (CPU and memory)

   **Figure 9** Host monitoring (CPU and memory)

This card mainly displays:

-  The top 5 hosts with high CPU and memory usage in the last minute.
-  Trend graph of the CPU and memory usage of the selected host in the last hour. The values of each point in the graph respectively indicate the CPU and memory usage of the host in one minute.
-  CPU and memory usage of the selected host at the latest time point, which is displayed above the trend graph.

Cluster Monitoring (CPU and Memory) Card
----------------------------------------


.. figure:: /_static/images/en-us_image_0000001410943068.png
   :alt: **Figure 10** Cluster monitoring (CPU and memory)

   **Figure 10** Cluster monitoring (CPU and memory)

This card mainly displays:

-  The top 5 clusters with high CPU and memory usage in the last minute.
-  Trend graph of the CPU and memory usage of the selected cluster in the last hour. The values of each point in the graph respectively indicate the CPU and memory usage of the cluster in one minute.
-  CPU and memory usage of the selected cluster at the latest time point, which is displayed above the trend graph.

More Operations
---------------

Perform the operations listed in :ref:`Table 1 <aom_02_0041__en-us_topic_0263893656_table62191141172620>` if needed.

.. _aom_02_0041__en-us_topic_0263893656_table62191141172620:

.. table:: **Table 1** Related operations

   +----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                  | Description                                                                                                                                                                                                                     |
   +============================+=================================================================================================================================================================================================================================+
   | Adding a card to favorites | To hide a card, click |image4| in the upper right corner of the card and choose **Add to Favorites**. After a card is added to favorites, it is hidden from the **O&M** page. To view the card later, obtain it from favorites. |
   +----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Adding a card to dashboard | Click |image5| in the upper right corner of the card and choose **Add to Dashboard**.                                                                                                                                           |
   +----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Zooming in a metric graph  | Click |image6| in the upper right corner of the metric graph.                                                                                                                                                                   |
   +----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Drilling down blue texts   | Click the blue texts, such as **Host**, **Application**, or **Component** to drill down to the details page.                                                                                                                    |
   +----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0263893663.png
.. |image2| image:: /_static/images/en-us_image_0263893651.png
.. |image3| image:: /_static/images/en-us_image_0263893592.png
.. |image4| image:: /_static/images/en-us_image_0263893663.png
.. |image5| image:: /_static/images/en-us_image_0263893651.png
.. |image6| image:: /_static/images/en-us_image_0263893592.png
