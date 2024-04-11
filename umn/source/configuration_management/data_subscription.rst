:original_name: aom_02_1013.html

.. _aom_02_1013:

Data Subscription
=================

AOM allows you to subscribe to metrics or alarms. After the subscription, data can be forwarded to custom Kafka or Distributed Message Service (DMS) topics for you to retrieve.

.. important::

   A maximum of 10 data subscription rules can be created.

Creating Subscription Rules
---------------------------

#. Log in to the AOM console. In the navigation pane, choose **Configuration Management** > **Data Subscription**.

#. Click **Create Subscription Rule** in the upper right corner. On the displayed page, set parameters and click **OK**.

   You can set **Subscription Target Type** to **Custom Kafka** or **DMS** as required.

   -  If **Subscription Target Type** is set to **Custom Kafka**, set parameters based on :ref:`Table 1 <aom_02_1013__en-us_topic_0270486186_table17220164915329>`.

      .. _aom_02_1013__en-us_topic_0270486186_table17220164915329:

      .. table:: **Table 1** Subscription rule parameters

         +-----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------+
         | Parameter                   | Description                                                                                                                                                         | Example                         |
         +=============================+=====================================================================================================================================================================+=================================+
         | Rule Name                   | Subscription rule name.                                                                                                                                             | Enter **aom-kafka-test**.       |
         +-----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------+
         | Subscription Content        | Options: **Metric** and **Alarm**.                                                                                                                                  | Select **Metric**.              |
         +-----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------+
         | Subscription Target Type    | Options: **Custom Kafka** and **DMS**.                                                                                                                              | Select **Custom Kafka**.        |
         +-----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------+
         | Subscription Target Address | Custom Kafka address, which needs to be connected to Internet.                                                                                                      | Set this parameter as required. |
         |                             |                                                                                                                                                                     |                                 |
         |                             | Each address must be in the format of "IPv4 address:port". If multiple addresses exist, separate them by commas (,). Example: **192.168.0.1:9092,192.168.0.2:9092** |                                 |
         +-----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------+

      a. (Optional) On the **Rule Details** page, click |image1| to enable Kafka SASL_SSL and set parameters based on :ref:`Table 2 <aom_02_1013__en-us_topic_0270486186_table17676115813360>`.

         .. note::

            AOM supports only Kafka SASL_SSL security authentication. If you have enabled Kafka SASL_SSL for instances, you also need to enable it on the **Rule Details** page.

         .. _aom_02_1013__en-us_topic_0270486186_table17676115813360:

         .. table:: **Table 2** Setting Kafka SASL_SSL parameters

            +--------------------+----------------------------------------------------------------------------------------------------------------------+---------+
            | Parameter          | Description                                                                                                          | Example |
            +====================+======================================================================================================================+=========+
            | User name          | SASL username for instance access authentication.                                                                    | demo    |
            +--------------------+----------------------------------------------------------------------------------------------------------------------+---------+
            | Password           | SASL password for instance access authentication. Keep your password secure. The system cannot detect your password. | ``-``   |
            +--------------------+----------------------------------------------------------------------------------------------------------------------+---------+
            | Client certificate | Use a client certificate in **.pem** format.                                                                         | ``-``   |
            +--------------------+----------------------------------------------------------------------------------------------------------------------+---------+

      b. Click **Verify and Save Custom Kafka Configuration** to verify the connectivity of the custom Kafka instance.

      c. Select a topic for transmitting data and click **OK**.

   -  If **Subscription Target Type** is set to **DMS**, set parameters based on :ref:`Table 3 <aom_02_1013__en-us_topic_0270486186_table132311349183212>`.

      .. _aom_02_1013__en-us_topic_0270486186_table132311349183212:

      .. table:: **Table 3** Subscription rule parameters

         +--------------------------+------------------------------------------------------------------------------------------------------+----------------------------+
         | Parameter                | Description                                                                                          | Example                    |
         +==========================+======================================================================================================+============================+
         | Rule Name                | Subscription rule name.                                                                              | Enter **aom-kafka-test**.  |
         +--------------------------+------------------------------------------------------------------------------------------------------+----------------------------+
         | Subscription Content     | Options: **Metric** and **Alarm**.                                                                   | Select **Metric**.         |
         +--------------------------+------------------------------------------------------------------------------------------------------+----------------------------+
         | Subscription Target Type | Options: **Custom Kafka** and **DMS**.                                                               | Select **DMS**.            |
         +--------------------------+------------------------------------------------------------------------------------------------------+----------------------------+
         | Instance                 | Select a DMS instance. If no DMS instance is available, click **Create DMS Instance** to create one. | Select **kafka-aom-7160**. |
         +--------------------------+------------------------------------------------------------------------------------------------------+----------------------------+

      a. On the **Rule Details** page, click **Create a network connection channel**.

      b. Verify the DMS instance connectivity.

         Ensure that an inbound rule is added to allow traffic from source IP address 198.19.128.0/20 on port 9011. To set a security group rule, do as follows:

         #. Log in to the management console.
         #. Click |image2| in the upper left corner and choose **Networking** > **Virtual Private Cloud**.
         #. In the navigation pane, choose **Access Control** > **Security Groups**. Then, locate the security group corresponding to the DMS instance and click **Manage Rule** in the **Operation** column.
         #. On the **Inbound Rules** tab page, click **Add Rule** to allow the network traffic from source IP address 198.19.128.0/20 on port 9011.

      c. Click **Verify and Save DMS Configuration Information**.

      d. Select a topic for transmitting data and click **OK**.

