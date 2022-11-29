:original_name: aom_02_2013.html

.. _aom_02_2013:

Upgrading the ICAgent
=====================

To ensure better collection experience, AOM will continuously upgrade ICAgent versions. When the system displays a message indicating that a new ICAgent version is available, perform the following operations:

#. Log in to the management console.

#. Under **Application**, click **Application Operations Management**.

#. In the navigation pane, choose **Agent Management**.

#. Upgrade the ICAgent. ICAgents are upgraded in batches by cluster. That is, ICAgents on all hosts in a cluster are upgraded at a time. For hosts where ICAgents have already been uninstalled, ICAgents are installed on them again.

   a. Select **Cluster: xxx** (**xxx** indicates the name of the cluster created on the CCE console) from the drop-down list on the right of the page.
   b. Click **Upgrade ICAgent**. In the displayed dialog box, click **Yes**.

   The ICAgent begins to be upgraded. Please wait. When the ICAgent status changes from **Upgrading** to **Running**, the ICAgent is successfully upgraded.
