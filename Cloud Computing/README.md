# Cloud Computing Infrastructure

This repository documents the practical lab work completed for the Cloud Computing Infrastructure course. The labs provided hands-on experience with VMware vSphere, a leading virtualization platform, and covered the core components of building and managing a private cloud environment.

The projects demonstrate a progressive understanding of virtualization, starting with the basics of ESXi host and virtual machine creation, and moving on to advanced topics such as shared storage, resource management, high availability, and VM migration.

## Summary of Weekly Labs

Below is a summary of the labs completed, each with a link to a detailed project report.

*   **[Week 2: VMware ESXi and VM Creation](./Week2_Lab/README.md)**
    *   **Description:** This lab focused on the initial setup of the VMware environment. It involved verifying access to pre-configured virtual machines, configuring the management network for two ESXi hosts, and creating a new ESXi host from an ISO installer.

*   **[Week 3: iSCSI Storage (VMFS) on ESXi](./Week3_Lab/README.md)**
    *   **Description:** This lab covered the fundamentals of network-based storage in a virtual environment. The key objective was to connect the ESXi hosts to an existing iSCSI target and create a shared VMFS datastore.

*   **[Week 4: vCenter Server and VM Migration](./Week4_Lab/README.md)**
    *   **Description:** This lab introduced the vCenter Server Appliance (VCSA) for centralized management. Key tasks included connecting ESXi hosts to vCenter, licensing the environment, and performing both Storage vMotion and live vMotion migrations of a running virtual machine.

*   **[Week 5: vSwitches and Port Groups](./Week5_Lab/README.md)**
    *   **Description:** This lab focused on virtual networking. It involved creating VMs from OVF/OVA files, configuring virtual switches (vSwitches), and using port groups and VLANs to segment network traffic and manage VM connectivity.

*   **[Week 6: Resource Pools and CPU Workload Management](./Week6_Lab/README.md)**
    *   **Description:** This lab explored resource management in vSphere. The main tasks were to create resource pools with different share and limit values and to observe the impact on VM performance by running a CPU-intensive script.

*   **[Week 7: Clusters, High Availability (HA), and DRS](./Week7_Lab/README.md)**
    *   **Description:** This lab covered two critical vSphere features: Distributed Resource Scheduler (DRS) and High Availability (HA). The lab involved creating a vSphere cluster, enabling HA to ensure automatic VM failover, and observing the results of a simulated host failure.

*   **[Week 8: ESXi Installation and Host Profiles](./Week8_Lab/README.md)**
    *   **Description:** This lab focused on infrastructure scalability and consistency. It involved adding a new ESXi host to the existing vCenter cluster and using Host Profiles to create a standardized configuration template for uniform host deployment.
