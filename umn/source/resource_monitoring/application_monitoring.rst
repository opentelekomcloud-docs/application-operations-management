:original_name: aom_02_0049.html

.. _aom_02_0049:

Application Monitoring
======================

An application is a group of identical or similar components divided based on service requirements. Applications are categorized into system applications and custom applications. The former are discovered based on built-in rules while the latter are discovered based on custom rules.

After application discovery rules are set, AOM automatically discovers applications that meet the rules and monitors related metrics. For details, see :ref:`Configuring Application Discovery Rules <aom_02_0023>`.

Procedure
---------

#. In the navigation pane, choose **Monitoring** > **Application Monitoring**.

   .. note::

      Set filter criteria above the application list to filter applications.

#. Click an application. On the details page that is displayed, manage and monitor components of the application in batches.

   You can also view the component list, host list, and alarm analysis result of the current application.

   .. note::

      In the upper right corner of the **Application Details** page, you can set a time range to query the component, host, or alarm information of the application. If no data exists within the time range, AOM automatically switches to the **Application Monitoring** page.

#. During routine O&M, you can monitor various metrics of applications on the **View Monitor Graphs** tab page.

   -  **Creating a view template**

      AOM provides a default view template (**Application Template**) which can be modified. You can also click **View Template** to customize one.

   -  **Adding a metric graph**

      -  You can click |image1| to add a line graph or |image2| to add a digit graph to the view template. You can also delete, move, and copy metric graphs in the view template. For details, see :ref:`Dashboard <aom_02_0003>`.

   -  **Adding to a dashboard**

      On the application details page, click the **View Monitor Graphs** tab, and choose **More** > **Add to Dashboard** in the upper right corner to add the view template to the dashboard for monitoring.

#. Perform the following operations if needed:

   -  **Adding an application**

      For identical or similar components that are discovered by default discovery rules or that are not installed with Application Performance Management (APM) probes, you can group them logically, that is, add them to the same application for monitoring.

      In the upper right corner of the **Application Monitoring** page, click **Create Application**. On the displayed page, add a custom application discovery rule. For details, see :ref:`Configuring Application Discovery Rules <aom_02_0023>`. You can monitor the application after adding it. AOM can display O&M information by component. For details, see :ref:`Component Monitoring <aom_02_0007>`.

.. |image1| image:: /_static/images/en-us_image_0269669240.png
.. |image2| image:: /_static/images/en-us_image_0269669241.png
