:original_name: UpdateAlarmRule.html

.. _UpdateAlarmRule:

Modifying a Threshold Rule
==========================

Function
--------

This API is used to modify a threshold rule.

URI
---

PUT /v2/{project_id}/alarm-rules

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+-------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                   |
   +============+===========+========+===============================================================================+
   | project_id | Yes       | String | Project ID obtained from IAM. Generally, a project ID contains 32 characters. |
   +------------+-----------+--------+-------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +-----------------+-----------------+-----------------+------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                              |
   +=================+=================+=================+==========================================+
   | X-Auth-Token    | Yes             | String          | User token obtained from IAM.            |
   +-----------------+-----------------+-----------------+------------------------------------------+
   | Content-Type    | Yes             | String          | Content type, which is application/json. |
   |                 |                 |                 |                                          |
   |                 |                 |                 | Enumeration values:                      |
   |                 |                 |                 |                                          |
   |                 |                 |                 | -  **application/json**                  |
   +-----------------+-----------------+-----------------+------------------------------------------+

.. table:: **Table 3** Request body parameters

   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter                 | Mandatory       | Type                                                                   | Description                                                                                                                                                                   |
   +===========================+=================+========================================================================+===============================================================================================================================================================================+
   | action_enabled            | No              | Boolean                                                                | Whether to enable notification.                                                                                                                                               |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | alarm_actions             | No              | Array of strings                                                       | List of alarm notifications.                                                                                                                                                  |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | alarm_advice              | No              | String                                                                 | Alarm clearance suggestion, which contains a maximum of 255 characters.                                                                                                       |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | Minimum: **0**                                                                                                                                                                |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | Maximum: **255**                                                                                                                                                              |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | alarm_description         | No              | String                                                                 | Threshold rule description, which contains a maximum of 1024 characters.                                                                                                      |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | Minimum: **0**                                                                                                                                                                |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | Maximum: **1024**                                                                                                                                                             |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | alarm_level               | Yes             | Integer                                                                | Alarm severity. Values: 1 (critical), 2 (major), 3 (minor), and 4 (warning).                                                                                                  |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | Enumeration values:                                                                                                                                                           |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **1**                                                                                                                                                                      |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **2**                                                                                                                                                                      |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **3**                                                                                                                                                                      |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **4**                                                                                                                                                                      |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | alarm_rule_name           | Yes             | String                                                                 | Threshold rule name. Enter a maximum of 100 characters and do not start or end with a special character. Only letters, digits, underscores (_), and hyphens (-) are allowed.  |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | comparison_operator       | Yes             | String                                                                 | Comparison operator. Options: <: less than the threshold; >: greater than the threshold; <=: less than or equal to the threshold; >=: greater than or equal to the threshold. |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | Enumeration values:                                                                                                                                                           |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **<**                                                                                                                                                                      |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **>**                                                                                                                                                                      |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **<=**                                                                                                                                                                     |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **>=**                                                                                                                                                                     |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dimensions                | Yes             | Array of :ref:`Dimension <updatealarmrule__request_dimension>` objects | List of time series dimensions.                                                                                                                                               |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | evaluation_periods        | Yes             | Integer                                                                | Interval at which data is calculated.                                                                                                                                         |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | id_turn_on                | No              | Boolean                                                                | Whether to enable the threshold rule.                                                                                                                                         |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | insufficient_data_actions | No              | Array of strings                                                       | List of insufficient data notifications.                                                                                                                                      |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | metric_name               | Yes             | String                                                                 | Time series name. Length: 1 to 255 characters.                                                                                                                                |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | namespace                 | Yes             | String                                                                 | Namespace of time series objects.                                                                                                                                             |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ok_actions                | No              | Array of strings                                                       | List of normal status notifications.                                                                                                                                          |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | period                    | Yes             | Integer                                                                | Statistical period. Options: 60000: one minute; 300000: five minutes; 900000: 15 minutes; 3600000: one hour.                                                                  |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | Enumeration values:                                                                                                                                                           |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **60000**                                                                                                                                                                  |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **300000**                                                                                                                                                                 |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **900000**                                                                                                                                                                 |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **36000000**                                                                                                                                                               |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | statistic                 | Yes             | String                                                                 | Statistic.                                                                                                                                                                    |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | Enumeration values:                                                                                                                                                           |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **maximum**                                                                                                                                                                |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **minimum**                                                                                                                                                                |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **average**                                                                                                                                                                |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **sum**                                                                                                                                                                    |
   |                           |                 |                                                                        |                                                                                                                                                                               |
   |                           |                 |                                                                        | -  **sampleCount**                                                                                                                                                            |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | threshold                 | Yes             | String                                                                 | Threshold.                                                                                                                                                                    |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | unit                      | Yes             | String                                                                 | Time series unit.                                                                                                                                                             |
   +---------------------------+-----------------+------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _updatealarmrule__request_dimension:

