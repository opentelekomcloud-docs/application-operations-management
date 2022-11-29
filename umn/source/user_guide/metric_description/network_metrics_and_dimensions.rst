:original_name: aom_02_1016.html

.. _aom_02_1016:

Network Metrics and Dimensions
==============================

.. table:: **Table 1** Network metrics

   +---------------------------------------+----------------------------------------------------------------------+-------------+-------------------------+
   | Metric                                | Description                                                          | Value Range | Unit                    |
   +=======================================+======================================================================+=============+=========================+
   | Downlink rate (recvBytesRate)         | Inbound network traffic rate of a measured object                    | >= 0        | Byte per Second (BPS)   |
   +---------------------------------------+----------------------------------------------------------------------+-------------+-------------------------+
   | Downlink rate (recvPackRate)          | Number of data packets received by the NIC per second                | >= 0        | Packet per Second (PPS) |
   +---------------------------------------+----------------------------------------------------------------------+-------------+-------------------------+
   | Downlink error rate (recvErrPackRate) | Number of error packets received by the NIC per second               | >= 0        | PPS                     |
   +---------------------------------------+----------------------------------------------------------------------+-------------+-------------------------+
   | Uplink rate (sendBytesRate)           | Outbound network traffic rate of a measured object                   | >= 0        | BPS                     |
   +---------------------------------------+----------------------------------------------------------------------+-------------+-------------------------+
   | Uplink error rate (sendErrPackRate)   | Number of error packets sent by the NIC per second                   | >= 0        | PPS                     |
   +---------------------------------------+----------------------------------------------------------------------+-------------+-------------------------+
   | Uplink rate (sendPackRate)            | Number of data packets sent by the NIC per second                    | >= 0        | PPS                     |
   +---------------------------------------+----------------------------------------------------------------------+-------------+-------------------------+
   | Total rate (totalBytesRate)           | Total inbound and outbound network traffic rate of a measured object | >= 0        | BPS                     |
   +---------------------------------------+----------------------------------------------------------------------+-------------+-------------------------+

.. table:: **Table 2** Dimensions of network metrics

   =========== ============================
   Dimension   Description
   =========== ============================
   clusterId   Cluster ID
   clustername Cluster name
   NIC         Network interface card (NIC)
   hostID      Host ID
   hostIP      Host IP address
   nameSpace   Cluster namespace
   netDevice   NIC name
   nodeIP      Host IP address
   nodeName    Host name
   =========== ============================
