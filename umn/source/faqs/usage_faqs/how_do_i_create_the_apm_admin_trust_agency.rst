:original_name: aom_03_0024.html

.. _aom_03_0024:

How Do I Create the apm_admin_trust Agency?
===========================================

Procedure
---------

#. Log in to the IAM console.

#. In the navigation pane, choose **Agencies**.

#. On the page that is displayed, click **Create Agency** in the upper right corner. The **Create Agency** page is displayed.

#. Set parameters based on :ref:`Table 1 <aom_03_0024__en-us_topic_0159938463_t7927638d398c4cc593fe522b3e57a455>`.

   .. _aom_03_0024__en-us_topic_0159938463_t7927638d398c4cc593fe522b3e57a455:

   .. table:: **Table 1** Parameters for creating an agency

      +-----------------------+-----------------------------------------------------+-----------------------+
      | Parameter             | Description                                         | Example               |
      +=======================+=====================================================+=======================+
      | Agency Name           | Set an agency name.                                 | ``-``                 |
      |                       |                                                     |                       |
      |                       | .. important::                                      |                       |
      |                       |                                                     |                       |
      |                       |    NOTICE:                                          |                       |
      |                       |    The agency name must be **apm_admin_trust**.     |                       |
      +-----------------------+-----------------------------------------------------+-----------------------+
      | Agency Type           | Select **Cloud service**.                           | Cloud service         |
      +-----------------------+-----------------------------------------------------+-----------------------+
      | Cloud Service         | Select **Application Operations Management (AOM)**. | ``-``                 |
      +-----------------------+-----------------------------------------------------+-----------------------+
      | Validity Period       | Select **Unlimited**.                               | Unlimited             |
      +-----------------------+-----------------------------------------------------+-----------------------+
      | Description           | (Optional) Provide details about the agency.        | ``-``                 |
      +-----------------------+-----------------------------------------------------+-----------------------+

#. On the **Permissions** area, click **Assign Permissions**.

#. Select the **DMS UserAccess** permission, and select the projects where you want the configuration to take effect.

#. Click **OK**.