.. table:: **Table 4** Dimension

   ========= ========= ====== ================
   Parameter Mandatory Type   Description
   ========= ========= ====== ================
   name      Yes       String Dimension name.
   value     Yes       String Dimension value.
   ========= ========= ====== ================

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 5** Response body parameters

   ============= ==== ==================
   Parameter     Type Description
   ============= ==== ==================
   alarm_rule_id Long Threshold rule ID.
   ============= ==== ==================

**Status code: 400**

.. table:: **Table 6** Response body parameters

   +------------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Type   | Description                                                                                                                                         |
   +============+========+=====================================================================================================================================================+
   | error_code | String | Error code.                                                                                                                                         |
   +------------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
   | error_msg  | String | Error message.                                                                                                                                      |
   +------------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
   | error_type | String | Error type.                                                                                                                                         |
   +------------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------+
   | trace_id   | String | Trace ID, which is used to search for logs and locate faults. If **2xx** is returned, **trace_id** is empty. If **4xx**, **trace_id** is not empty. |
   +------------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------+

Example Requests
----------------

Modify a threshold rule whose name is **testaom**, alarm severity is **3**, metric name is **cpuCoreLimit**, and namespace is **PAAS.CONTAINER**.

.. code-block::

   https://{Endpoint}/v2/{project_id}/alarm-rules

   {
     "action_enabled" : false,
     "alarm_actions" : [ ],
     "alarm_advice" : "",
     "alarm_description" : "",
     "alarm_level" : 3,
     "alarm_rule_name" : "aom_rule",
     "comparison_operator" : ">=",
     "dimensions" : [ {
       "name" : "appName",
       "value" : "rhm-broker"
     } ],
     "evaluation_periods" : 1,
     "insufficient_data_actions" : [ ],
     "metric_name" : "cpuCoreLimit",
     "namespace" : "PAAS.CONTAINER",
     "ok_actions" : [ ],
     "period" : 60000,
     "statistic" : "average",
     "threshold" : 0,
     "unit" : "Core"
   }

Example Responses
-----------------

**Status code: 200**

OK: The request is successful.

.. code-block::

   {
     "alarm_rule_id" : 91307490000416600
   }

**Status code: 400**

Bad Request: The request is invalid. The client should not repeat the request without modifications.

.. code-block::

   {
     "error_code" : "AOM.02001AOM.02001SVCSTG_AMS_4000115",
     "error_msg" : "please check request param",
     "error_type" : "BAD_REQUEST",
     "trace_id" : ""
   }

Status Codes
------------

+-------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Status Code | Description                                                                                                                                                                                         |
+=============+=====================================================================================================================================================================================================+
| 200         | OK: The request is successful.                                                                                                                                                                      |
+-------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 400         | Bad Request: The request is invalid. The client should not repeat the request without modifications.                                                                                                |
+-------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 401         | Unauthorized: The authentication information is incorrect or invalid.                                                                                                                               |
+-------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 403         | Forbidden: The request is rejected. The server has received the request and understood it, but the server refuses to respond to it. The client should not repeat the request without modifications. |
+-------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 500         | Internal Server Error: The server is able to receive the request but unable to understand the request.                                                                                              |
+-------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 503         | Service Unavailable: The requested service is invalid. The client should not repeat the request without modifications.                                                                              |
+-------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.
