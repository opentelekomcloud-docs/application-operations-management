:original_name: aom_02_2012.html

.. _aom_02_2012:

Installing the ICAgent
======================

ICAgent is the collector of AOM. It runs on each host to collect metrics and logs in real time. Before using AOM, install the ICAgent. Otherwise, AOM cannot be used.

VM Mode
-------

**Prerequisite**

-  Before installing the ICAgent, ensure that the time and time zone of the local browser are consistent with those of the server. Otherwise, metric data of services and servers displayed on the console may be inaccurate.
-  You have obtained an AK/SK. For details, see :ref:`Obtaining an AK/SK <aom_02_1100>`.

**Procedure**

#. Log in to the management console.

#. Under **Application**, click **Application Operations Management**.

#. In the navigation pane, choose **Agent Management**.

#. Select **Other: user-defined nodes**, and click **Install ICAgent**.

#. .. _aom_02_2012__en-us_topic_0141087170_l836b10183bf24ed1b45ac06d86ee8f81:

   Generate and copy the ICAgent installation command.

#. Use a remote login tool, such as PuTTY, to log in as the **root** user to the server where the ICAgent is to be installed, run the command copied in :ref:`5 <aom_02_2012__en-us_topic_0141087170_l836b10183bf24ed1b45ac06d86ee8f81>`, and enter the obtained AK/SK as prompted to install the ICAgent.

   .. note::

      -  If the message **ICAgent install success.** is displayed, the ICAgent is successfully installed in the **/opt/oss/servicemgr/** directory. After the ICAgent is successfully installed, choose **Agent Management** in the navigation pane on the left, and select **Other: user-defined nodes** to view the ICAgent status of the server.
      -  If the ICAgent fails to be installed, uninstall it according to :ref:`Uninstalling the ICAgent <aom_02_2014>` and then install it again. If the problem persists, contact technical support.

Container Mode
--------------

After a cluster is created on the Cloud Container Engine (CCE) console, the system automatically installs the ICAgent on all hosts in the cluster. After the ICAgent is uninstalled, install it again according to the following procedure:

#. Log in to the management console.

#. Under **Application**, click **Application Operations Management**.

#. In the navigation pane, choose **Agent Management**.

#. Install the ICAgent. The ICAgent is installed in batches by cluster. That is, the ICAgent is installed on all hosts in a cluster at a time.

   a. Select **Cluster: xxx** (**xxx** indicates the name of the cluster created on the CCE console) from the drop-down list on the right of the page.
   b. Click **Install ICAgent**. In the displayed dialog box, click **Yes**.

   The ICAgent begins to be installed. Please wait. When the ICAgent status changes from **Installing** to **Running**, the ICAgent is successfully installed.
