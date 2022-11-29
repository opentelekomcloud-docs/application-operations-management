:original_name: en-us_topic_0296826282.html

.. _en-us_topic_0296826282:

Process of Using AOM
====================

:ref:`Process of Using AOM <en-us_topic_0296826282>` shows the process of using AOM.


.. figure:: /_static/images/en-us_image_0297183045.png
   :alt: **Figure 1** Process of using AOM

   **Figure 1** Process of using AOM

#. (Mandatory) Register an account.

#. (Mandatory) Create a cloud host.

#. (Mandatory) Install the ICAgent.

   ICAgent is the data collector of AOM. It runs on hosts to collect metrics, logs, and application performance data in real time. Ensure that you have :ref:`installed the ICAgent <aom_02_2012>` before using AOM.

#. The system automatically discovers services.

   After the ICAgent is installed, the services that meet the built-in service discovery rules on the host will be automatically discovered.

#. (Optional) Configure a log collection path.

   To view the logs of the monitored host, you must first :ref:`configure a log collection path <aom_02_0039>`. The ICAgent then will collect host logs from the configured path and display them on AOM.

#. (Optional) Perform O&M.

   You can use AOM functions such as dashboard, monitoring, alarm reporting, and log management to implement routine O&M.
