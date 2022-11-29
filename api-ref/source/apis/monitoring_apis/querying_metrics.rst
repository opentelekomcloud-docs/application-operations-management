:original_name: aom_04_1011.html

.. _aom_04_1011:

Querying Metrics
================

Function
--------

This API is used to query the metrics that can be monitored in the system. You can specify the namespace, metric name, dimension, resource ID (format: **resType_resId**), start position, and maximum number of returned records in pagination queries.

URI
---

POST /v2/{project_id}/ams/metrics?type={type}&limit={limit}&start={start}

:ref:`Table 1 <aom_04_1011__table186473594509>` describes the parameters.

.. _aom_04_1011__table186473594509:

.. table:: **Table 1** Parameters

   +------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Description                                                                                                 |
   +============+===========+=============================================================================================================+
   | project_id | Yes       | Project ID obtained from IAM. Generally, a project ID contains 32 characters.                               |
   +------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | type       | No        | Metric query mode. The information carried by **metricItems** in the request body is used to query metrics. |
   +------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | limit      | No        | Maximum number of returned records. Value range: 1-1000. Default value: 1000.                               |
   +------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | start      | No        | Start position of a pagination query. The value is a non-negative integer.                                  |
   +------------+-----------+-------------------------------------------------------------------------------------------------------------+

Request
-------

**Request parameters**

:ref:`Table 2 <aom_04_1011__table1221212122718>` describes the request parameters.

.. _aom_04_1011__table1221212122718:

.. table:: **Table 2** Request parameter

   +-------------+-----------+--------+--------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------+
   | Parameter   | Mandatory | Type   | Value Range                                            | Description                                                                                                        |
   +=============+===========+========+========================================================+====================================================================================================================+
   | metricItems | No        | Arrays | See :ref:`Table 3 <aom_04_1011__table71641056115911>`. | If **type** (a URI parameter) is not **inventory**, the information carried by the array is used to query metrics. |
   +-------------+-----------+--------+--------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------+

.. _aom_04_1011__table71641056115911:

.. table:: **Table 3** metricItems parameters

   +-------------+-------------+-------------+---------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter   | Mandatory   | Type        | Value Range                                                               | Description                                                                                                                                     |
   +=============+=============+=============+===========================================================================+=================================================================================================================================================+
   | namespace   | Yes         | String      | PAAS.CONTAINER, PAAS.NODE, PAAS.SLA, PAAS.AGGR, CUSTOMMETRICS, and so on. | Metric namespace.                                                                                                                               |
   |             |             |             |                                                                           |                                                                                                                                                 |
   |             |             |             |                                                                           | PAAS.CONTAINER: application metric.                                                                                                             |
   |             |             |             |                                                                           |                                                                                                                                                 |
   |             |             |             |                                                                           | PAAS.NODE: node metric.                                                                                                                         |
   |             |             |             |                                                                           |                                                                                                                                                 |
   |             |             |             |                                                                           | PAAS.SLA: Service Level Agreement (SLA) metric.                                                                                                 |
   |             |             |             |                                                                           |                                                                                                                                                 |
   |             |             |             |                                                                           | PAAS.AGGR: cluster metric.                                                                                                                      |
   |             |             |             |                                                                           |                                                                                                                                                 |
   |             |             |             |                                                                           | CUSTOMMETRICS: custom metric.                                                                                                                   |
   +-------------+-------------+-------------+---------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
   | dimensions  | No          | Array       | ``-``                                                                     | Metric dimension.                                                                                                                               |
   |             |             |             |                                                                           |                                                                                                                                                 |
   |             |             |             |                                                                           | dimensions.name: dimension name, such as clusterName, clusterId, appName, appID, deploymentName, podName, podID, containerName, or containerID. |
   |             |             |             |                                                                           |                                                                                                                                                 |
   |             |             |             |                                                                           | dimensions.value: dimension value, such as a specific application instance ID.                                                                  |
   +-------------+-------------+-------------+---------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+
   | metricName  | No          | String      | 1-1000 characters.                                                        | Metric name.                                                                                                                                    |
   +-------------+-------------+-------------+---------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------+

**Request headers**

:ref:`Table 4 <aom_04_1011__table17428844137>` describes the request headers.

.. _aom_04_1011__table17428844137:

