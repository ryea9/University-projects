# vSwitches and Port Groups

This lab focused on the networking components within vSphere. The objectives were to understand how virtual switches (vSwitches) and port groups work, and how they can be used to manage and segment network traffic for virtual machines using VLANs.

### Key Concepts
*   **vSwitch (Standard Switch):** A virtual switch that works like a physical layer-2 Ethernet switch. It forwards traffic between VMs on the same host and links to the physical network via uplink adapters.
*   **Port Group:** A configuration template for a group of virtual ports on a vSwitch. All ports in a port group share the same settings, such as VLAN ID, security policies, and traffic shaping.
*   **VLAN (Virtual LAN):** A method of segmenting a physical network into multiple logical broadcast domains. In vSphere, VLAN tagging on a port group isolates VM traffic.

### Lab Walkthrough

1.  **Create VMs from OVF:** The lab started by deploying two new VMs from an OVF (Open Virtualization Format) file. This is a common method for deploying pre-configured appliances or VMs.

2.  **Clone a VM:** One of the newly created VMs was cloned to create an identical copy. The two cloned VMs were used to test connectivity.

3.  **Test Initial Connectivity:** The two cloned VMs were located on the same host and connected to the default "VM Network" port group. A ping test between them was successful, confirming they were in the same broadcast domain.

4.  **Create a New Port Group with a VLAN:**
    *   On the VCSA web browser, I navigated to the host's networking configuration.
    *   A new port group named **'Production'** was created on the existing `vSwitch0`.
    *   This port group was assigned a **VLAN ID of 100**.

5.  **Isolate a VM:** The network adapter of the second VM was reconfigured to connect to the new 'Production' port group.
    *   A ping test between the two VMs now failed. This is because the second VM's traffic was tagged with VLAN 100, placing it in a different broadcast domain from the first VM, which was still in the untagged default port group.

### Learning Outcomes
This lab provided a practical understanding of virtual networking. I learned how to deploy VMs from templates, create and configure port groups, and use VLANs to enforce network segmentation—a fundamental concept in network security.
