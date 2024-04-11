:original_name: aom_02_002301.html

.. _aom_02_002301:

Installing an ICAgent
=====================

ICAgent is used to collect metrics, logs, and application performance data. For servers that are directly purchased on the Elastic Cloud Server (ECS) or Bare Metal Server (BMS) console, manually install an ICAgent. For hosts purchased through Cloud Container Engine (CCE), an ICAgent is automatically installed.

Prerequisites
-------------

-  Before installing an ICAgent, ensure that the time and time zone of the local browser are consistent with those of the server. If multiple servers are deployed, ensure that the local browser and multiple servers use the same time zone and time. Otherwise, metric data of applications and servers displayed on the UI may be incorrect.
-  An ICAgent process needs to be installed and run by the **root** user.

Installation Methods
--------------------

There are two methods to install an ICAgent. Note that the two methods are not applicable to container nodes created using CCE. For container nodes, you do not need to manually install an ICAgent. Instead, you only need to perform certain operations when creating clusters or deploying applications.

For details, see :ref:`Table 1 <aom_02_002301__en-us_topic_0263893622_td567fa2f6ccc421ca2e6a4b8a51ee8c6>`.

.. _aom_02_002301__en-us_topic_0263893622_td567fa2f6ccc421ca2e6a4b8a51ee8c6:

.. table:: **Table 1** Installation methods

   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Method                            | Scenario                                                                                                                                                                                                                                                                                                 |
   +===================================+==========================================================================================================================================================================================================================================================================================================+
   | Initial installation              | This method is used when the following condition is met:                                                                                                                                                                                                                                                 |
   |                                   |                                                                                                                                                                                                                                                                                                          |
   |                                   | An ICAgent has never been installed on your server.                                                                                                                                                                                                                                                      |
   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Inherited installation            | This method is used when the following conditions are met:                                                                                                                                                                                                                                               |
   |                                   |                                                                                                                                                                                                                                                                                                          |
   |                                   | You have multiple servers where an ICAgent is to be installed. One server is bound to an EIP, but others are not. An ICAgent has been installed on the server bound to an EIP by using the initial installation method. You can use the inherited method to install an ICAgent on the remaining servers. |
   |                                   |                                                                                                                                                                                                                                                                                                          |
   |                                   | See :ref:`Inherited Installation <aom_02_0012__en-us_topic_0263893607_section490015619361>`.                                                                                                                                                                                                             |
   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Initial Installation
--------------------

After you apply for a server and install an ICAgent for the first time, perform the following operations:

#. Obtain an Access Key ID/Secret Access Key (AK/SK).

   -  If you have obtained the AK/SK, skip this step.
   -  If you have not obtained an AK/SK, :ref:`obtain them first <aom_03_0015>`.

#. In the navigation pane, choose **Configuration Management** > **Agent Management**.

#. Select **Other: custom hosts**, and click **Install ICAgent**.

#. (Optional) To prevent your AK/SK from being disclosed, select the check box shown in the following figure to disable historical record collection.


   .. figure:: /_static/images/en-us_image_0000001423571610.png
      :alt: **Figure 1** Copying the ICAgent installation command

      **Figure 1** Copying the ICAgent installation command

#. Generate the ICAgent installation command, and copy and run it to install an ICAgent.

#. After the ICAgent is installed, run the following command to enable historical record collection:

   **set -o history**

   .. note::

      -  If the message **ICAgent install success** is displayed, the ICAgent has been installed in the **/opt/oss/servicemgr/** directory. After the ICAgent is successfully installed, choose **Configuration Management** > **Agent Management** in the navigation pane on the left, and select **Other: custom hosts** to view the ICAgent status of the server.
      -  If the ICAgent fails to be installed, uninstall the ICAgent according to :ref:`Uninstalling the ICAgent by Logging In to the Server <aom_02_0014__en-us_topic_0263893549_section1218782615374>` and then install it again. If the problem persists, contact technical support.

Follow-up Operations
--------------------

For more information about how to install, upgrade, and uninstall the ICAgent, see :ref:`ICAgent Management <aom_02_0011>`.
