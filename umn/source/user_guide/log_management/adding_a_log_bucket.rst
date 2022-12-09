:original_name: aom_02_0079.html

.. _aom_02_0079:

Adding a Log Bucket
===================

A log bucket is a logical group of log files. Ensure that a log bucket has been created before you :ref:`view bucket logs <aom_02_0083>`.

Precautions
-----------

-  A maximum of 500 log files can be added to each log bucket.
-  A log bucket only stores the log files of the same cluster.


Adding a Log Bucket
-------------------

#. Log in to the management console.

#. Under **Application**, click **Application Operations Management**.

#. In the navigation pane, choose **Log** **Management** > **Log Buckets**.

#. Click the **Bucket List** tab and then click **Add Log Bucket**. On the displayed page, enter a log bucket name and description, add a log file, and click **OK**, as shown in the following figure.


   .. figure:: /_static/images/en-us_image_0297610957.png
      :alt: **Figure 1** Adding a log bucket

      **Figure 1** Adding a log bucket

More Operations
---------------

After adding a log bucket, you can also perform the operations described in :ref:`Table 1 <aom_02_0079__en-us_topic_0175844843_table14918185010104>`.

.. _aom_02_0079__en-us_topic_0175844843_table14918185010104:

.. table:: **Table 1** Related operations

   +-----------------------------------+--------------------------------------------------------+
   | Operation                         | Description                                            |
   +===================================+========================================================+
   | View bucket logs                  | Click a log bucket to view logs.                       |
   +-----------------------------------+--------------------------------------------------------+
   | Modify a log bucket               | Click **Modify** in the **Operation** column.          |
   +-----------------------------------+--------------------------------------------------------+
   | Delete a log bucket               | Click **Delete** in the **Operation** column.          |
   |                                   |                                                        |
   |                                   | Deleting a log bucket will not delete log files in it. |
   +-----------------------------------+--------------------------------------------------------+
