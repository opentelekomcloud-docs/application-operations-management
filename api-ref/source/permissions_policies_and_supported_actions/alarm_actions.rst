:original_name: aom_04_0065.html

.. _aom_04_0065:

Alarm Actions
=============

.. note::

   Y: supported; x: not supported

.. table:: **Table 1** Alarm actions

   +-----------------------------+----------------------------------------+----------------+-------------+--------------------+
   | Permissions                 | API                                    | Action         | IAM Project | Enterprise Project |
   +=============================+========================================+================+=============+====================+
   | Querying events and alarms  | POST /v2/{project_id}/events           | aom:alarm:list | Y           | x                  |
   +-----------------------------+----------------------------------------+----------------+-------------+--------------------+
   | Counting events and alarms  | POST /v2/{project_id}/events/statistic | aom:alarm:list | Y           | x                  |
   +-----------------------------+----------------------------------------+----------------+-------------+--------------------+
   | Reporting events and alarms | PUT /v2/{project_id}/push/events       | aom:alarm:put  | Y           | x                  |
   +-----------------------------+----------------------------------------+----------------+-------------+--------------------+
