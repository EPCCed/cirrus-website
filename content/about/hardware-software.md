---
layout: single
title: Cirrus Hardware and Software
summary:
---

- [New HPE Cray EX4000 System](#new-hpe-cray-ex4000-system)
- [Historical hardware information](#historical-hardware-information)

## HPE Cray EX4000 System

### Hardware 

The Cirrus hardware is provided by an HPE Cray EX4000 system with 73,728 CPU cores in 256 compute nodes. There
are no GPU accelerators in the updated Cirrus system.

The compute nodes each have 288 cores. They are dual socket nodes with two 144-core AMD EPYC(tm) 9825
processors. There are 192 standard memory nodes and 64 high memory nodes. Standard memory nodes have
768 GB DDR5 memory, and high memory nodes have 1,536 GB DDR5 memory.

Compute nodes are connected together by a HPE Cray Slingshot 11 interconnect.

Login nodes provide interactive access via command-line (SSH) and we are also planning to provide
a web interface to the service using [Open OnDemand](https://openondemand.org/).

Storage is provided via two file systems:

* 1 PB Ceph distributed file system for critical data storage. Mounted on all login nodes (not available
  on compute nodes). Not backed up.
* 1 PB HPE E1000 ClusterStor Lustre parallel file system provides
  high performance data access with high capacity. Mounted on all login and compute nodes. Not backed up.

The default striping on the Lustre filesystem is 1 stripe, and the default stripe size is 1 MiB.

More detailed information is available in [the Hardware section of the User Guide](https://docs.cirrus.ac.uk/user-guide/hardware/).

### Software 

All user-facing nodes run HPE Cray Supercomputing Services Software (based on RHEL). Base compilers
and numerical/IO libraries and software development tools are provided by the HPE Cray Programming
Environment (CPE) which supports Cray Compiling Environment (CCE), GNU Compiler Collection (GCC) and
AMD Optimizing Compiler Collection (AOCC). The new service uses the Slurm scheduler to control
access to compute resources. 

## Historical hardware information

- [2015-2025: Cirrus SGI ICE XA](../sgi-hardware-software/)


