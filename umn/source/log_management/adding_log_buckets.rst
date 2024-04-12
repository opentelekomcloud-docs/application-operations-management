:original_name: aom_02_0079.html

.. _aom_02_0079:

Adding Log Buckets
==================

A log bucket is a logical group of log files. Before using functions such as :ref:`Viewing Bucket Logs <aom_02_0083>`, ensure that a log bucket has been created.

Precautions
-----------

-  You can add up to 500 log files to a log bucket.
-  A log bucket only stores the log files of the same cluster.

Procedure
---------

#. Log in to the AOM console. In the navigation pane, choose **Log** > **Log Buckets**.

#. Click **Bucket List** tab and then click **Add Log Bucket**. On the page that is displayed, enter a log bucket name and description, select one or more log files, and click **OK**, as shown in the following figure.


   .. figure:: /_static/images/en-us_image_0000001479016049.png
      :alt: **Figure 1** Adding a log bucket

      **Figure 1** Adding a log bucket

   .. note::

      -  The **Component** tab page displays log files of all components except system components.
      -  The **System** tab page displays all system log files.
      -  The **Host** tab page displays all host log files.

More Operations
---------------

After adding a log bucket, perform the operations listed in :ref:`Table 1 <aom_02_0079__en-us_topic_0263893511_en-us_topic_0169698335_table14918185010104>` if needed.

.. _aom_02_0079__en-us_topic_0263893511_en-us_topic_0169698335_table14918185010104:

.. table:: **Table 1** Related operations

   +-----------------------------------+--------------------------------------------------------+
   | Operation                         | Description                                            |
   +===================================+========================================================+
   | Viewing bucket logs               | Click a log bucket to view its logs.                   |
   +-----------------------------------+--------------------------------------------------------+
   | Modifying a log bucket            | Click **Modify** in the **Operation** column.          |
   +-----------------------------------+--------------------------------------------------------+
   | Deleting a log bucket             | Click **Delete** in the **Operation** column.          |
   |                                   |                                                        |
   |                                   | Deleting a log bucket will not delete log files in it. |
   +-----------------------------------+--------------------------------------------------------+
