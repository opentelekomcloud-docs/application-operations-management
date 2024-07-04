:original_name: aom_00_0001.html

.. _aom_00_0001:

Process of Using AOM
====================

Application Operations Management (AOM) is a one-stop cloud operations management platform that helps you with problem management, monitoring, security, and performance. Streamline cloud operational processes and effectively manage cloud hardware, software, services, and networks.


.. figure:: /_static/images/en-us_image_0000001199786128.png
   :alt: **Figure 1** Process of using AOM

   **Figure 1** Process of using AOM

#. (Optional) Create IAM users and set permissions.

   Create IAM users for employees based on the organizational structure of your enterprise, and grant different access permissions to them.

#. (Mandatory) Create a cloud host.

   A host corresponds to a VM, for example, Elastic Cloud Server (ECS), or a physical machine, for example, Bare Metal Server (BMS). A host can be directly created on the ECS or BMS console, or indirectly created on the Cloud Container Engine (CCE) console.

#. (Mandatory) :ref:`Install an ICAgent <aom_00_0003>`.

   An ICAgent is a collector of AOM. It collects metrics, logs, and application performance data in real time. For hosts created on the ECS or BMS console, install the ICAgent manually. For hosts created on the CCE console, the ICAgent is automatically installed.

#. (Optional) Configure application discovery rules.

   Connect applications on the host to AOM for monitoring. For the applications that meet built-in application discovery rules, they will be automatically discovered after the ICAgent is installed. For those that do not meet built-in rules, custom your own rules.

#. (Optional) Configure a log collection path.

   To use AOM to monitor host logs, configure a log collection path first.

#. (Optional) Perform O&M.

   Use AOM functions such as , and alarm management to perform routine O&M.
