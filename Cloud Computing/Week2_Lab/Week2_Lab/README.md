# Week 2 Lab: VMware ESXi and VM Creation

This lab provided a foundational understanding of the VMware vSphere environment. The primary goals were to ensure the lab environment was correctly set up, perform initial network configurations on ESXi hosts, and build a new ESXi host as a virtual machine.

### Key Concepts
*   **VMware ESXi:** A bare-metal hypervisor that installs directly onto a physical server, allowing it to be partitioned into multiple virtual machines.
*   **VMware Workstation:** A desktop hypervisor used here to run the nested ESXi hosts and other lab components.
*   **Management Network:** A dedicated network interface on an ESXi host used for administrative access and communication with vCenter Server.

### Lab Walkthrough

1.  **Verify VM Access:** The lab began by accessing pre-configured VMs, including two ESXi hosts (`ESXi01`, `ESXi02`), a vCenter Server Appliance (`VCSA7.0`), and a FreeNAS iSCSI storage VM. This step ensured the base lab environment was functional.

2.  **Configure ESXi Management Network:**
    *   Logged into `ESXi01` and `ESXi02` via the console using the root credentials.
    *   Navigated to the "Configure Management Network" settings to assign static IP addresses:
        *   `ESXi01`: `172.20.20.51`
        *   `ESXi02`: `172.20.20.52`
    *   This step is crucial for establishing predictable network connectivity for management.

3.  **Create a New ESXi Host (`ESXi03`):**
    *   A new virtual machine was created in VMware Workstation with the following specifications: 2 vCPUs, 4GB RAM, 18GB disk, and 4 NICs.
    *   The ESXi installer ISO was attached to the VM's virtual CD/DVD drive.
    *   The VM was powered on, and the ESXi installation process was completed.
    *   After installation, the management network for `ESXi03` was configured with the static IP `172.20.20.53`.

### Learning Outcomes
This lab provided hands-on experience with the initial setup of a virtualized environment. I learned how to perform basic network configuration on ESXi hosts directly through the console and how to install ESXi as a nested hypervisor, a common practice for lab and testing environments.