Data Subscription Format
------------------------

-  Metric data example (in JSON format)

   .. code-block:: text

      package metric

      type MetricDatas struct {
         Metrics   []Metrics `json:"metrics"`
         ProjectId string    `json:"project_id"`
      }

      type Metrics struct {
         Metric      Metric  `json:"metric"`
         Values      []Value `json:"values"`
         CollectTime int64   `json:"collect_time"`
      }

      type Metric struct {
         Namespace  string      `json:"namespace"`
         Dimensions []Dimension `json:"dimensions"`
      }

      type Value struct {
         Value           interface{} `json:"value"`
         Type            string      `json:"type"`
         Unit            string      `json:"unit"`
         StatisticValues string      `json:"statisticvalues"`
         MetricName      string      `json:"metric_name"`
      }

      type Dimension struct {
         Name  string `json:"name"`
         Value string `json:"value"`
      }

-  Kafka message example

   .. code-block::

      key:,
      value:{"metrics":[{"metric":{"namespace":"PAAS.NODE","dimensions":[{"name":"nodeName","value":"test-vss-cop-master-1"},{"name":"nodeIP","value":"1.1.1.1"},{"name":"hostID","value":"75d97111-4734-4c6c-ae9e-f6111111111"},{"name":"nameSpace","value":"default"},{"name":"clusterId","value":"46a7bc0d-1d8b-11ea-9b04-333333333333333"},{"name":"clusterName","value":"test-vss-111"},{"name":"diskDevice","value":"vda"},{"name":"master","value":"true"}]},"values":[{"value":0,"type":"","unit":"Kilobytes/Second","statisticvalues":"","metric_name":"diskReadRate"},{"value":30.267,"type":"","unit":"Kilobytes/Second","statisticvalues":"","metric_name":"diskWriteRate"}],"collect_time":1597821030037}],"project_id":"111111111111111111111"}

