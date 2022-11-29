:original_name: aom_04_1016.html

.. _aom_04_1016:

Querying a Threshold Rule
=========================

Function
--------

This API is used to query a threshold rule.

URI
---

GET /v2/{project_id}/ams/alarms/{alarm_id}

Request
-------

**Request parameters**

:ref:`Table 1 <aom_04_1016__d0e3305>` describes the request parameters.

.. _aom_04_1016__d0e3305:

.. table:: **Table 1** Request parameters

   +------------+-----------+--------+-----------------------------------------------------------------------+-------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Value Range                                                           | Description                                                                   |
   +============+===========+========+=======================================================================+===============================================================================+
   | project_id | Yes       | String | ``-``                                                                 | Project ID obtained from IAM. Generally, a project ID contains 32 characters. |
   +------------+-----------+--------+-----------------------------------------------------------------------+-------------------------------------------------------------------------------+
   | alarm_id   | Yes       | String | Non-null value that can be converted to a value of the **long** type. | Threshold rule ID.                                                            |
   +------------+-----------+--------+-----------------------------------------------------------------------+-------------------------------------------------------------------------------+

**Request headers**

:ref:`Table 2 <aom_04_1016__table17428844137>` describes the request headers.

.. _aom_04_1016__table17428844137:

.. table:: **Table 2** Request headers

   ============ ========= ============================================
   Name         Mandatory Description
   ============ ========= ============================================
   X-Auth-Token Yes       User token obtained from IAM.
   Content-Type Yes       Content type, which is **application/json**.
   ============ ========= ============================================

Response
--------

**Response parameters**

:ref:`Table 3 <aom_04_1016__d0e3376>` describes the response parameters.

.. _aom_04_1016__d0e3376:

.. table:: **Table 3** Response parameters

   ============ ========== ====================
   Parameter    Type       Description
   ============ ========== ====================
   errorCode    String     Response code.
   errorMessage String     Response message.
   thresholds   JSON array Threshold rule list.
   ============ ========== ====================

**Example response**

.. code-block::

   {
       "errorCode": "AOM.0200",
       "errorMessage": "success",
       "thresholds":
       [
       {
           "id": "2137",
           "alarmName": "aaaaaaaa",
           "alarmDescription": "",
           "actionEnabled": false,
           "okActions": [],
           "alarmActions": [],
           "insufficientDataActions": [],
           "stateValue": "alarm",
           "stateReason": "",
           "stateUpdatedTimestamp": null,
           "metricName": "cpuCoreLimit",
           "namespace": "PAAS.CONTAINER",
           "statistic": "average",
           "dimensions": [
               {
                   "name": "appName",
                   "value": "rhm-broker"
               }
           ],
           "period": 60000,
           "evaluationPeriods": 1,
           "unit": "Core",
           "threshold": "0",
           "comparisonOperator": ">=",
           "alarmAdvice": "",
           "alarmLevel": 3
       }
       ]
   }

Status Code
-----------

-  Success response

   :ref:`Table 4 <aom_04_1016__table86491459125016>` describes the status code.

   .. _aom_04_1016__table86491459125016:

   .. table:: **Table 4** Status code

      =========== ======= ==========================
      Status Code Message Description
      =========== ======= ==========================
      200         OK      The request has succeeded.
      =========== ======= ==========================

-  Error response

   :ref:`Table 5 <aom_04_1016__table939134985614>` describes the status codes. For more information, see :ref:`Status Codes <aom_04_0018>`.

   .. _aom_04_1016__table939134985614:

   .. table:: **Table 5** Status codes

      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Status Code           | Message               | Description                                                                                                                                                         |
      +=======================+=======================+=====================================================================================================================================================================+
      | 400                   | Bad Request           | The request is invalid.                                                                                                                                             |
      |                       |                       |                                                                                                                                                                     |
      |                       |                       | The client should not repeat the request without modifications.                                                                                                     |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | 401                   | Unauthorized          | The authorization information provided by the client is incorrect or invalid.                                                                                       |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | 403                   | Forbidden             | The request is rejected.                                                                                                                                            |
      |                       |                       |                                                                                                                                                                     |
      |                       |                       | The server has received the request and understood it, but the server is refusing to respond to it. The client should not repeat the request without modifications. |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | 500                   | Internal Server Error | The server is able to receive the request but unable to understand the request.                                                                                     |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | 503                   | Service Unavailable   | The requested service is invalid.                                                                                                                                   |
      |                       |                       |                                                                                                                                                                     |
      |                       |                       | The client should not repeat the request without modifications.                                                                                                     |
      +-----------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Error Code
----------

.. table:: **Table 6** Error codes

   +------------+--------------------------------------+-------------------------------------------------+
   | Error Code | Message                              | Solution                                        |
   +============+======================================+=================================================+
   | AOM.0115   | Invalid request parameter.           | Check whether the parameter meets requirements. |
   +------------+--------------------------------------+-------------------------------------------------+
   | AOM.0501   | The Cassandra session is null.       | Contact technical support.                      |
   +------------+--------------------------------------+-------------------------------------------------+
   | AOM.0502   | The Cassandra execution is abnormal. | Contact technical support.                      |
   +------------+--------------------------------------+-------------------------------------------------+
