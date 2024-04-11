:original_name: aom_06_0010.html

.. _aom_06_0010:

Cluster Metrics and Dimensions
==============================

.. note::

   Cluster metrics are aggregated by AOM based on host metrics, and do not include the metrics of master nodes.

.. table:: **Table 1** Cluster metrics

   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Metric                                                               | Description                                                            | Value Range | Unit   |
   +======================================================================+========================================================================+=============+========+
   | Total CPU cores (aom_cluster_cpu_limit_core)                         | Total number of CPU cores that have been applied for a measured object | >= 1        | Cores  |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Used CPU cores (aom_cluster_cpu_used_core)                           | Number of CPU cores used by a measured object                          | >= 0        | Cores  |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | CPU usage (aom_cluster_cpu_usage)                                    | CPU usage of a measured object                                         | 0-100       | %      |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Available disk space (aom_cluster_disk_available_capacity_megabytes) | Disk space that has not been used                                      | >= 0        | MB     |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Total disk space (aom_cluster_disk_capacity_megabytes)               | Total disk space                                                       | >= 0        | MB     |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Disk usage (aom_cluster_disk_usage)                                  | Percentage of the used disk space to the total disk space              | 0-100       | %      |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Available physical memory (aom_cluster_memory_free_megabytes)        | Available physical memory of a measured object                         | >= 0        | MB     |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Available virtual memory (aom_cluster_virtual_memory_free_megabytes) | Available virtual memory of a measured object                          | >= 0        | MB     |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Available GPU memory (aom_cluster_gpu_memory_free_megabytes)         | Available GPU memory of a measured object                              | > 0         | MB     |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | GPU memory usage (aom_cluster_gpu_memory_usage)                      | Percentage of the used GPU memory to the total GPU memory              | 0-100       | %      |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Used GPU memory (aom_cluster_gpu_memory_used_megabytes)              | GPU memory used by a measured object                                   | >= 0        | MB     |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | GPU usage (aom_cluster_gpu_usage)                                    | GPU usage of a measured object                                         | 0-100       | %      |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Physical memory usage (aom_cluster_memory_usage)                     | Percentage of the used physical memory to the total physical memory    | 0-100       | %      |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Downlink rate (BPS) (aom_cluster_network_receive_bytes)              | Inbound traffic rate of a measured object                              | >= 0        | Byte/s |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Uplink rate (BPS) (aom_cluster_network_transmit_bytes)               | Outbound traffic rate of a measured object                             | >= 0        | Byte/s |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Total physical memory (aom_cluster_memory_total_megabyte)            | Total physical memory that has been applied for a measured object      | >= 0        | MB     |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Total virtual memory (aom_cluster_virtual_memory_total_megabytes)    | Total virtual memory that has been applied for a measured object       | >= 0        | MB     |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+
   | Virtual memory usage (aom_cluster_virtual_memory_usage)              | Percentage of the used virtual memory to the total virtual memory      | 0-100       | %      |
   +----------------------------------------------------------------------+------------------------------------------------------------------------+-------------+--------+

.. table:: **Table 2** Dimensions of cluster metrics

   =========== ============
   Dimension   Description
   =========== ============
   clusterId   Cluster ID
   clusterName Cluster name
   projectId   Project ID
   =========== ============
