# Lab 003 - CLIENT01

## Objective

Deploy a Windows 11 Pro workstation, perform the initial operating system configuration, assign a static IP address, and join the workstation to the **lab.local** Active Directory domain.

---

## Environment

| Component | Configuration |
|-----------|---------------|
| VM Name | CLIENT01 |
| Operating System | Windows 11 Pro 25H2 (Build 26200.8037) |
| Network | VMnet2 (Host-only) |
| Subnet | 10.10.10.100/24 |

---

## VM Hardware Specifications

| Component | Configuration |
|-----------|---------------|
| Hardware Compatibility | VMware Workstation 25H2 or later |
| Guest OS | Windows 11 x64 |
| Firmware | UEFI |
| Processors | 2 |
| Cores per Processor | 2 |
| Memory | 4096 MB |
| Network Adapter | VMnet2 (Host-only) |
| I/O Controller | LSI Logic SAS |
| Disk Type | NVMe |
| Virtual Disk | 80 GB (Single File) |

---

## Workstation Configuration

| Setting | Value |
|---------|-------|
| Hostname | CLIENT01 |
| Domain | lab.local |
| Static IP | 10.10.10.100 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | None |
| Preferred DNS | 10.10.10.10 |
| Alternate DNS | None |

---

## Current Status

- [x] Windows 11 Pro installed
- [x] Windows Updates completed
- [x] Static IP configured
- [x] Hostname configured
- [x] Joined to **lab.local**
- [x] Verified computer object exists in Active Directory
- [x] Domain Join snapshot created

---

## Build Log

| Date & Time | Activity |
|-------------|----------|
| 2026-07-04 01:40 | Created CLIENT01 virtual machine using the documented hardware specifications. |
| 2026-07-04 01:45 | Installed Windows 11 Pro. |
| 2026-07-04 01:53 | Added temporary VMnet8 adapter to provide Internet access for updates. |
| 2026-07-04 01:56 | Executed Windows Update during OOBE using the Control Update command. |
| 2026-07-04 02:02 | Configured static network settings. |
| 2026-07-04 02:25 | Created snapshot after Windows Updates and network configuration. |
| 2026-07-04 02:29 | Completed Windows 11 Out-of-Box Experience (OOBE). |
| 2026-07-04 02:31 | Renamed workstation to **CLIENT01**. |
| 2026-07-04 02:33 | Selected organization setup and configured sign-in options for domain joining. |
| 2026-07-04 02:37 | Created the initial local administrator account. |
| 2026-07-04 02:37 | Configured Windows privacy settings. |
| 2026-07-04 02:40 | Joined CLIENT01 to the **lab.local** domain using **Access work or school**. |
| 2026-07-04 02:44 | Successfully joined the Active Directory domain. |
| 2026-07-04 02:45 | Verified domain login using **LAB\\Administrator**. |
| 2026-07-04 02:46 | Created a post-domain join snapshot. |
| 2026-07-04 02:48 | Confirmed CLIENT01 appears in the Active Directory Computers container on DC01. |

---

## Issues Encountered

### Local Account Name Conflict

**Issue**

Windows does not allow a local user account to have the same name as the computer hostname.

**Resolution**

Created a different local administrator account before completing setup.

---

### Unexpected Restart During OOBE

**Issue**

The workstation restarted unexpectedly while completing the Windows Out-of-Box Experience.

**Resolution**

Allowed Windows Setup to continue after the reboot. No configuration changes were lost.

---

### Winget Unavailable During OOBE

**Issue**

The `winget upgrade --all` command was unavailable during the Out-of-Box Experience.

**Resolution**

Installed Windows Updates using the built-in Windows Update process. Application updates can be completed after initial setup.

---

## Observations

- Internet connectivity was verified by successfully pinging Google before removing the temporary NAT adapter.
- Windows Update located six cumulative updates during the initial deployment.
- Two additional updates became available after the first reboot.
- Completing Windows Updates before joining the domain reduced the number of post-deployment updates required.

---

## Lessons Learned

- Windows 11 local account names cannot match the workstation hostname.
- The `winget` package manager is not fully available during the Windows Out-of-Box Experience.
- Using a temporary NAT adapter simplifies downloading updates before isolating the workstation on the Host-only network.
- Creating a VM snapshot immediately after joining the domain provides an excellent recovery point before additional configuration.
- Verifying the computer object inside Active Directory confirms a successful domain join.

---

## Skills Demonstrated

- VMware Virtual Machine Deployment
- Windows 11 Administration
- Active Directory Domain Join
- Static IP Configuration
- Windows Networking
- DNS Client Configuration
- Windows Update Management
- Enterprise Workstation Deployment
- Infrastructure Documentation

---

## Next Lab

**Lab 004 - Active Directory Administration**

Create Organizational Units (OUs), users, security groups, and begin implementing Group Policy Objects (GPOs) to centrally manage the domain environment.
