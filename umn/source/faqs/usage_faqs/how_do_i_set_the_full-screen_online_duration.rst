:original_name: aom_03_0012.html

.. _aom_03_0012:

How Do I Set the Full-Screen Online Duration?
=============================================

AOM provides an automatic logout mechanism to secure customer information. Specifically, after you access a page on the console but do not perform any operations within 1 hour, the console automatically logs you out.

If you set a full-screen view in the AOM console and later the system logs you out, the full-screen view will also exit. In this case, real-time monitoring cannot be performed. AOM allows you to customize full-screen online duration, meeting various requirements.

Precautions
-----------

-  For security purposes, exit the full-screen view when it is not required.

-  The full-screen online duration is irrelevant to operations. If the preset duration times out, the login page is automatically displayed.

-  The full-screen online duration is subject to the last setting.

   For example, if full-screen monitoring is implemented on multiple screens, the online duration is subject to the last setting.

   For another example, if the online duration is set on both the **O&M** and **Dashboard** pages, the last setting prevails.

-  The full-screen online duration takes precedence over the automatic logout mechanism of the cloud.

   For example, if you log in to the console, set the full-screen online duration to 2 hours on AOM pages, and then open other pages, your setting on the AOM pages also takes effect on other pages. That is, the login page will be automatically displayed 2 hours later.

-  If you leave all full-screen views, the default automatic logout mechanism is used.

   For example, if you log in to the console, set the full-screen online duration to 2 hours on AOM pages, open other pages, and then leave all full-screen views of AOM, the default logout mechanism will be used. That is, if you do not perform any operations within 1 hour, the login page will be automatically displayed.

Setting the Full-Screen Online Duration on the Dashboard Page
-------------------------------------------------------------

#. Log in to the AOM console. In the navigation pane, choose **Overview** > **Dashboard**.
#. Click |image1| in the upper right corner of the **Dashboard** page. In the dialog box that is displayed, set the full-screen online duration.

   -  **Custom**: The default online duration is 1 hour. You can enter 1-24 (unit: hour) in the text box.

      For example, if you enter **2** in the text box, the login page is automatically displayed 2 hours later.

   -  **Always online**: The full-screen online duration is not restricted. That is, you can always implement full-screen monitoring and the login page will never be displayed.

#. Click **OK** to enter the full-screen view.

.. |image1| image:: /_static/images/en-us_image_0000001598820253.png
