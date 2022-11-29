:original_name: aom_04_1013.html

.. _aom_04_1013:

Adding Monitoring Data
======================

Function
--------

This API is used to add one or more monitoring data records to a server.

URI
---

POST /v2/{project_id}/ams/report/metricdata

:ref:`Table 1 <aom_04_1013__table369962415599>` describes the parameters.

.. _aom_04_1013__table369962415599:

.. table:: **Table 1** Parameters

   +------------+-----------+-------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Description                                                                   |
   +============+===========+===============================================================================+
   | project_id | Yes       | Project ID obtained from IAM. Generally, a project ID contains 32 characters. |
   +------------+-----------+-------------------------------------------------------------------------------+

Request
-------

**Request parameters**

:ref:`Table 2 <aom_04_1013__table539122593914>` describes the request parameters.

.. _aom_04_1013__table539122593914:

.. table:: **Table 2** Request parameters

   +--------------+-------------+----------------+--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------+
   | Parameter    | Mandatory   | Type           | Value Range                                            | Description                                                                                                   |
   +==============+=============+================+========================================================+===============================================================================================================+
   | metric       | Yes         | JSON object    | See :ref:`Table 3 <aom_04_1013__table682420139176>`.   | Metric data.                                                                                                  |
   +--------------+-------------+----------------+--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------+
   | values       | Yes         | JSON array     | See :ref:`Table 4 <aom_04_1013__table15287516161811>`. | ``-``                                                                                                         |
   +--------------+-------------+----------------+--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------+
   | collect_time | Yes         | UNIX timestamp | UNIX timestamp, in ms.                                 | Data collection time, which must meet the following requirement:                                              |
   |              |             |                |                                                        |                                                                                                               |
   |              |             |                |                                                        | Current UTC time - Data collection time <= 24 hours, or Data collection time - Current UTC time <= 30 minutes |
   +--------------+-------------+----------------+--------------------------------------------------------+---------------------------------------------------------------------------------------------------------------+

.. _aom_04_1013__table682420139176:

.. table:: **Table 3** metric parameters

   +-------------+-------------+-------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------+
   | Parameter   | Mandatory   | Type        | Value Range                                                                                                                                                                                                                                 | Description                |
   +=============+=============+=============+=============================================================================================================================================================================================================================================+============================+
   | namespace   | Yes         | String      | Namespace, which must be in the format of service.item. The value must be 3 to 32 characters starting with a letter. Only letters, digits, and underscores (_) are allowed. In addition, **service** cannot start with **PAAS** or **SYS**. | Metric namespace.          |
   +-------------+-------------+-------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------+
   | dimensions  | Yes         | JSON array  | Each dimension is a JSON object, and its structure is as follows:                                                                                                                                                                           | List of metric dimensions. |
   |             |             |             |                                                                                                                                                                                                                                             |                            |
   |             |             |             | dimension.name: 1-32 characters.                                                                                                                                                                                                            |                            |
   |             |             |             |                                                                                                                                                                                                                                             |                            |
   |             |             |             | dimension.value: 1-64 characters.                                                                                                                                                                                                           |                            |
   +-------------+-------------+-------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------+

.. _aom_04_1013__table15287516161811:

.. table:: **Table 4** values parameters

   +-------------+-----------+-----------------+----------------------------+---------------+
   | Parameter   | Mandatory | Type            | Value Range                | Description   |
   +=============+===========+=================+============================+===============+
   | unit        | No        | String          | ``-``                      | Data unit.    |
   +-------------+-----------+-----------------+----------------------------+---------------+
   | metric_name | Yes       | String          | ``-``                      | Metric name.  |
   +-------------+-----------+-----------------+----------------------------+---------------+
   | type        | No        | String          | Integer or floating number | Data type.    |
   +-------------+-----------+-----------------+----------------------------+---------------+
   | value       | Yes       | Floating number | Valid numeral type.        | Metric value. |
   +-------------+-----------+-----------------+----------------------------+---------------+

