:original_name: aom_02_0007.html

.. _aom_02_0007:

Component Monitoring
====================

Components refer to the services that you deploy, including containers and common processes. For example, a workload on the Cloud Container Engine (CCE) is a component, and the Tomcat running on the VM is also a component.

The component list displays the type, CPU usage, memory usage, and alarm status of each component, helping you learn their running status. You can click a component name to learn more information about the component. AOM supports drill-down from a component to an instance, and then to a container. By viewing the status of each layer, you can implement dimensional monitoring for components.

#. In the navigation pane, choose **Monitoring** > **Component Monitoring**.

   -  The component list displays information such as **Component Name**, **Status**, **Application**, **Deployment Mode**, and **Application Discovery Rules**.
   -  Click |image1| in the upper right corner and select **Hide system component**.
   -  Set filter criteria above the component list to filter components.

#. Perform the following operations as required:

   -  **Adding an alias**

      If a component name is complex and difficult to identify, you can add an alias for the component.

      Click **Add alias** in the **Operation** column to add an alias.

   -  **Adding a tag**

      Tags are identifiers of components. You can distinguish system components from non-system ones based on tags. By default, AOM adds the **System Service** tag to system components (including icagent, css-defender, nvidia-driver-installer, nvidia-gpu-device-plugin, kube-dns, org.tanukisoftware.wrapper.WrapperSimpleApp, evs-driver, obs-driver, sfs-driver, icwatchdog, and sh). You can click |image2| in the upper right corner to select or deselect **Hide system component**. AOM also allows you to customize tags for easier component management.

      In the component list, click **Add tags** in the **Operation** column of the component, enter a tag, and click |image3| and **OK** to add a tag. You can also mark the component as a system component.

      .. note::

         -  The **Tags** column of the component list is hidden by default. You can click |image4| in the upper right corner and select or deselect **Tags** to show or hide tags.
         -  **Application Discovery Rules**:

            -  **Sys_Rule**: AOM automatically discovers components based on the built-in application discovery rule named **Sys_Rule**. For details, see :ref:`Built-in Discovery Rules <aom_02_0023__en-us_topic_0263893455_section938317591962>`.

            -  **Default_Rule**: AOM automatically discovers components based on the built-in application discovery rule named **Default_Rule**. For details, see :ref:`Built-in Discovery Rules <aom_02_0023__en-us_topic_0263893455_section938317591962>`.
            -  Custom rules: Their names are customized and not fixed. Applications are discovered based on custom rules.

#. Set filter criteria to search for the desired component.

   .. note::

      Components cannot be searched by alias.

#. Click the component name. The **Component Details** page is displayed.

   .. note::

      In the upper right corner of the **Component Details** page, you can set a time range to query the instance, host, or alarm information of the component. If no data exists within the time range, AOM automatically switches to the **Component Monitoring** page.

   -  On the **Instance List** tab page, view the instance details.

      .. note::

         Click an instance name to monitor the resource usage and health status.

   -  On the **Host List** tab page, view the host details.
   -  On the **Alarm Analysis** tab page, view the alarm details.

   -  Click the **View Monitor Graphs** tab to monitor the metrics of the component.

      -  AOM provides a default view template (**Service Template**) which can be modified. You can also click **View Template** to customize one.
      -  You can click |image5| to add a line graph or |image6| to add a digit graph to the view template. You can also delete, move, and copy metric graphs in the view template. For details, see :ref:`Dashboard <aom_02_0003>`.

   -  **Adding to a dashboard**

      On the component details page, click the **View Monitor Graphs** tab, and choose **More** > **Add to Dashboard** in the upper right corner to add the view template to the dashboard for monitoring.

.. |image1| image:: /_static/images/en-us_image_0000001163172426.png
.. |image2| image:: /_static/images/en-us_image_0000001163172776.png
.. |image3| image:: /_static/images/en-us_image_0000001240568411.png
.. |image4| image:: /_static/images/en-us_image_0000001461510225.png
.. |image5| image:: /_static/images/en-us_image_0269669234.png
.. |image6| image:: /_static/images/en-us_image_0269669235.png
