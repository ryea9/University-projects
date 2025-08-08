# Lab 6 - Resource Pools and CPU Workload Management

This lab explored the resource management capabilities of VMware vSphere. The objective was to use resource pools to control the allocation of CPU resources to virtual machines and to observe how these settings impact VM performance under load.

### Key Concepts
*   **Resource Pool:** A logical abstraction of a host's or cluster's physical resources (CPU and memory). Resource pools can be used to delegate control over resources and to partition them among different groups of VMs.
*   **Shares:** A value (High, Normal, Low, or Custom) that specifies the relative priority or importance of a resource pool or VM. When there is resource contention, VMs with more shares get a larger portion of the physical resources.
*   **Limit:** A hard cap on the amount of CPU or memory a VM can consume, specified in MHz or MB.

### Lab Walkthrough

1.  **Create Resource Pools:**
    *   Two resource pools were created on a single ESXi host:
        *   **'Fast'**: Configured with **High** CPU shares.
        *   **'Slow'**: Configured with **Low** CPU shares and a **500Mhz CPU limit**.
    *   One VM was placed into each resource pool.

2.  **Observe Performance with a CPU Limit:**
    *   A CPU-intensive script (`cpubusy.sh`) was run inside both VMs simultaneously.
    *   The script took significantly longer to complete in the VM inside the 'Slow' pool due to the 500Mhz limit, which acted as a hard performance ceiling.

3.  **Observe Performance with Shares:**
    *   The CPU limit on the 'Slow' pool was removed, leaving only the share values (Low vs. High) as the differentiator.
    *   The `cpubusy.sh` script was run again.
    *   This time, the VM in the 'Fast' pool completed the script much faster because it was allocated a greater proportion of the host's CPU cycles due to its higher share value. This demonstrated how shares only come into play during periods of resource contention.

4.  **Force CPU Competition:** To ensure both VMs were competing for the same physical CPU core, **Scheduling Affinity** was configured to lock both VMs to `CPU0`. This made the effects of resource pool shares even more pronounced.

### Learning Outcomes
This lab provided valuable insight into vSphere resource controls. I learned the difference between setting hard limits and using flexible shares to manage performance. I now understand how to use resource pools to prioritize critical VMs and ensure they receive adequate resources during periods of high demand.
