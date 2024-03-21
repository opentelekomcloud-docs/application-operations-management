:original_name: aom_04_0022.html

.. _aom_04_0022:

Introduction
============

This section describes fine-grained permissions management for AOM. If your cloud account does not need individual IAM users, then you may skip over this section.

By default, new IAM users do not have any permissions assigned. You need to add a user to one or more groups, and assign permissions policies or roles to these groups. The user then inherits permissions from the groups it is a member of. This process is called authorization. After authorization, the user can perform specified operations on AOM.

You can grant users permissions by using roles and policies. Roles are a type of coarse-grained authorization mechanism that defines permissions related to user responsibilities. Policies define API-based permissions for operations on specific resources under certain conditions, allowing for more fine-grained, secure access control of cloud resources.

.. note::

   Policy-based authorization is recommended if you want to allow or deny the access to an API.

Each account has all the permissions required to call all APIs, but IAM users must be assigned the required permissions. The permissions required for calling an API are determined by the actions supported by the API. Only users who have been granted permissions can call the API successfully. For example, if an IAM user queries metrics using an API, the user must have been granted permissions that allow the **aom:metric:get** action.

Supported Actions
-----------------

There are two kinds of policies: system-defined policies and custom policies. If the permissions preset in the system do not meet your requirements, you can create custom policies and apply these policies to user groups for refined access control. Operations supported by policies are specific to APIs. The following are common concepts related to policies:

-  Permissions: Defined by actions in a custom policy.
-  APIs: REST APIs that can be called in a custom policy.
-  Actions: Added to a custom policy to control permissions for specific operations.
-  IAM projects and enterprise projects: Type of projects for which an action will take effect. Policies that contain actions supporting both IAM and enterprise projects can be assigned to user groups and take effect in both IAM and Enterprise Management. Policies that only contain actions supporting IAM projects can be assigned to user groups and only take effect for IAM. Such policies will not take effect if they are assigned to user groups in Enterprise Management.

AOM supports the following actions that can be defined in custom policies:

-  :ref:`Monitoring Actions <aom_04_0062>`: includes the actions supported by monitoring APIs, such as the APIs for querying metrics and monitoring data.
-  :ref:`Log Actions <aom_04_0064>`: includes the actions supported by log APIs, such as the API for querying logs.
-  :ref:`Alarm Actions <aom_04_0065>`: includes the actions supported by alarm APIs, such as the API for querying events and alarms.
