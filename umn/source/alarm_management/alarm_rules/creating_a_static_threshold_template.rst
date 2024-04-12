:original_name: aom_02_0063.html

.. _aom_02_0063:

Creating a Static Threshold Template
====================================

Ensure that a static threshold template is available if you want to create threshold rules based on a template.

Precautions
-----------

You can create a maximum of 50 static threshold templates. If the maximum number has been reached, delete unnecessary templates and create new ones.

Procedure
---------

#. Log in to the AOM console. In the navigation pane, choose **Alarm Center** > **Alarm Rules**.

#. Click the **Static Threshold Templates** tab, and then click **Create**.

#. Customize a static threshold template.

   Enter a template name, select a resource type, and set parameters such as **Name**, **Statistic**, and **Threshold Criterion**.

   .. note::

      -  **Statistic**: method used to measure metric values.
      -  **Threshold Criterion**: trigger condition of a threshold alarm. It consists of two parts: determination condition (>=, <=, >, or <) and threshold value. For example, after **Threshold Criterion** is set to **> 85**, if the actual metric value exceeds 85, a threshold alarm is generated.
      -  **Consecutive Periods**: If a metric value meets the threshold condition for a specified number of consecutive periods, a threshold alarm is generated.
      -  **Statistical Period**: interval at which metric data is collected.
      -  **Alarm Severity**: includes **Critical**, **Major**, **Minor**, and **Warning**.


   .. figure:: /_static/images/en-us_image_0000001410881540.png
      :alt: **Figure 1** Customizing a static threshold template

      **Figure 1** Customizing a static threshold template

#. Click **Create**.

More Operations
---------------

After creating a static threshold template, perform the operations listed in :ref:`Table 1 <aom_02_0063__en-us_topic_0263893608_en-us_topic_0169698339_table15831736105910>` if needed.

.. _aom_02_0063__en-us_topic_0263893608_en-us_topic_0169698339_table15831736105910:

.. table:: **Table 1** Related operations

   +-----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                                                                   | Description                                                                                                                                                                                            |
   +=============================================================================+========================================================================================================================================================================================================+
   | Using a static threshold template to create a multi-resource threshold rule | Click **Create Rule** in the **Operation** column. For details, see :ref:`Using Templates to Create Threshold Rules <aom_02_0060__en-us_topic_0263893548_en-us_topic_0169698491_section215851225919>`. |
   +-----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Editing a static threshold template                                         | Click **Edit** in the **Operation** column.                                                                                                                                                            |
   +-----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Deleting a static threshold template                                        | -  To delete a static threshold template, click **Delete** in the **Operation** column.                                                                                                                |
   |                                                                             | -  To delete one or more static threshold templates, select them and click **Delete** above the template list.                                                                                         |
   +-----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Searching for a static threshold template                                   | Enter a template name in the search box in the upper right corner and click |image1|.                                                                                                                  |
   +-----------------------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0263893524.png
