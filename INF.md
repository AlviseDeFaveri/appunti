# COMPUTING INFRASTRUCTURES

## Data Centers

* Cooling system (Turbo coolers, water tanks, heat exchangers)
* Battery and diesel generators as backup supply
* Corridors: made by **racks** with a **cold aisle** (front panel) and a **warm aisle** (back connectors)
* Rack modules contain
  * Servers
  * Communication equipment
  * Storage units (JBOD, RAID, NAS)
  * Power distribution units
* **Network architectures**
  * Three layers 
    * Access layer: servers
    * Aggregation: switch at the Top of each Rack (TOR, lower costs) or at the end of corridors (EOL, higher scalability)
    * Core: high speed links
    * **Equal Cost Multiple Path** equally shares traffic among routers
  * Fat tree: node divided in pods with same number of nodes and switches
    * in each pod, 2 layers of switches, each connected to half of the nodes
    * **Good** less expensive, **Bad** high number of switches
  * D cell: network of networks. Each cell can contain other cells.
    * **Good** fewer switches and less cables, **Bad** some node have to be routers -> limit performance and administration problems

* 4 tier levels, with different availability.

## VMs

* **virtualizationABI** *Application Binary Interface*: syscalls offered by OS
* **User ISA**: instruction set architecture available to application layer
* **System ISA**: instruction set available only to the OS



* **Process VM**: simulates OS and machine (ABI + User ISA)
  * same ABI: *multiprogrammed*
  * different ABI: *dynamic translators* (just-in-time-compilers, JVM)
* **System VM**: simulates ISA (guest OS on top, Host OS under)
  * Same ISA: *classic system VM* Host OS and Guest OS both for the same hardware
  * Different ISA: windows apps running on power-pc



* **Hypervisor**
  * Monolithic: drivers run in the Hypervisor
  * Microkernel: drivers run in a Service VM
  * VMM (Virtual Machine Manager): has gui to manage resources & instances -> hypervisor runs on a OS



* **Paravirtualization** guest OS & VMM collaborate (modified OS are needed)
* **Full Virtualization** complete simulation
* **Kernel Level Virtualization** virtualization happens in the OS
* **Hardware Assited Virtualization** adds a priviledge level at hardware level VMX root and VMX non-root

## VIRTUAL RESOURCES

* *Virtualization* (virtual resource has same interface of the real resource) VS *Emulation* (different interface)

* Mapping: *Aggregation* (same virtual resource has multiple real resources) vs *Sharing*

  

* **Processor**: 

  * *Emulation* (different ISA) 
  * *Direct Native Execution* (same ISA)

* **Memory**

  * *Balooning* Asks VMs for free pages
  * *Overcommit* VMM determines less used pages

* **Virtual Memory**

  * *Shadow Pages* SW, VMM keeps shadow pages table
  * *Nested pages* HW, TLB uses a NPT (nested pages table)

* **Network**

  * *NAT* VMM as Router, dispatches messages to VMs 
  * *Bridged* Each VM has an IP address
  * *Host* Only VM and hosts can talk to each other
  * *Internal* Only VM can talk to each other

## Cloud Computing

1. Application Level (SaaS - *Software as a Service*) Gmail, GDocs
2. Environment (PaaS - *Platform as a Service*) TensorFlow
3. Infrastructure
   1.  IaaS - *Infrastructure as a service* (Amazon EC2, Azure)
   2. Caas - *Communication as a service*
   3. DaaS - *Data as a Service* (Drive, Dropbox)
4. kernel
5. HaaS



* Public: rent a piece of an infrastructure
* Private: internally managed data centers
* Community: managed by a group of several organizations
* Hybrid (EC2): in normal situations private, when there is overload -> rent from a public cloud

FOG computing: IoT, edge computing