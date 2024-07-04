:original_name: aom_03_0037.html

.. _aom_03_0037:

Why Is "no crontab for root" Displayed During ICAgent Installation?
===================================================================

Symptom
-------

During ICAgent installation, the system displays the message "no crontab for root".


.. figure:: /_static/images/en-us_image_0000001759018189.png
   :alt: **Figure 1** Installing an ICAgent

   **Figure 1** Installing an ICAgent

Possible Causes
---------------

When you execute the script for installing an ICAgent, crontab scheduled tasks will also be installed. The message "no crontab for root" indicates that there is no scheduled task of the **root** user.

Solution
--------

No measure needs to be taken.

If the command output contains "ICAgent install success", the ICAgent is successfully installed and O&M data can be collected.
