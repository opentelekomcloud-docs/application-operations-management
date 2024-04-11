:original_name: aom_02_0083.html

.. _aom_02_0083:

Viewing Bucket Logs
===================

AOM supports fine-grained log query. That is, you can view logs by bucket to obtain key service data and quickly locate problems.

Precautions
-----------

-  Before viewing bucket logs, ensure that you have created at least one log bucket. Otherwise, you cannot view bucket logs.
-  You can view bucket logs generated in the last seven days.


Viewing Bucket Logs
-------------------

#. Log in to the AOM console. In the navigation pane, choose **Log** > **Log Buckets**, and click the **Bucket Log** tab to view logs.

#. .. _aom_02_0083__en-us_topic_0263893620_en-us_topic_0169698259_li13990166371:

   Set filter criteria.

   -  **Select a log bucket**: Select a target log bucket from the drop-down list in the upper left corner.
   -  **Set a time range**: In the drop-down list in the upper right corner, select a time range, such as **Last 30 minutes**, **Last 1 hour**, or **Last 6 hours**. You can also select **Custom time range** to specify the start time and end time.
   -  **Enter a keyword**: Click the text box. All statistical rules and keywords of the bucket are displayed under the text box. Select a keyword. It is automatically displayed in the text box. Alternatively, enter a keyword directly in the text box.

#. View the search result.

   -  **Viewing statistical data in a bar chart**

      The bar chart shows the number of logs that met the filter criteria set in step :ref:`2 <aom_02_0083__en-us_topic_0263893620_en-us_topic_0169698259_li13990166371>` in different time periods. The horizontal axis represents the time and is divided into 30 rectangular blocks of the same size. The time duration indicated by each rectangle block is **selected time range/30**. For example, if the time range is 30 minutes, the time duration of each rectangle block is 1 minute. If the time range is set to 60 minutes, the time duration of each rectangle block is 2 minutes. The vertical axis represents the number of queried logs.


      .. figure:: /_static/images/en-us_image_0000001479138361.png
         :alt: **Figure 1** Viewing statistical data in a bar chart

         **Figure 1** Viewing statistical data in a bar chart

      When you hover over a rectangle block, the prompt displays the time range (start time and end time) and the number of logs that meet the filter criteria within the time range. When you click a rectangle block, the log list displays corresponding log details. To deselect the block, click |image1|.

   -  **Viewing log details in a log list**

      The log list displays the details of the logs that meet the filter criteria set in step :ref:`2 <aom_02_0083__en-us_topic_0263893620_en-us_topic_0169698259_li13990166371>`.


      .. figure:: /_static/images/en-us_image_0000001479298177.png
         :alt: **Figure 2** Viewing log details in a log list

         **Figure 2** Viewing log details in a log list

      Perform the following operations if needed:

      -  Click |image2| to view details of a selected log, such as the host IP address and source.

      -  Sort search results: Logs are sorted based on collection time in descending order by default. You can click |image3| in the **Collection Time** column to change the order. When you click |image4| to sort logs by time in ascending order, the latest log is displayed at the end. When you click |image5| to sort logs by time in descending order, the latest log is displayed at the top.

      -  View the context of a specified log: AOM allows you to view the previous or next logs of a specified log by clicking **View Context** in the **Operation** column, facilitating fault locating. Therefore, you do not need to search for logs in raw files.


         .. figure:: /_static/images/en-us_image_0000001429259356.png
            :alt: **Figure 3** Viewing the context of a specified log

            **Figure 3** Viewing the context of a specified log

.. |image1| image:: /_static/images/en-us_image_0263893614.png
.. |image2| image:: /_static/images/en-us_image_0263893584.png
.. |image3| image:: /_static/images/en-us_image_0000001562424626.png
.. |image4| image:: /_static/images/en-us_image_0000001562264710.png
.. |image5| image:: /_static/images/en-us_image_0000001612744525.png
