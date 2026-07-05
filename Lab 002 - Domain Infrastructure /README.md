# Lab 002 - Domain Infrastructure

## Objective

Deploy the first Windows Server 2025 virtual machine and configure it as the primary Active Directory Domain Controller for the enterprise cybersecurity home lab.

---

## Environment

| Component | Configuration |
|-----------|---------------|
| VM Name | DC01 |
| Operating System | Windows Server 2025 Standard Evaluation (Desktop Experience) |
| Network | VMnet2 (Host-only) |
| Subnet | 10.10.10.0/24 |

---

## VM Hardware Specifications

| Component | Configuration |
|-----------|---------------|
| Hardware Compatibility | VMware Workstation 25H2 or later |
| Guest OS | Windows Server 2025 |
| Firmware | UEFI |
| Processors | 2 |
| Cores per Processor | 2 |
| Memory | 6144 MB |
| Network Adapter | VMnet2 (Host-only) |
| I/O Controller | LSI Logic SAS |
| Disk Type | SCSI |
| Virtual Disk | 80 GB (Single File) |

---

## Server Configuration

| Setting | Value |
|---------|-------|
| Hostname | DC01 |
| Domain | lab.local |
| Static IP | 10.10.10.10 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | None |
| Preferred DNS | 10.10.10.10 |
| Alternate DNS | None |

---

## Planned Server Roles

- Active Directory Domain Services (AD DS)
- DNS Server
- DHCP Server (Future Lab)

---

## VM Snapshots

- Fresh Installation
- Windows Fully Updated
- Static IP Configured
- Active Directory Installed
- Domain Controller Complete

---

## Current Status

- [x] Windows Server 2025 installed
- [x] Windows fully updated
- [x] Static IP configured
- [x] Hostname configured
- [x] Active Directory Domain Services installed
- [x] DNS Server installed
- [x] Domain Controller promoted
- [x] Post-installation snapshot created

---

## Build Log

| Date & Time | Activity |
|-------------|----------|
| 2026-06-29 19:11 | Created Windows Server virtual machine. |
| 2026-06-29 19:29 | Reinstalled Windows Server after rebuilding the VM. |
| 2026-06-29 19:48 | Rebuilt VM using custom hardware configuration. |
| 2026-06-29 19:49 | Updated VM boot configuration to use Windows Server installation media. |
| 2026-06-29 19:51 | Booted into Windows Server installation. |
| 2026-06-29 19:57 | Completed Windows installation and reached Administrator setup. |
| 2026-06-29 20:02 | Created local Administrator account. |
| 2026-06-29 20:31 | Added temporary VMnet8 adapter to provide Internet access. |
| 2026-06-29 20:32 | Executed `winget upgrade --all`. |
| 2026-06-29 20:37 | Restarted server after updates. |
| 2026-06-29 20:39 | Installed additional Windows Updates. |
| 2026-06-29 20:55 | Windows Updates completed successfully. |
| 2026-06-29 21:00 | Removed temporary VMnet8 adapter. |
| 2026-06-29 21:00 | Configured static IP address. |
| 2026-06-29 21:02 | Renamed server to **DC01**. |
| 2026-06-29 21:03 | Created snapshot after network configuration. |
| 2026-07-04 00:10 | Verified hostname and network configuration. |
| 2026-07-04 00:11 | Installed Active Directory Domain Services and DNS Server roles. |
| 2026-07-04 00:12 | Completed Domain Controller promotion and restarted server. |
| 2026-07-04 00:54 | Verified Domain Controller deployment and created final snapshot. |

---

## Issues Encountered

### Windows Installation Boot Loop

**Issue**

During Windows installation, the virtual machine repeatedly attempted to boot from the installation media instead of the virtual hard disk.

**Resolution**

Reconfigured the VM boot order and rebuilt the virtual machine using custom hardware settings.

---

### Frozen Installation

**Issue**

The Windows installation became unresponsive and remained on a black screen.

**Resolution**

Deleted the virtual machine and recreated it from scratch since no production data had been stored.

---

### Incorrect Subnet Mask

**Issue**

The subnet mask was initially configured as **255.0.0.0**.

**Resolution**

Updated the configuration to **255.255.255.0** to match the **10.10.10.0/24** lab network.

---

## Observations

- Windows Server required multiple cumulative updates immediately after installation.
- A temporary NAT adapter simplified downloading updates before isolating the server on the Host-only network.
- Active Directory Domain Services automatically installs several prerequisite components during deployment.
- Multiple VM snapshots significantly reduced recovery time while building the environment.

---

## Lessons Learned

- LDAP stands for **Lightweight Directory Access Protocol**.
- `winget upgrade --all` installs application updates but does not replace Windows Update.
- Building virtual machines using **Custom Configuration** provides greater flexibility than the default wizard.
- Rebuilding a virtual machine is often faster than troubleshooting installation issues during the initial deployment phase when no data has been created.
- Creating snapshots before major configuration changes provides reliable recovery points.

---

## Skills Demonstrated

- VMware Virtual Machine Deployment
- Windows Server 2025 Administration
- Active Directory Domain Services
- DNS Server Configuration
- Static IP Configuration
- Enterprise Server Deployment
- Windows Update Management
- Infrastructure Documentation

---

## Next Lab

**Lab 003 - Active Directory Administration**

Deploy organizational units, user accounts, security groups, and begin configuring enterprise Active Directory management.
