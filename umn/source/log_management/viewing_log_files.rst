:original_name: aom_02_0010.html

.. _aom_02_0010:

Viewing Log Files
=================

You can quickly view log files of component instances to locate faults.


Viewing Log Files
-----------------

#. In the navigation pane, choose **Log** > **Log Files**.

#. On the page that is displayed, click the **Component** or **Host** tab and click a component or host name. Information such as the log file name and latest written time is displayed in the log file list on the right.

#. Click **View** in the **Operation** column of the desired instance. :ref:`Table 1 <aom_02_0010__en-us_topic_0263893505_table108124216110>` describes how to view log file details. :ref:`Figure 1 <aom_02_0010__en-us_topic_0263893505_fig12644152135813>` shows log file details.

   .. _aom_02_0010__en-us_topic_0263893505_table108124216110:

   .. table:: **Table 1** Operations

      +-----------------------+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Operation             | Setup                  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
      +=======================+========================+======================================================================================================================================================================================================================================================================================================================================================================================================================================================================+
      | Setting a time range  | Date                   | Click |image1| to select a date.                                                                                                                                                                                                                                                                                                                                                                                                                                     |
      +-----------------------+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Time range             | Click the desired time on the time axis to set a time range. You can select only one unit (5 minutes) each time.                                                                                                                                                                                                                                                                                                                                                     |
      +-----------------------+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Viewing log files     | Clear                  | Click **Clear** to clear the logs displayed on the screen. Logs displayed on the screen will be cleared, but will not be deleted.                                                                                                                                                                                                                                                                                                                                    |
      +-----------------------+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Viewing real-time logs | The real-time monitoring function is disabled by default. You can click **Enable Real-Time Viewing** as required. After this function is enabled, the latest written logs can be viewed.                                                                                                                                                                                                                                                                             |
      |                       |                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
      |                       |                        | The **exception** in the log records the exceptions that occur during code running. When using logs to locate faults, pay attention to the **exception**. For real-time log viewing, AOM automatically highlights exception keywords in logs, facilitating fault locating. Such keywords are case-sensitive. For example, **exception** and **Exception** are highlighted, but keywords such as **EXCEPTION**, **exCeption**, and **EXception** are not highlighted. |
      +-----------------------+------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   .. _aom_02_0010__en-us_topic_0263893505_fig12644152135813:

   .. figure:: /_static/images/en-us_image_0000001461631457.png
      :alt: **Figure 1** Log file details

      **Figure 1** Log file details

Log File Description
--------------------

The time information contained in a log file, if any, is automatically displayed, as shown in the red box in :ref:`Figure 2 <aom_02_0010__en-us_topic_0263893505_fig1840281674012>`. This time information is irrelevant to the time range that you set.

.. _aom_02_0010__en-us_topic_0263893505_fig1840281674012:

.. figure:: /_static/images/en-us_image_0000001561946430.png
   :alt: **Figure 2** Viewing log files

   **Figure 2** Viewing log files

.. |image1| image:: /_static/images/en-us_image_0000001411431544.png
