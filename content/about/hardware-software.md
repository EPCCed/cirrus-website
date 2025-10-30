---
layout: single
title: Cirrus Hardware and Software
summary:
---

- [New HPE Cray EX4000 System](#new-hpe-cray-ex4000-system)
- [Current SGI ICE XA System](#current-sgi-ice-xa-system)

## New HPE Cray EX4000 System

A new Cirrus system based will be installed in Q4 2025 to replace the end-of-life components that will be
retired once the new system is up and running.

### Hardware 

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

### Software 

All user-facing nodes will run HPE Cray Supercomputing Services Software (based on RHEL). Base compilers
and numerical/IO libraries and software development tools will be provided by the HPE Cray Programming
Environment (CPE) which supports Cray Compiling Environment (CCE), GNU Compiler Collection (GCC) and
AMD Optimizing Compiler Collection (AOCC). The new service will use the Slurm scheduler to control
access to compute resources. 

## Current SGI ICE XA System

The current Cirrus compute provision consists of 282 compute nodes connected
together by a single Infiniband fabric. 280 of these are standard 
compute nodes and 2 of these contain 4 GPU accelerators.

Cirrus Phase II saw the addition of 36 HPE Plainfield Blades each with two Intel 
Xeon processors and four NVIDIA v100 GPUs. A 512 TB (raw) of NVMe fast storage for 
data-intensive applications on Cirrus was also added. 

There are 3 login nodes that share a common software environment and
file system with the compute nodes. In addition, there are 4 Intel Xeon 8280L in the backend with 3TB of RAM
available as a fraction or as a whole node.  There is a max of 2 jobs submitted and only 1 running per user.

### Compute Nodes

#### CPU compute nodes

Cirrus standard compute nodes each contain two 2.1 GHz, 18-core Intel Xeon
E5-2695 (Broadwell) series processors. Each of the cores in these
processors support 2 hardware threads (Hyperthreads), which are enabled
by default.

The standard compute nodes on Cirrus have 256 GB of memory shared between the two
processors. The memory is arranged in a non-uniform access (NUMA) form:
each 18-core processor is a single NUMA region with local memory of 128
GB. Access to the local memory by cores within a NUMA region has a lower
latency and higher bandwidth than accessing memory on the other NUMA region.

There are three levels of cache, configured as follows:

-   L1 Cache 32 KiB Instr., 32 KiB Data (per core)
-   L2 Cache 256 KiB (per core)
-   L3 Cache 45 MiB (shared)

There are 280 standard compute nodes on Cirrus giving a total of 10,080 cores.
When employing hyperthreads, the core count doubles to 20,160.

#### GPU compute nodes

The Cirrus Phase II GPU nodes added 36 GPU compute nodes which each contain two 2.5 GHz, 
20-core Intel Xeon Gold 6148 (Cascade Lake) series processors. Each of the cores in these 
processors support 2 hardware threads (Hyperthreads), which are enabled by default. 
The nodes also each contain four NVIDIA Tesla V100-SXM2-16GB (Volta) GPU accelerators connected 
to the host processors and each other via PCIe. These GPU compute nodes provide a total of 144 
GPU accelerators and 1440 CPU cores.

There are also two Cirrus GPU compute nodes which each contain two 2.4 GHz, 20-core Intel 
Xeon Gold 6248 (Skylake) series processors. Each of the cores in these processors support 
2 hardware threads (Hyperthreads), which are enabled by default. The nodes also each contain 
four NVIDIA Tesla V100-SXM2-16GB (Volta) GPU accelerators connected to the host processors and
each other via PCIe. These GPU compute nodes provide a total of 8 GPU accelerators and 80
CPU cores.

All of the GPU compute nodes on Cirrus have 384 GB of main memory shared between the two 
processors. The memory is arranged in a non-uniform access (NUMA) form: 
each 20-core processor is a single NUMA region with local memory of 192
GB. Access to the local memory by cores within a NUMA region has a lower
latency and higher bandwidth than accessing memory on the other NUMA region.

There are three levels of cache, configured as follows:

-   L1 Cache 32 KiB Instr., 32 KiB Data (per core)
-   L2 Cache 1 MiB (per core)
-   L3 Cache 27.5 MiB (shared)

Each GPU accelerator has 16 GiB of fast GPU memory.

### Infiniband fabric

The system has a single infiniband (IB) fabric and every compute node
and login node has a single ib0 interface. The IB interface is FDR, with
a bandwidth of 54.5 Gb/s. The Lustre servers have two connections to the
IB fabric and all Lustre file system IO traverses the IB fabric.

### File systems and Data Infrastructure

There are a number of file systems available on Cirrus:

* 1 PB Ceph distributed file system for critical data storage. Mounted on all login nodes. Backed up.
* 1 PB HPE E1000 ClusterStor Lustre parallel file system provides
  high performance data access with high capacity. Mounted on all login and compute nodes. Not backed up.
* 233 TiB HPE high performance solid state storage. Mounted on all login and compute nodes. Not backed up.

The compute nodes are diskless. Each node boots from a cluster management node called the Rack Leader and NFS mounts the root file
system from this management node.

### Software

#### Operating System

Cirrus login and compute nodes run the CentOS 8 Linux operating system.

#### Research Software

The Cirrus Service includes a number of centrally installed research software
packages maintained by EPCC staff and other experts.

A list of this software with details of how to access it and run jobs (including
example job submission scripts) is available in the online documentation, see:

* [Cirrus Online Documentation](http://docs.cirrus.ac.uk)

We also record instructions for compiling many packages on Cirrus that users may
find useful in a GitHub repository, see:

* [GitHub: Package Build Instructions](https://github.com/hpc-uk/build-instructions)

#### Application Development Environment

The application development environment includes a number of different compilers,
parallel programming models, numerical/IO libraries, debuggers and profiling tools.
In short:

* Compilers - GNU, Intel, NVIDIA
* Parallel Programming Models - MPI, OpenMP, SYCL, CUDA, OpenACC
* Libraries - BLAS, LAPACK, BLACS, ScaLAPACK, FFTW, and more

For more information see the [Cirrus Online Documentation](http://docs.cirrus.ac.uk).

#### Job Submission System

Cirrus uses the Slurm job submission system. More information on running jobs on
Cirrus and Slurm options can be found in the [Cirrus Online Documentation](http://docs.cirrus.ac.uk).




