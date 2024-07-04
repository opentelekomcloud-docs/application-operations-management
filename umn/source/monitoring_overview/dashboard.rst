:original_name: aom_02_0003.html

.. _aom_02_0003:

Dashboard
=========

With a dashboard, different graphs such as line graphs and digit graphs are displayed on the same screen, which lets you view comprehensive monitoring data.

For example, you can add key metrics of important resources to the dashboard for real-time monitoring. You can also compare the same metric for different resources on one GUI. In addition, you can add routine O&M metrics to the dashboard so that you can perform routine check without re-selecting metrics when you re-open AOM.

Before creating a dashboard, learn the types of graphs that can be added to the dashboard for accurate resource monitoring. The following graphs can be added to the dashboard:

Metric Data Graphs (Including Line and Digit Graphs)
----------------------------------------------------

-  **Line graph**: displays the metric data trend by time. Use this type of graph to monitor the metric data trend of one or more resources in a period.

   You can use a line graph to compare the same metric of different resources. The following figure shows the total CPU cores of different components.


   .. figure:: /_static/images/en-us_image_0000001411325438.png
      :alt: **Figure 1** Line graph

      **Figure 1** Line graph

-  **Digit graph**: displays the latest value of a metric in real time.

   The following figure shows the average uplink rate (BPS) of a component.


   .. figure:: /_static/images/en-us_image_0000001461164845.png
      :alt: **Figure 2** Digit graph

      **Figure 2** Digit graph

Health Status Graphs (Including Threshold, Host, and Component Status Graphs)
-----------------------------------------------------------------------------

The status of thresholds, hosts, and components can be displayed. The status of one or more threshold rules, hosts, or components can be added to one graph for monitoring.

-  **Threshold-crossing status graph**: monitors the status of threshold rules in real time.


   .. figure:: /_static/images/en-us_image_0000001411006006.png
      :alt: **Figure 3** Threshold status graph

      **Figure 3** Threshold status graph

   .. note::

      Before adding a threshold status graph, ensure that you have :ref:`created a threshold rule <aom_02_0060>`. Otherwise, such a graph cannot be added.

-  **Host status graph**: monitors the host status in real time.


   .. figure:: /_static/images/en-us_image_0000001461046213.png
      :alt: **Figure 4** Host status graph

      **Figure 4** Host status graph

-  **Component status graph**: monitors the component status in real time.


   .. figure:: /_static/images/en-us_image_0000001411326706.png
      :alt: **Figure 5** Component status graph

      **Figure 5** Component status graph

Top N Resource Graphs
---------------------

For top N resource graphs, the statistical unit is a cluster and statistical objects are resources such as hosts, components, or instances in the cluster. A top N resource graph shows the top N resources in a cluster in a visualized manner. Both the top 5 and top 15 resources can be displayed. By default, the top 5 resources are displayed. After the graph is zoomed in, the top 15 resources are displayed.

To quickly view the top N resources, add a top N graph to the dashboard. You only need to select resources and metrics, for example, host CPU usage. AOM then automatically singles out top N hosts for display. If the number of resources is less than N, actual resources are displayed. The following figure shows the top 5 hosts with the highest CPU usage.


.. figure:: /_static/images/en-us_image_0000001461287489.png
   :alt: **Figure 6** Top N resource graph

   **Figure 6** Top N resource graph

.. note::

   -  By default, the top 5 resources are displayed. To view the top 15 resources, click **Top 15 xxx**, double-click the graph, or click **View Larger** in the **Operation** column.
   -  To monitor the top 5 resources among all clusters, view them on the **O&M** page. Alternatively, add the corresponding graph on the **O&M** page to the dashboard.
   -  You can customize the title of the top N resource graph. By default, the title is **resource type(cluster name)**.

Precautions
-----------

-  A maximum of 50 dashboards can be created in a region.
-  A maximum of 20 graphs can be added to a dashboard.
-  A maximum of 10 resources can be added to a line graph, and resources can be selected across clusters.
-  Only one resource can be added to a digit graph.
-  A maximum of 10 threshold rules can be added to a threshold-crossing status graph.
-  A maximum of 10 hosts can be added to a host status graph.
-  A maximum of 10 components can be added to a component status graph.

Creating a Dashboard
--------------------

#. In the navigation pane, choose **Overview** > **Dashboard**.

#. On the **Dashboard** page, click **Create Dashboard**. In the displayed **Create Dashboard** dialog box, enter a dashboard name and click **OK**.

#. Add a metric graph to the dashboard. The dashboard supports the following graphs: line graphs, digit graphs, threshold-crossing status graphs, host status graphs, and component status graphs. Select a graph that meets your requirements.

   The following shows how to add a line graph to a dashboard:

   a. On the **Dashboard** page, click **Add Metric Graph**. In the displayed **Select Which to Add** dialog box, click **Create** below **Metric Data**.

   b. Select the type of the graph: In the displayed **Add Metric Graph** dialog box, select **Line graph** and then click **Next**.

   c. Select the metrics and set **Statistical Mode** and **Statistical Cycle**, and click **OK**.


      .. figure:: /_static/images/en-us_image_0000001411328114.png
         :alt: **Figure 7** Adding a metric graph

         **Figure 7** Adding a metric graph