-  Alarm data format

   Example:

   .. code-block::

      {
          "events": [{
              "id": "4346299651651991683",
              "starts_at": 1597822250194,
              "ends_at": 0,
              "arrives_at": 1597822250194,
              "timeout": 300000,
              "resource_group_id": "312313123112222222222232131312131",
              "metadata": {
                  "kind": "Pod",
                  "event_severity": "Major",
                  "resource_type": "service",
                  "clusterId": "6add4ef5-1358-11ea-a5bf-111111111",
                  "event_type": "alarm",
                  "clusterName": "cce-ief-4516140c-96ca-4a5f-8d85-1111111",
                  "namespace": "PAAS.NODE",
                  "name": "test15769793809553052-f5557bd7f-qnfkm",
                  "event_name": "FailedScheduling",
                  "resource_id": "clusterName=cce-ief-4516140c-96ca-4a5f-8d85-111111;clusterID=6add4ef5-1358-11ea-a5bf-11111111111;kind=Pod;namespace=30d5758f166947c6b164af604a654b09;name=test15769793809553052-f5557bd7f-qnfkm;uid=589fc746-245d-11ea-a465-fa163e5fc15d",
                  "nameSpace": "30d5758f166947c6b164af604a654b09",
                  "resource_provider": "CCE",
                  "nodeID": "589fc746-245d-11ea-a465-fa163e5fc15d"
              },
              "annotations": {
                  "alarm_probableCause_zh_cn": "FailedScheduling",
                  "alarm_probableCause_en_us": "FailedScheduling",
                  "message": "0/110 nodes are available: 1 node(s) had taints that the pod didn't tolerate, 109 node(s) didn't match node selector."
              },
              "attach_rule": {

              }
          }],
          "project_id": "312313123112222222222232131312131"
      }

   Parameter description:

   .. table:: **Table 4** Alarm parameters

      +------------+--------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
      | Parameter  | Type                                                                                                         | Description                                                                   |
      +============+==============================================================================================================+===============================================================================+
      | events     | Array of objects. For details, see :ref:`Table 5 <aom_02_1013__en-us_topic_0270486186_table81981529165813>`. | Event or alarm details.                                                       |
      +------------+--------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
      | project_id | String                                                                                                       | Project ID obtained from IAM. Generally, a project ID contains 32 characters. |
      +------------+--------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------+

   .. _aom_02_1013__en-us_topic_0270486186_table81981529165813:

   .. table:: **Table 5** EventModel

      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                                                                                                                                      |
      +=======================+=======================+==================================================================================================================================================================================+
      | id                    | String                | Event or alarm ID, which is automatically generated by the system.                                                                                                               |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | starts_at             | Long                  | Time when an event or alarm is generated. The value is a China Standard Time (CST) timestamp precise down to the millisecond.                                                    |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | ends_at               | Long                  | Time when an event or alarm is cleared. The value is a CST timestamp precise down to the millisecond. If the value is **0**, the event or alarm is not deleted.                  |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | arrives_at            | Long                  | Time when an event or alarm reaches AOM. The value is a CST timestamp precise down to the millisecond.                                                                           |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | timeout               | Long                  | Duration (unit: ms) at which an alarm is automatically cleared. For example, if the duration is one minute, set this parameter to **60000**. The default duration is three days. |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | resource_group_id     | String                | Reserved field for a resource group. The default value is the same as the value of **projectid**.                                                                                |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | metadata              | Object                | Details of an event or alarm. The value is a key-value pair. The following fields are mandatory:                                                                                 |
      |                       |                       |                                                                                                                                                                                  |
      |                       |                       | -  **event_name**: Event or alarm name, which is a string.                                                                                                                       |
      |                       |                       | -  **event_severity**: Event severity, which is an enumerated value with the string-type attribute. Options: **Critical**, **Major**, **Minor**, and **Info**.                   |
      |                       |                       | -  **event_type**: Event type, which is an enumerated value with the string-type attribute. Options: **event** and **alarm**.                                                    |
      |                       |                       | -  **resource_provider**: Name of a cloud service corresponding to an event, which is a string.                                                                                  |
      |                       |                       | -  **resource_type**: Resource type corresponding to an event, which is a string.                                                                                                |
      |                       |                       | -  **resource_id**: Resource ID corresponding to an event, which is a string.                                                                                                    |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | annotations           | Object                | Additional field for an event or alarm, which can be left blank.                                                                                                                 |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | attach_rule           | Object                | Reserved field for an event or alarm, which can be left blank.                                                                                                                   |
      +-----------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Follow-up Operations
--------------------

After the data subscription rule is created, AOM will send data to your custom Kafka or DMS topic so that you can retrieve the subscribed metrics or alarms.

.. |image1| image:: /_static/images/en-us_image_0000001208742219.png
.. |image2| image:: /_static/images/en-us_image_0000001163348542.png
