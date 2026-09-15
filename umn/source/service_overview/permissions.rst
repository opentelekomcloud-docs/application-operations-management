:original_name: aom_06_0021.html

.. _aom_06_0021:

Permissions
===========

If you need to assign different permissions to employees in your enterprise to access your AOM resources, Identity and Access Management (IAM) is a good choice for fine-grained permissions management. IAM provides identity authentication, permissions management, and access control, helping you secure access to your AOM resources.

With IAM, you can use your account to create IAM users for your employees, and assign permissions to the users to control their access to specific types of resources. For example, some software developers in your enterprise need to use AOM resources but are not allowed to delete them or perform any high-risk operations such as deleting application discovery rules. To achieve this result, you can create IAM users for the software developers and grant them only the permissions required for using AOM resources.

If your cloud account does not need individual IAM users for permissions management, you may skip over this chapter.

IAM can be used free of charge. You pay only for the resources in your account. For more information about IAM, see `IAM Service Overview <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0026.html>`__.

AOM Permissions
---------------

By default, new IAM users do not have any permissions assigned. You need to add a user to one or more groups, and assign permissions policies or roles to these groups. The user then inherits permissions from the groups it is a member of. This process is called authorization. After authorization, the user can perform specified operations on AOM.

AOM is a project-level service deployed and accessed in specific physical regions. To assign AOM permissions to a user group, specify the scope as region-specific projects and select projects for the permissions to take effect. If **All projects** is selected, the permissions will take effect for the user group in all region-specific projects. When accessing AOM, the users need to switch to a region where they have been authorized to use this service.

You can grant users permissions by using roles and policies.

-  Roles: A type of coarse-grained authorization mechanism that defines permissions related to user responsibilities. This mechanism provides only a limited number of service-level roles for authorization. When using roles to grant permissions, you also need to assign dependency roles. However, roles are not an ideal choice for fine-grained authorization and secure access control.
-  Policies: A type of fine-grained authorization mechanism that defines permissions required to perform operations on specific cloud resources under certain conditions. This mechanism allows for more flexible policy-based authorization, meeting requirements for secure access control. For example, you can grant Elastic Cloud Server (ECS) users only the permissions for managing a certain type of ECSs.

:ref:`Table 1 <aom_06_0021__table145316572518>` lists all the system permissions supported by AOM.

.. _aom_06_0021__table145316572518:

.. table:: **Table 1** System permissions supported by AOM

   +-------------+---------------------------------------------------------------------------------------------+-----------------------+----------------------------------------------------------+
   | Policy Name | Description                                                                                 | Type                  | Depended System Permissions                              |
   +=============+=============================================================================================+=======================+==========================================================+
   | AOM Admin   | Administrator permissions for AOM. Users granted these permissions can operate and use AOM. | System-defined policy | CCE Administrator, OBS Administrator, and LTS FullAccess |
   +-------------+---------------------------------------------------------------------------------------------+-----------------------+----------------------------------------------------------+
   | AOM Viewer  | Read-only permissions for AOM. Users granted these permissions can only view AOM data.      | System-defined policy |                                                          |
   +-------------+---------------------------------------------------------------------------------------------+-----------------------+----------------------------------------------------------+

:ref:`Table 2 <aom_06_0021__table126113571055>` lists the common operations supported by each system-defined policy of AOM. Please choose proper system-defined policies according to this table.

.. _aom_06_0021__table126113571055:

.. table:: **Table 2** Common operations supported by each system-defined policy of AOM

   ======================================= ========= ==========
   Operation                               AOM Admin AOM Viewer
   ======================================= ========= ==========
   Creating a threshold rule               Y         x
   Modifying a threshold rule              Y         x
   Deleting a threshold rule               Y         x
   Creating a threshold template           Y         x
   Modifying a threshold template          Y         x
   Deleting a threshold template           Y         x
   Creating an application discovery rule  Y         x
   Modifying an application discovery rule Y         x
   Deleting an application discovery rule  Y         x
   Exporting a monitoring report           Y         Y
   Configuring a VM log collection path    Y         x
   Configuring a delimiter                 Y         x
   Installing the ICAgent                  Y         Y
   Upgrading the ICAgent                   Y         x
   Uninstalling the ICAgent                Y         x
   ======================================= ========= ==========

To use a custom fine-grained policy, log in to IAM as the administrator and select fine-grained permissions of AOM as required. For details, see :ref:`Table 3 <aom_06_0021__table13611192118526>`

.. _aom_06_0021__table13611192118526:

.. table:: **Table 3** Fine-grained permissions of AOM

   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | Permission Name          | Description                            | Dependency | Scenario                                                                  |
   +==========================+========================================+============+===========================================================================+
   | aom:alarmRule:create     | Creating a threshold rule              | N/A        | Creating a threshold rule                                                 |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:alarmRule:set        | Modifying a threshold rule             |            | Modifying a threshold rule                                                |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:alarmRule:get        | Querying threshold rules               |            | Querying all threshold rules or a single threshold rule by rule ID        |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:alarmRule:delete     | Deleting threshold rules               |            | Deleting threshold rules in batches or a single threshold rule by rule ID |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:discoveryRule:list   | Querying application discovery rules   |            | Querying existing application discovery rules                             |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:discoveryRule:delete | Deleting an application discovery rule |            | Deleting an application discovery rule                                    |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:discoveryRule:set    | Adding an application discovery rule   |            | Adding an application discovery rule                                      |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:metric:list          | Querying time series objects           |            | Querying time series objects                                              |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:metric:list          | Querying time series data              |            | Querying time series data                                                 |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:metric:get           | Querying metrics                       |            | Querying metrics                                                          |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:metric:get           | Querying monitoring data               |            | Querying monitoring data                                                  |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