**Request headers**

:ref:`Table 5 <aom_04_1013__table17428844137>` describes the request headers.

.. _aom_04_1013__table17428844137:

.. table:: **Table 5** Request headers

   ============ ========= ============================================
   Name         Mandatory Description
   ============ ========= ============================================
   X-Auth-Token Yes       User token obtained from IAM.
   Content-Type Yes       Content type, which is **application/json**.
   ============ ========= ============================================

**Example request**

.. code-block::

   [
       {
           "metric": {
               "namespace": "NOPAAS.ESC",
               "dimensions": [
                   {
                       "name": "instance_id",
                       "value": "instance-101"
                   }
               ]
           },
           "values": [
               {
                   "unit": "percent",
                   "metric_name": "cpu_util",
                   "type": "int",
                   "value": 35
               }
           ],
           "collect_time": 1467787152000
       }
   ]

Response
--------

**Response parameters**

:ref:`Table 6 <aom_04_1013__table03641013479>` describes the response parameters.

.. _aom_04_1013__table03641013479:

.. table:: **Table 6** Response parameters

   ============ ====== =================
   Parameter    Type   Description
   ============ ====== =================
   errorCode    String Response code.
   errorMessage String Response message.
   ============ ====== =================

**Example response**

.. code-block::

   {
       "errorCode": "AOM.0200",
       "errorMessage": "success"
   }

Status Code
-----------

-  Success response

   :ref:`Table 7 <aom_04_1013__table86491459125016>` describes the status code.

   .. _aom_04_1013__table86491459125016:

   .. table:: **Table 7** Status code

      =========== ======= ==========================
      Status Code Message Description
      =========== ======= ==========================
      200         OK      The request has succeeded.
      =========== ======= ==========================

-  Error response

   :ref:`Table 8 <aom_04_1013__table939134985614>` describes the status codes. For more information, see :ref:`Status Codes <aom_04_0018>`.

   .. _aom_04_1013__table939134985614:

   .. table:: **Table 8** Status codes

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

.. table:: **Table 9** Error codes

   +------------+------------------------------------------------+-------------------------------------------------+
   | Error Code | Message                                        | Solution                                        |
   +============+================================================+=================================================+
   | AOM.0001   | Invalid request parameter.                     | Check whether the parameter meets requirements. |
   +------------+------------------------------------------------+-------------------------------------------------+
   | AOM.0002   | Invalid namespace.                             | Check whether the parameter meets requirements. |
   +------------+------------------------------------------------+-------------------------------------------------+
   | AOM.0003   | Dimensions are left blank.                     | Check whether the parameter meets requirements. |
   +------------+------------------------------------------------+-------------------------------------------------+
   | AOM.0005   | Invalid metric data type.                      | Check whether the parameter meets requirements. |
   +------------+------------------------------------------------+-------------------------------------------------+
   | AOM.0006   | The metric data value is left blank.           | Check whether the parameter meets requirements. |
   +------------+------------------------------------------------+-------------------------------------------------+
   | AOM.0007   | Invalid name or value length in the dimension. | Check whether the parameter meets requirements. |
   +------------+------------------------------------------------+-------------------------------------------------+
   | AOM.0008   | The request exceeds 40 KB.                     | Check whether the parameter meets requirements. |
   +------------+------------------------------------------------+-------------------------------------------------+
   | AOM.0009   | A metric supports a maximum of 20 dimensions.  | Check whether the parameter meets requirements. |
   +------------+------------------------------------------------+-------------------------------------------------+
   | AOM.0010   | Invalid collection time.                       | Check whether the parameter meets requirements. |
   +------------+------------------------------------------------+-------------------------------------------------+
   | AOM.0500   | Internal server error.                         | Contact technical support.                      |
   +------------+------------------------------------------------+-------------------------------------------------+
