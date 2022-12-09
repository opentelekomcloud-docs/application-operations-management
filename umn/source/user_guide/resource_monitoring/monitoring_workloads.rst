:original_name: aom_02_2007.html

.. _aom_02_2007:

Monitoring Workloads
====================

AOM enables you to monitor workloads deployed on Cloud Container Engine (CCE).

Precautions
-----------

The workload status can be **Normal**, **Abnormal**, **Warning**, **Silent**, or **Deleted**. If a workload generates a threshold alarm or is abnormal due to a network exception, host power-off, or shutdown, the workload status becomes **Abnormal**. For more information, see :ref:`What Can I Do If Resources Are Not Running Properly? <aom_02_1012>`.

Procedure
---------

#. Log in to the management console.

#. Under **Application**, click **Application Operations Management**.

#. In the navigation pane, choose **Workload Monitoring**.

   The workload list displays the status, CPU usage, and memory usage of each workload, helping you learn the running status of each workload.

#. Set filter criteria to search for a desired workload.

#. Click the workload to enter its details page. AOM supports drill-down from a workload to an instance, and then to a container. By viewing the status of each layer, you can monitor the workload in a multi-dimensional manner.

   -  On the **Resource List** page, view instance status, CPU usage, and physical memory usage, as shown in the following figure.

      |image1|

      .. note::

         Click an instance to monitor information such as resource usage and health status.

   -  Click the **View Monitor Graphs** tab to view the metrics of the workload, such as the CPU usage and memory usage, as shown in the following figure.

      |image2|

      -  **Creating a view template**

         AOM provides a default view template (**Service Template**) that can be modified. You can also click the plus sign (+) in |image3| to customize view templates.

      -  **Adding a metric graph**

         You can click |image4| to add a line graph or |image5| to add a digit graph to the view template. You can also delete, move, and copy metric graphs in the view template according to :ref:`Dashboard <aom_02_0003>`.

      -  **Adding a view template to a dashboard**

         On the workload details page, choose **More** > **Add To Dashboard** in the upper right corner to add the view template to a dashboard for monitoring.

.. |image1| image:: /_static/images/en-us_image_0000001366881660.png
.. |image2| image:: /_static/images/en-us_image_0000001417801529.png
.. |image3| image:: /_static/images/en-us_image_0000001417721645.png
.. |image4| image:: /_static/images/en-us_image_0201820799.png
.. |image5| image:: /_static/images/en-us_image_0201820725.png
