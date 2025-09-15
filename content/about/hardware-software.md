---
layout: single
title: Cirrus Hardware and Software
summary:
---

## Hardware: HPE Cray EX4000  

New Cirrus hardware based will be installed in Q4 2025 to replace the end-of-life components that will be
retired once the new system is up and running.

The new hardware will be provided by an HPE Cray EX4000 system with 73,728 cores in 256 compute nodes. There
be no GPU accelerators in the updated Cirrus system.

The compute nodes will each have 288 cores. They are dual socket nodes with two 144-core AMD EPYC(tm) 9825
processors. There will be 192 standard memory nodes and 64 high memory nodes. Standard memory nodes have
768 GB DDR5 memory, and high memory nodes have 1,536 GB DDR5 memory.

Compute nodes will be connected together by a HPE Cray Slingshot 11 interconnect.

Login nodes will provide interactive access via command-line (SSH) and we are also planning to provide
a web interface to the service using [Open OnDemand](https://openondemand.org/).

Storage will be provided via two file systems:

* 1 PB Ceph distributed file system for critical data storage. Mounted on all login nodes (not available
  on compute nodes). Backed up.
* 1 PB HPE E1000 ClusterStor Lustre parallel file system provides
  high performance data access with high capacity. Mounted on all login and compute nodes. Not backed up.

The default striping on the Lustre filesystem is 1 stripe, and the default stripe size is 1 MiB.

## Software 

All user-facing nodes will run HPE Cray Supercomputing Services Software (based on RHEL). Base compilers
and numerical/IO libraries and software development tools will be provided by the HPE Cray Programming
Environment (CPE) which supports Cray Compiling Environment (CCE), GNU Compiler Collection (GCC) and
AMD Optimizing Compiler Collection (AOCC). The new service will use the Slurm scheduler to control
access to compute resources. 




