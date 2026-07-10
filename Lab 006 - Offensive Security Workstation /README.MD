# Lab 006 - Offensive Security Workstation

## Objective

Deploy a Kali Linux virtual machine to serve as the dedicated offensive security workstation within the Enterprise Cyber Lab.

Configure enterprise-standard virtual hardware, install Kali Linux using Logical Volume Manager (LVM), install VMware integration tools, update the operating system, configure static networking, validate connectivity, and prepare the workstation for future penetration testing, Active Directory security assessments, and red team exercises.

---

## Environment

| Component | Configuration |
|-----------|---------------|
| VM Name | KALI01 |
| Operating System | Kali Linux |
| Hostname | kali01 |
| Network | VMnet2 (Host-only) |
| Static IP | 10.10.10.30/24 |
| DNS Server | 10.10.10.10 |
| Domain | lab.local |

---

## VM Hardware Specifications

| Component | Configuration |
|-----------|---------------|
| Hardware Compatibility | VMware Workstation 25H2 or later |
| Guest OS | Kali Linux (Debian 64-bit) |
| Firmware | UEFI |
| Processors | 2 |
| Cores per Processor | 4 |
| Memory | 8192 MB |
| Network Adapter | VMnet2 (Host-only) |
| I/O Controller | LSI Logic |
| Disk Type | SCSI |
| Virtual Disk | 80 GB (Single File) |

---

## Technologies Used

- VMware Workstation Pro
- Kali Linux
- Open VM Tools Desktop
- OpenSSH
- Git
- Python 3
- Curl
- Nmap
- Linux Package Manager (APT)

---

## Workstation Configuration

### Installation

- Kali Linux Installer
- Guided Partitioning
- Logical Volume Manager (LVM)
- Single Partition Layout
- GRUB installed to `/dev/sda`

### Networking

- Static IPv4 Configuration
- VMnet2 Host-only Network
- Temporary VMnet8 NAT Adapter for updates
- DNS configured

### System Updates

```bash
sudo apt update
sudo apt full-upgrade -y
sudo apt autoremove -y
```

### VMware Integration

- open-vm-tools-desktop installed
- Copy / Paste enabled
- Dynamic display resizing enabled

### Git Configuration

- Global username configured
- Global email configured
- Workstation prepared for future GitHub integration

### Workspace Structure

```
~/Labs
~/Projects
~/Loot
~/Scripts
~/Wordlists
~/Reports
~/Screenshots
~/Tools
```

---

## Current Status

- [x] Kali Linux installed
- [x] Static IPv4 configured
- [x] Operating system fully updated
- [x] VMware Tools installed
- [x] Git configured
- [x] Offensive security workspace created
- [x] Connectivity validated
- [x] Baseline VMware snapshot created

---

## Build Log

| Date | Activity |
|------|----------|
| 2026-07-09 | Created the KALI01 virtual machine. |
| 2026-07-09 | Configured enterprise virtual hardware. |
| 2026-07-09 | Installed Kali Linux. |
| 2026-07-09 | Configured Logical Volume Manager (LVM). |
| 2026-07-09 | Installed the GRUB bootloader to `/dev/sda`. |
| 2026-07-09 | Completed operating system installation. |
| 2026-07-09 | Created VMware baseline snapshot. |
| 2026-07-09 | Updated Kali Linux packages. |
| 2026-07-09 | Installed Open VM Tools Desktop. |
| 2026-07-09 | Configured Git identity. |
| 2026-07-09 | Created the offensive security workspace directory structure. |
| 2026-07-09 | Verified VMware integration and workstation readiness. |

---

## Validation

| Validation | Command / Method | Result |
|------------|------------------|--------|
| Hostname | `hostnamectl` | Verified workstation hostname |
| VMware Tools | `systemctl status open-vm-tools` | VMware Tools service active |
| Package Repository | `sudo apt update` | Package repositories updated successfully |
| Python | `python3 --version` | Verified installation |
| Git | `git --version` | Verified installation |
| Curl | `curl --version` | Verified installation |
| SSH | `ssh -V` | Verified installation |
| Nmap | `nmap --version` | Verified installation |
| Connectivity | Ping tests | Successfully communicated with DC01, CLIENT01, and LINUX01 |

---

## Issues Encountered

### Temporary Internet Access Required

**Issue**

Internet connectivity was required to download operating system updates and VMware integration components.

**Resolution**

Temporarily connected the workstation to the VMnet8 NAT network, completed updates and package installations, then returned the workstation to the isolated VMnet2 Host-only network.

---

## Observations

- Kali Linux is intended to function as a dedicated offensive security workstation rather than an enterprise production server.
- Logical Volume Manager provides consistency with the Linux infrastructure deployed throughout the lab.
- VMware integration significantly improves usability through clipboard sharing, dynamic resolution changes, and enhanced guest performance.
- Organizing tools, reports, scripts, screenshots, and collected data into dedicated directories simplifies future penetration testing engagements.

---

## Lessons Learned

- Kali Linux can be deployed using Guided Partitioning with Logical Volume Manager (LVM), allowing future storage expansion.
- GRUB should be installed to the primary virtual disk (`/dev/sda`) rather than an individual partition.
- Kali Linux should be fully updated using:

```bash
sudo apt update
sudo apt full-upgrade -y
sudo apt autoremove -y
```

- VMware Open VM Tools Desktop enables clipboard sharing, dynamic display resizing, and improved VMware integration.
- Git user configuration identifies the author of future commits but does not connect the workstation to GitHub.
- Organizing offensive security resources into dedicated directories improves workflow during penetration testing engagements.

---

## Security Relevance

KALI01 serves as the primary offensive security workstation within the Enterprise Cyber Lab.

Future responsibilities include:

- Network Enumeration
- Service Enumeration
- Active Directory Enumeration
- Vulnerability Assessment
- Web Application Testing
- Password Attacks
- Privilege Escalation
- Lateral Movement
- Report Writing
- Purple Team Validation

No offensive security activities were performed during this lab. The objective was to establish a stable, standardized workstation that will support future penetration testing and defensive validation exercises.

---

## Skills Demonstrated

- Kali Linux Administration
- VMware Workstation Administration
- Linux Package Management
- VMware Tools Deployment
- Static IPv4 Configuration
- Git Configuration
- Linux System Validation
- Enterprise Workstation Deployment
- Offensive Security Environment Preparation
- Technical Documentation

---

## Next Lab

**Lab 007 - Vulnerable Web Application (OWASP Juice Shop)**

Deploy a vulnerable web application to provide a safe environment for learning web application security testing, vulnerability assessment, and offensive security techniques.
