:original_name: DeleteAlarmRules.html

.. _DeleteAlarmRules:

Deleting Threshold Rules in Batches
===================================

Function
--------

This API is used to delete threshold rules in batches.

URI
---

POST /v2/{project_id}/alarm-rules/delete

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

   =========== ========= ================ ===============================
   Parameter   Mandatory Type             Description
   =========== ========= ================ ===============================
   alarm_rules Yes       Array of strings Name of the rule to be deleted.
   =========== ========= ================ ===============================

Response Parameters
-------------------

**Status code: 400**

.. table:: **Table 4** Response body parameters

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

Delete threshold rules in batches by rule name.

.. code-block::

   https://{Endpoint}/v2/{project_id}/alarm-rules/delete

   {
     "alarm_rules" : [ ]
   }

Example Responses
-----------------

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
