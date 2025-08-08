# Lab 7 - Clusters, High Availability (HA), and DRS

This lab covered two of the most important features of a vSphere cluster: High Availability (HA) and Distributed Resource Scheduler (DRS). The objective was to create a cluster, enable HA, and simulate a host failure to observe the automatic failover of virtual machines.

### Key Concepts
*   **vSphere Cluster:** A group of ESXi hosts that are managed as a single entity. Creating a cluster aggregates the resources of all hosts and enables features like HA and DRS.
*   **High Availability (HA):** A cluster feature that provides automatic failover for VMs. If an ESXi host in the cluster fails, HA will automatically restart the VMs that were running on it on other available hosts in the cluster.
*   **Distributed Resource Scheduler (DRS):** A cluster feature that provides automated load balancing. DRS monitors the CPU and memory usage across all hosts in a cluster and can automatically migrate VMs (using vMotion) to balance the load.

### Lab Walkthrough

1.  **Create a Cluster:** A new cluster object was created in the vCenter datacenter. Both `ESXi01` and `ESXi02` were moved into this cluster, pooling their resources.

2.  **Enable High Availability (HA):**
    *   The HA feature was enabled in the cluster's settings.
    *   During the configuration, vCenter agents were installed on each host, and an election process took place to designate one host as the **Master** and the other as the **Slave**. The Master host is responsible for monitoring the health of the slave hosts and initiating VM failovers.

3.  **Simulate a Host Failure:**
    *   A VM was running on the Slave host (`ESXi02`).
    *   To simulate a failure, the Slave host was abruptly powered off directly from VMware Workstation.

4.  **Observe HA Failover:**
    *   In the vCenter client, the Slave host was shortly reported as disconnected.
    *   vSphere HA detected the failure.
    *   HA automatically initiated a restart of the VM that was on the failed host. The VM was powered back on, running on the Master host (`ESXi01`).

5.  **Troubleshoot HA Errors:** A common warning message regarding "vSphere HA heartbeat datastores" appeared. This was resolved by ensuring the Default Gateway was correctly configured on the management network of both ESXi hosts, allowing them to communicate with the isolation address.

### Learning Outcomes
This lab was a powerful demonstration of the resilience offered by vSphere HA. I learned how to create a cluster, configure HA, and witnessed the automatic recovery of a virtual machine after a host failure. This solidified my understanding of how virtualization provides business continuity.
