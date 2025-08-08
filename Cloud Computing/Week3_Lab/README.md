# Lab 3 - iSCSI Storage (VMFS) on ESXi

This lab focused on configuring shared storage for the ESXi hosts. The goal was to connect the hosts to an iSCSI storage area network (SAN) and create a shared datastore, which is a prerequisite for advanced vSphere features like vMotion and High Availability.

### Key Concepts
*   **iSCSI (Internet Small Computer System Interface):** A storage networking protocol that allows block-level storage data to be transported over standard TCP/IP networks. It enables the creation of affordable Storage Area Networks (SANs).
*   **VMFS (Virtual Machine File System):** A high-performance, clustered file system from VMware that is specifically designed for storing virtual machines. A key feature of VMFS is that it allows multiple ESXi hosts to read and write to the same shared storage device simultaneously.
*   **Datastore:** A logical storage unit that virtual machines use. In vSphere, a datastore represents a formatted storage volume (like VMFS) on a local disk, iSCSI LUN, or Fibre Channel LUN.

### Lab Walkthrough

1.  **Prepare the Lab:** The lab began by ensuring the `ESXi01`, `ESXi02`, and `iSCSI` VMs were powered on. The `iSCSI` VM was pre-configured to act as a storage provider (target), and its IP address was set to `172.20.20.50`.

2.  **Configure iSCSI Connectivity on Hosts:**
    *   For each ESXi host (`ESXi01` and `ESXi02`), I logged into the web client.
    *   I navigated to **Storage > Adapters > Software iSCSI**.
    *   The IP address of the iSCSI target (`172.20.20.50`) was added to the **Dynamic targets** section.
    *   A rescan of the storage adapter was performed. After the rescan, the `FreeNAS iSCSI Disk` became visible under the **Devices** tab, confirming the host could see the storage LUN.

3.  **Create a Shared VMFS Datastore:**
    *   On `ESXi01`, I navigated to **Storage > Datastores** and selected the **New datastore** option.
    *   The "Create new VMFS datastore" wizard was launched.
    *   The newly discovered `FreeNAS iSCSI Disk` was selected as the backing device for the new datastore.
    *   The datastore was named `YourName-vmfs1` and formatted with the VMFS file system.

4.  **Verify Shared Access:**
    *   After creating the datastore on `ESXi01`, the crucial final step was to verify that it was accessible from `ESXi02`.
    *   By logging into the `ESXi02` web client and navigating to the **Storage** section, the new `YourName-vmfs1` datastore was automatically visible. This confirmed that both hosts had concurrent read/write access to the same shared storage, successfully creating a clustered storage environment.

### Learning Outcomes
This lab provided critical, hands-on experience in configuring a software iSCSI initiator on an ESXi host. I learned how to connect hosts to a network-based storage device and how to create a shared VMFS datastore. This lab established the foundational storage architecture required for almost all advanced vSphere features, including vMotion, High Availability, and DRS.
