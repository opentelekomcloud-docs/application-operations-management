:original_name: aom_03_0025.html

.. _aom_03_0025:

Why Are Connection Channels Required?
=====================================

Different Virtual Private Clouds (VPCs) cannot communicate with each other. To solve this problem, create an application in the VPC where the data subscription application resides and set it to a VPC endpoint service. Then, create a VPC endpoint in the VPC where Distributed Message Service (DMS) resides. A connection channel can be established between the VPC endpoint and VPC endpoint service for communication.
