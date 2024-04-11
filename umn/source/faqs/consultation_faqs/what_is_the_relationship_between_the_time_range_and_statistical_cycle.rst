:original_name: aom_03_0009.html

.. _aom_03_0009:

What Is the Relationship Between the Time Range and Statistical Cycle?
======================================================================

For Application Operations Management (AOM), a maximum of 1440 data points can be returned for a single metric query. The relationship between the time range and statistical cycle is as follows:

Maximum time range = Statistical cycle x 1440

If you select a time range shorter than or equal to the maximum time range, all the statistical cycles that meet the preceding formula can be selected. For example, if you query metrics in the last 1 hour, the available statistical cycles are 1 minute and 5 minutes.

:ref:`Table 1 <aom_03_0009__table2206532177>` shows the relationship between the time range and statistical cycle.

.. _aom_03_0009__table2206532177:

.. table:: **Table 1** Relationship between the time range and statistical cycle

   +-----------------------------------+--------------------------------------------------------------------------------+
   | Time Range                        | Statistical Cycle                                                              |
   +===================================+================================================================================+
   | Last 1 hour                       | 1 minute or 5 minutes                                                          |
   +-----------------------------------+--------------------------------------------------------------------------------+
   | Last 6 hours                      | 1 minute, 5 minutes, or 1 hour                                                 |
   +-----------------------------------+--------------------------------------------------------------------------------+
   | Last 1 day                        |                                                                                |
   +-----------------------------------+--------------------------------------------------------------------------------+
   | Last 7 days                       | 1 hour or 1 day                                                                |
   |                                   |                                                                                |
   |                                   | .. note::                                                                      |
   |                                   |                                                                                |
   |                                   |    **1 day** is only for the metrics generated based on log statistical rules. |
   +-----------------------------------+--------------------------------------------------------------------------------+
   | Last 15 days                      | 1 hour or 1 day                                                                |
   |                                   |                                                                                |
   |                                   | .. note::                                                                      |
   |                                   |                                                                                |
   |                                   |    **1 day** is only for the metrics generated based on log statistical rules. |
   +-----------------------------------+--------------------------------------------------------------------------------+
   | Last 30 days                      |                                                                                |
   +-----------------------------------+--------------------------------------------------------------------------------+
   | Last 3 months                     |                                                                                |
   +-----------------------------------+--------------------------------------------------------------------------------+
   | Last 6 months                     |                                                                                |
   +-----------------------------------+--------------------------------------------------------------------------------+
   | Last 9 months                     |                                                                                |
   +-----------------------------------+--------------------------------------------------------------------------------+
   | Last 12 months                    |                                                                                |
   +-----------------------------------+--------------------------------------------------------------------------------+