#. Click **Save** in the upper right corner of the **Dashboard** page.

   .. note::

      Enable **Auto Refresh** (|image1|) in the upper right corner of the **Dashboard** page so that all graphs in the dashboard can be refreshed automatically.

      -  On (default)

         Data in the dashboard will be automatically refreshed each minute.

      -  Off

         Data in the dashboard will not be automatically refreshed.

More Operations
---------------

After creating a dashboard, perform the operations listed in :ref:`Table 1 <aom_02_0003__en-us_topic_0263893596_table16941192520152>` if needed.

.. _aom_02_0003__en-us_topic_0263893596_table16941192520152:

.. table:: **Table 1** Related operations

   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Object                | Operation                           | Description                                                                                                                                                                                                                                                                                                                                                                                                        |
   +=======================+=====================================+====================================================================================================================================================================================================================================================================================================================================================================================================================+
   | Dashboard             | Save as                             | Click **More** in the upper right corner, and choose **Save As**, **Rename**, or **Delete** from the drop-down list.                                                                                                                                                                                                                                                                                               |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                       | Rename                              |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                       | Delete                              |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                       | Export a monitoring report          | Click **Export Monitoring Report** to export a line graph in the dashboard as a CSV file to a local PC.                                                                                                                                                                                                                                                                                                            |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                       | Set the full-screen online duration | #. Select the target dashboard and click |image2| in the upper right corner of the **Dashboard** page.                                                                                                                                                                                                                                                                                                             |
   |                       |                                     | #. In the dialogue box that is displayed, set the full-screen online duration.                                                                                                                                                                                                                                                                                                                                     |
   |                       |                                     |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   |                       |                                     |    .. note::                                                                                                                                                                                                                                                                                                                                                                                                       |
   |                       |                                     |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   |                       |                                     |       -  **Custom**: The default online duration is 1 hour. You can enter 1-24 (unit: hour) in the text box.                                                                                                                                                                                                                                                                                                       |
   |                       |                                     |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   |                       |                                     |          For example, if you enter **2** in the text box, the login page is automatically displayed 2 hours later.                                                                                                                                                                                                                                                                                                 |
   |                       |                                     |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   |                       |                                     |       -  **Always online**: The full-screen online duration is not restricted. That is, you can always implement full-screen monitoring and the login page will never be displayed.                                                                                                                                                                                                                                |
   |                       |                                     |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   |                       |                                     |       -  **Rotation Period**: Set **Rotation Period** and **Dashboard** if rotation display is enabled. Range: 10s (default) to 120s.                                                                                                                                                                                                                                                                              |
   |                       |                                     |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   |                       |                                     | #. Click **OK** to enter the full-screen mode.                                                                                                                                                                                                                                                                                                                                                                     |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                       | Set an interpolation mode           | Click **Interpolation Mode** to set a mode for aggregating metric data. By default, AOM uses **null** to represent breakpoints in a metric graph. However, a metric graph with breakpoints is not suitable for reporting or presentation. To solve the problem, set **Interpolation Mode** to **0** or **null** to interpolate values. In this way, you can replace the missing metric data and avoid breakpoints. |
   |                       |                                     |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   |                       |                                     | You can set **Interpolation Mode** to **null**, or **0**.                                                                                                                                                                                                                                                                                                                                                          |
   |                       |                                     |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   |                       |                                     | -  **null**: Breakpoints are represented by **null** by default.                                                                                                                                                                                                                                                                                                                                                   |
   |                       |                                     | -  **0**: Breakpoints are indicated by **0**.                                                                                                                                                                                                                                                                                                                                                                      |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Graph                 | Add                                 | Click **Add Metric Graph** to add a line graph, digit graph, threshold-crossing status graph, host status graph, or component status graph to the dashboard.                                                                                                                                                                                                                                                       |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                       | Edit                                | Choose **Edit**, **Copy**, **Delete**, and **View Larger** (only a line graph can be enlarged) from the **Operation** column. The **Time Select** option is available only in a line graph. This option allows you to set a temporary time range and statistical cycle so that you can view the resource data within a specified time range.                                                                       |
   |                       |                                     |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   |                       |                                     | .. note::                                                                                                                                                                                                                                                                                                                                                                                                          |
   |                       |                                     |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   |                       |                                     |    In the dashboard, when resources such as hosts and components are deleted, graphs created for these resources are not automatically deleted. To improve system performance, manually delete unnecessary graphs.                                                                                                                                                                                                 |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                       | Copy                                |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                       | Delete                              |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                       | Zoom in                             |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                       | Time select                         |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                       | Refresh                             |                                                                                                                                                                                                                                                                                                                                                                                                                    |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                       | Resize                              | Move the cursor to the lower right corner of a graph. When the cursor changes to |image3|, hold down your left mouse button to resize the graph.                                                                                                                                                                                                                                                                   |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   |                       | Reposition                          | Put the cursor at the blank area in the upper or lower part of a graph, and drag and drop it to the desired position.                                                                                                                                                                                                                                                                                              |
   +-----------------------+-------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001411422764.png
.. |image2| image:: /_static/images/en-us_image_0000001599019641.png
.. |image3| image:: /_static/images/en-us_image_0263893612.png