.. table:: **Table 4** Request headers

   ============ ========= ============================================
   Name         Mandatory Description
   ============ ========= ============================================
   X-Auth-Token Yes       User token obtained from IAM.
   Content-Type Yes       Content type, which is **application/json**.
   ============ ========= ============================================

**Example request**

(Query by namespace+appName+clusterName)

.. code-block::

   /v2/{projectId}/ams/metrics
   {
       "metricItems": [
           {
               "namespace": "PAAS.CONTAINER",
               "dimensions":[
                   {
                       "name":"appName",
                       "value":"demo"
                   },
                   {
                       "name":"clusterName",
                       "value":"test"
                   }
               ]
           }
       ]
   }

Response
--------

**Response parameters**

:ref:`Table 5 <aom_04_1011__table6943113915268>` describes the response parameters.

.. _aom_04_1011__table6943113915268:

.. table:: **Table 5** Response parameters

   +--------------+------------+-----------------------------------------------------------------------+
   | Parameter    | Type       | Description                                                           |
   +==============+============+=======================================================================+
   | errorCode    | String     | Response code. Example: AOM.0200, which indicates a success response. |
   +--------------+------------+-----------------------------------------------------------------------+
   | errorMessage | String     | Response message.                                                     |
   +--------------+------------+-----------------------------------------------------------------------+
   | metrics      | JSON array | List of metrics.                                                      |
   +--------------+------------+-----------------------------------------------------------------------+
   | namespace    | String     | Namespace.                                                            |
   +--------------+------------+-----------------------------------------------------------------------+
   | metricName   | String     | Metric name.                                                          |
   +--------------+------------+-----------------------------------------------------------------------+
   | unit         | String     | Metric unit.                                                          |
   +--------------+------------+-----------------------------------------------------------------------+
   | dimensions   | JSON array | List of metric dimensions.                                            |
   +--------------+------------+-----------------------------------------------------------------------+

**Example response**

.. code-block::

   {
       "errorCode": "AOM.0200",
       "errorMessage": "success",
       "metrics": [{
           "namespace": "abc",
           "metricName": "cpuUsage",
           "unit":"Percent",
           "dimensions": [{
                       "name": "instance_id",
                       "value": "demo1"
           }]
       }]
   }

Status Code
-----------

-  Success response

   :ref:`Table 6 <aom_04_1011__table86491459125016>` describes the status code.

   .. _aom_04_1011__table86491459125016:

   .. table:: **Table 6** Status code

      =========== ======= ==========================
      Status Code Message Description
      =========== ======= ==========================
      200         OK      The request has succeeded.
      =========== ======= ==========================

-  Error response

   :ref:`Table 7 <aom_04_1011__table7649145915013>` describes the status codes. For more information, see :ref:`Status Codes <aom_04_0018>`.

   .. _aom_04_1011__table7649145915013:

   .. table:: **Table 7** Status codes

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

.. table:: **Table 8** Error codes

   +------------+--------------------------------------+-------------------------------------------------+
   | Error Code | Message                              | Solution                                        |
   +============+======================================+=================================================+
   | AOM.0101   | Invalid namespace.                   | Check whether the parameter meets requirements. |
   +------------+--------------------------------------+-------------------------------------------------+
   | AOM.0102   | Invalid inventoryId.                 | Check whether the parameter meets requirements. |
   +------------+--------------------------------------+-------------------------------------------------+
   | AOM.0103   | ProjectId is left blank.             | Check whether the parameter meets requirements. |
   +------------+--------------------------------------+-------------------------------------------------+
   | AOM.0105   | Invalid limit.                       | Check whether the parameter meets requirements. |
   +------------+--------------------------------------+-------------------------------------------------+
   | AOM.0106   | Invalid start.                       | Check whether the parameter meets requirements. |
   +------------+--------------------------------------+-------------------------------------------------+
   | AOM.0109   | Invalid metricName.                  | Check whether the parameter meets requirements. |
   +------------+--------------------------------------+-------------------------------------------------+
   | AOM.0501   | The Cassandra session is null.       | Contact technical support.                      |
   +------------+--------------------------------------+-------------------------------------------------+
   | AOM.0502   | The Cassandra execution is abnormal. | Contact technical support.                      |
   +------------+--------------------------------------+-------------------------------------------------+
