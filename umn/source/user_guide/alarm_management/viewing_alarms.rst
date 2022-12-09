:original_name: aom_02_0004.html

.. _aom_02_0004:

Viewing Alarms
==============

Alarms are the information reported when AOM or an external service such as Cloud Container Engine (CCE) is abnormal or may cause exceptions. Take measures to resolve faults. Otherwise, service exceptions may occur.


Viewing Alarms
--------------

#. Log in to the management console.

#. Under **Application**, click **Application Operations Management**.

#. In the navigation pane, choose **Alarm Center** > **Alarms**.

   .. note::

      -  Alarms are displayed by time. The alarm generated at the latest time is displayed at the topmost of the alarm list.
      -  You can also click |image1| on the right of the page to view the latest three alarms.

#. .. _aom_02_0004__li13952173133419:

   Set the time range or filter criteria.

   a. Set the time range.

      View the alarms generated within the time range. There are two methods to set a time range:

      Method 1: Use the predefined time label, such as **Last 1 hour**, **Last 6 hours**, or **Last 1 day**. You can select a time range as required.

      Method 2: Specify the start time and end time to customize a time range. You can specify 30 days at most.

   b. Set filter criteria.

      Enter an alarm status, name, or source, and click **Search**.

      .. note::

         -  You can click **Reset** to reset filter criteria.
         -  You can enter multiple alarm sources and separate them by using commas (,) to filter alarms.
         -  Alarm names and sources are case-sensitive.

#. View the search result.

   -  In the bar graph, view the statistics of alarms that meet the filter criterion within the time range specified in :ref:`4 <aom_02_0004__li13952173133419>`.


      .. figure:: /_static/images/en-us_image_0297078493.png
         :alt: **Figure 1** Alarm statistics

         **Figure 1** Alarm statistics

   -  In the alarm list, view the information about alarms that meet the filter criterion within the time range specified in :ref:`4 <aom_02_0004__li13952173133419>`.

      Click **View Details** in the **Operation** column to view alarm details.


      .. figure:: /_static/images/en-us_image_0297078494.png
         :alt: **Figure 2** Alarm list

         **Figure 2** Alarm list

#. Clear alarms.

   In the **Operation** column of the target alarm, click **Clear**.

   In addition, AOM supports automatic clearance of alarms triggered by threshold rules. For example, you create a threshold rule. That is, if the CPU usage exceeds 85%, a threshold alarm will be generated. If the CPU usage is lower than 85%, the alarm will be cleared. In this case, you do not need to manually clear the alarm. When the CPU usage returns to normal, the threshold alarm will be automatically cleared. In addition, when the threshold rule is deleted, the threshold alarm will also be automatically cleared.

.. |image1| image:: /_static/images/en-us_image_0297078492.png
