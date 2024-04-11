:original_name: aom_02_0009.html

.. _aom_02_0009:

Searching for Logs
==================

AOM enables you to quickly query logs, and locate faults based on log sources and contexts.

#. In the navigation pane, choose **Log** > **Log Search**.

#. On the **Log Search** page, click the **Component**, **System**, or **Host** tab and set filter criteria as prompted.

   .. note::

      a. You can search for logs by component, system, or host.

         -  For component logs, you can set filter criteria such as **Cluster**, **Namespace**, and **Component**. You can also click **Advanced Search** and set filter criteria such as **Instance**, **Host**, and **File Name**, and choose whether to enable **Hide System Component**.
         -  For system logs, you can set filter criteria such as **Cluster** and **Host**.
         -  For host logs, you can set filter criteria such as **Cluster** and **Host**.

      b. Enter a keyword in the search box. Rules are as follows:

         -  Enter a keyword between two adjacent delimiters for exact search. By :ref:`configuring delimiters <aom_02_0082>`, you can divide the log content into multiple words and then enter these words to search for logs. If you are not sure whether there are adjacent delimiters, enter a keyword for fuzzy search.
         -  Enter a keyword with a question mark (?) or an asterisk (*) for fuzzy match. Do not start a keyword with a question mark or an asterisk. For example, you can enter **ER?OR** or **ER*R**.
         -  Enter search criteria containing search operator AND (&&) or OR (||). For example, enter **query logs&&erro\*** or **query logs||error**.

#. .. _aom_02_0009__en-us_topic_0263893558_li34212241:

   View the search result of logs.

   The search results are sorted based on the log collection time, and keywords in them are highlighted. You can click |image1| in the **Time** column to switch the sorting order.

   By default, logs are displayed in the descending order. |image2| indicates the ascending order by time (that is, the latest log is displayed at the end). |image3| indicates the descending order by time (that is, the latest log is displayed at the top).

   a. Click |image4| on the left of the log list to view details.
   b. AOM allows you to view the previous or next logs of a specified log by clicking **View Context** in the **Operation** column, facilitating fault locating. Therefore, you do not need to search for logs in raw files.

      -  In the **Display Rows** drop-down list, set the number of rows that display raw context data of the log.

         .. note::

            For example, select **200** from the **Display Rows** drop-down list.

            -  If there are 100 logs or more printed prior to a log and 99 or more logs printed following the log, the preceding 100 logs and following 99 logs are displayed as the context.
            -  If there are fewer than 100 logs (for example, 90) printed prior to a log and fewer than 99 logs (for example, 80) printed following the log, the preceding 90 logs and following 80 logs are displayed as the context.

      -  Click **Export Current Page** to export displayed raw context data of the log to a local PC.

   .. note::

      To ensure that tenant hosts and services run properly, some components (for example, kube-dns) provided by the system will run on the tenant hosts. The logs of these components are also queried during tenant log query.

#. (Optional) Click |image5| in the upper right corner on the **Log Search** page, select the file format, and export the search result to the local PC.

   Logs are sorted according to the order set in :ref:`3 <aom_02_0009__en-us_topic_0263893558_li34212241>` and a maximum of 5000 logs can be exported. For example, when 6000 logs in the search result are sorted in descending order, only the first 5000 logs can be exported.

   Logs can be exported in CSV or TXT format. You can select a format as required. If you select the CSV format, detailed information (such as log content, host IP address, and source) can be exported, as shown in :ref:`Figure 1 <aom_02_0009__en-us_topic_0263893558_fig1785710409496>`. If you select the TXT format, only log content can be exported, as shown in :ref:`Figure 2 <aom_02_0009__en-us_topic_0263893558_fig74285517415>`. Each row represents a log. If a log contains a large amount of content, you are advised to view the log using a text editor.

   .. _aom_02_0009__en-us_topic_0263893558_fig1785710409496:

   .. figure:: /_static/images/en-us_image_0000001461829881.png
      :alt: **Figure 1** Exporting logs in CSV format

      **Figure 1** Exporting logs in CSV format

   .. _aom_02_0009__en-us_topic_0263893558_fig74285517415:

   .. figure:: /_static/images/en-us_image_0263893562.png
      :alt: **Figure 2** Exporting logs in TXT format

      **Figure 2** Exporting logs in TXT format

.. |image1| image:: /_static/images/en-us_image_0000001163330328.png
.. |image2| image:: /_static/images/en-us_image_0000001411430140.png
.. |image3| image:: /_static/images/en-us_image_0000001411270156.png
.. |image4| image:: /_static/images/en-us_image_0263893649.png
.. |image5| image:: /_static/images/en-us_image_0000001163171568.png
