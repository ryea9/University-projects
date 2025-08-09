# vCenter Server and VM Migration

This lab introduced the VMware vCenter Server Appliance (VCSA), a crucial component for centralized management of a vSphere environment. The main objectives were to connect the existing ESXi hosts to vCenter and to perform live migrations of virtual machines using vMotion and Storage vMotion.

### Key Concepts
*   **vCenter Server:** A management platform that acts as a central control point for ESXi hosts and their virtual machines. It is required for advanced vSphere features.
*   **vMotion:** Enables the live migration of a running virtual machine from one ESXi host to another with zero downtime. The VM's memory and execution state are transferred over the network.
*   **Storage vMotion:** Enables the migration of a virtual machine's files from one datastore to another while the VM is running, without any service interruption.

### Lab Walkthrough

1.  **Connect to vCenter Server:** The lab started by connecting to the VCSA management portal. The ESXi hosts (`ESXi01` and `ESXi02`) were then added to the vCenter inventory, bringing them under centralized management.

2.  **Verify Licensing:** The licensing for both the vCenter Server and the ESXi hosts was managed through the vCenter interface. This step is necessary to enable enterprise-level features.

3.  **Migrate VM with Storage vMotion:**
    *   A running VM on `ESXi02` was selected.
    *   The **Migrate** action was chosen, with the "Change storage only" option.
    *   The VM's files were moved from the local datastore on the host to the shared iSCSI datastore (`YourName-vmfs1`) created in the previous lab. This was done without shutting down the VM.

4.  **Migrate VM with vMotion:**
    *   With the VM now running from shared storage, a second migration was initiated.
    *   This time, the "Change compute resource only" option was selected.
    *   The VM was live-migrated from `ESXi02` to `ESXi01`.
    *   To make this possible, **vMotion** had to be enabled on the management network (`vmk0`) of both ESXi hosts.

### Learning Outcomes
This lab was essential for understanding the power of centralized management with vCenter. I successfully performed zero-downtime migrations, demonstrating a key benefit of a properly configured virtual infrastructure. I learned that shared storage is a hard requirement for vMotion and that a dedicated vMotion network is a best practice for performance.
