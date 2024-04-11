:original_name: aom_02_0008.html

.. _aom_02_0008:

Host Monitoring
===============

Hosts include the Elastic Cloud Server (ECS) and Bare Metal Server (BMS). AOM monitors the hosts purchased during Cloud Container Engine (CCE) cluster creation and those directly purchased. Ensure that hosts meet operating system (OS) and version requirements, and the ICAgent is installed on them according to :ref:`Installing an ICAgent <aom_02_0012>`. Otherwise, these hosts cannot be monitored by AOM. In addition, the hosts support both IPv4 and IPv6 addresses.

AOM monitors common system devices such as disks and file systems, and resource usage and health status of hosts and service processes or instances running on them.

Precautions
-----------

-  A maximum of five tags can be added to a host, and each tag must be unique.
-  The same tag can be added to different hosts.
-  For hosts created on the CCE console, you cannot select clusters or create aliases for them.
-  The host status can be **Normal**, **Abnormal**, **Warning**, **Silent**, or **Deleted**. The running status of a host is displayed as **Abnormal** when the host is faulty due to network failures, and power off or shut down of the host, or a threshold alarm is reported on the host.

Procedure
---------

#. In the navigation pane, choose **Monitoring** > **Host Monitoring**.

   To view the host list more easily, you can:

   -  Click |image1| in the upper right corner and select **Hide master host**.
   -  Set filter criteria above the host list to filter hosts.

#. Perform the following operations as required:

   -  **Adding an alias**

      If a host name is too complex, you can add a simple alias.

      In the host list, click **Add alias** in the **Operation** column.

   -  **Adding a tag**

      A tag is the identifier of a host. You can manage and classify hosts by tag. After a tag is added, you can quickly identify, select, or search for a host.

      In the host list, choose **More** > **Add tags** in the **Operation** column, enter a tag, and click |image2| and **OK** to add a tag. The **Tags** column of the host list is hidden by default. You can click |image3| in the upper right corner and select or deselect **Tags** to show or hide tags.

   -  **Synchronizing host data**

      In the host list, locate the target host and choose **More** > **Sync Host Data** in the **Operation** column to synchronize host data.

#. Set filter criteria to search for the desired host.

   .. note::

      Hosts cannot be searched by alias.

#. Click the host name to enter the **Host Details** page. In the instance list, monitor the resource usage and health status of instances. In addition, click the **View Monitor Graphs** tab to monitor the metrics of the host.

   .. note::

      In the upper right corner of the **Host Details** page, you can set the time range to query the instance, GPU, NIC, and alarm information of the host. If no data exists within the time range, AOM automatically switches to the **Host Monitoring** page.

   -  **Creating a view template**

      AOM provides a default view template (**Host Template**) which can be modified. You can also click **View Template** to customize one.

   -  **Adding a metric graph**

      -  You can click |image4| to add a line graph or |image5| to add a digit graph to the view template. You can also delete, move, and copy metric graphs in the view template. For details, see :ref:`Dashboard <aom_02_0003>`.

   -  **Adding to a dashboard**

      On the host details page, click the **View Monitor Graphs** tab, and choose **More** > **Add to Dashboard** in the upper right corner to add the view template to the dashboard for monitoring.

#. Monitor common system devices such as the GPU and NIC of the host.

   -  Click the **Instance List** tab to view the basic information such as the instance status and type. Click an instance to view its metrics on the details page.
   -  Click the **GPUs** tab to view the basic information about the GPU of the host. Click a GPU to monitor its metrics on the **View Monitor Graphs** page.
   -  Click the **NIC** tab to view the basic information about the NIC of the host. Click a NIC to monitor its metrics on the **View Monitor Graphs** page.
   -  Click the **Disks** tab to view the basic information about the disk of the host. Click a disk to monitor its metrics on the **View Monitor Graphs** page.
   -  Click the **File System** tab to view the basic information about the file system of the host. Click a disk file partition to monitor its metrics on the **View Monitor Graphs** page.
   -  Click the **Alarm Analysis** tab to view the alarm details.
   -  Click the **Disk Partition** tab to view the disk partition type, size, and usage.

      .. note::

         Disk partitions are supported by CentOS 7.x and EulerOS 2.5.

.. |image1| image:: /_static/images/en-us_image_0000001163172900.png
.. |image2| image:: /_static/images/en-us_image_0000001195728488.png
.. |image3| image:: /_static/images/en-us_image_0000001461829877.png
.. |image4| image:: /_static/images/en-us_image_0269669237.png
.. |image5| image:: /_static/images/en-us_image_0269669238.png
