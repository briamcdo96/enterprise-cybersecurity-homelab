# Lab 005 - Linux Infrastructure

## Objective

Deploy an Ubuntu Server 26.04 LTS virtual machine to serve as the enterprise Linux infrastructure server within the Active Directory lab environment.

Configure enterprise-standard virtual hardware, assign a static IPv4 address, install OpenSSH Server, install VMware integration tools, validate network connectivity, and prepare the server for future enterprise services and offensive security labs.

---

## Environment

| Component | Configuration |
|-----------|---------------|
| VM Name | LINUX01 |
| Operating System | Ubuntu Server 26.04 LTS |
| Hostname | linux01 |
| Network | VMnet2 (Host-only) |
| Static IP | 10.10.10.20/24 |
| DNS Server | 10.10.10.10 |
| Domain | lab.local |

---

## VM Hardware Specifications

| Component | Configuration |
|-----------|---------------|
| Hardware Compatibility | VMware Workstation 25H2 or later |
| Guest OS | Ubuntu Linux 64-bit |
| Firmware | UEFI |
| Processors | 2 |
| Cores per Processor | 2 |
| Memory | 4096 MB |
| Network Adapter | VMnet2 (Host-only) |
| I/O Controller | LSI Logic |
| Disk Type | SCSI |
| Virtual Disk | 60 GB (Single File) |

---

## Technologies Used

- VMware Workstation Pro
- Ubuntu Server 26.04 LTS
- OpenSSH Server
- Netplan
- Logical Volume Manager (LVM)
- Open VM Tools
- Git
- Curl
- Wget
- DNS Utilities

---

## Server Configuration

### Installation

- Ubuntu Server (Standard Installation)
- Ubuntu Pro skipped
- OpenSSH Server installed
- Password authentication enabled
- No SSH keys imported

### Networking

- Static IPv4 configured
- DHCP disabled
- IPv6 disabled
- VMnet2 Host-only network
- Temporary VMnet8 NAT adapter used for package installation

### Storage

- Guided storage layout
- Logical Volume Manager (LVM)
- ext4 filesystem
- Separate `/boot` partition
- Root filesystem deployed on LVM
- Additional LVM space reserved for future expansion

### Installed Packages

- open-vm-tools
- curl
- wget
- net-tools
- dnsutils
- vim
- git
- tree
- htop

### Security

- OpenSSH Server enabled
- Password authentication enabled
- Ubuntu Pro disabled
- Isolated Host-only enterprise network

---

## Current Status

- [x] Ubuntu Server installed
- [x] Static IPv4 configured
- [x] OpenSSH Server installed
- [x] VMware Tools installed
- [x] Administrative packages installed
- [x] Network connectivity verified
- [x] Linux orientation completed
- [x] Baseline snapshot created

---

## Build Log

| Date & Time | Activity |
|-------------|----------|
| 2026-07-06 21:18 | Created the LINUX01 virtual machine. |
| 2026-07-06 21:25 | Configured virtual machine hardware. |
| 2026-07-06 21:39 | Installed Ubuntu Server 26.04 LTS. |
| 2026-07-06 21:48 | Configured static IPv4 networking. |
| 2026-07-06 21:56 | Configured Logical Volume Manager storage. |
| 2026-07-06 22:03 | Installed OpenSSH Server. |
| 2026-07-06 22:18 | Completed Ubuntu installation. |
| 2026-07-06 22:31 | Logged into Ubuntu Server for the first time. |
| 2026-07-06 22:36 | Created baseline VMware snapshot. |
| 2026-07-07 | Added temporary Internet access for package installation. |
| 2026-07-07 | Installed Open VM Tools and administrative utilities. |
| 2026-07-07 | Verified hostname, networking, SSH, VMware Tools, and installed packages. |
| 2026-07-07 | Validated connectivity to DC01 and CLIENT01. |
| 2026-07-07 | Completed Linux orientation and basic administrative commands. |

---

## Validation

| Validation | Command | Result |
|------------|---------|--------|
| Hostname | `hostnamectl` | Verified hostname and Ubuntu version |
| Network | `ip addr` | Verified static IPv4 configuration |
| Routing | `ip route` | Verified routing table |
| Netplan | `cat /etc/netplan/*.yaml` | Verified network configuration |
| SSH | `systemctl status ssh` | SSH service active |
| VMware Tools | `systemctl status open-vm-tools` | VMware Tools active |
| Package Repository | `sudo apt update` | Repository verified |
| Package Status | `sudo apt list --upgradable` | Update status verified |
| Connectivity | `ping -c 4 10.10.10.10` | Successfully reached DC01 |
| Connectivity | `ping -c 4 10.10.10.100` | Successfully reached CLIENT01 |

---

## Issues Encountered

### DNS Configuration During Installation

**Issue**

Ubuntu Server did not retain the configured DNS Name Server during installation.

**Resolution**

Verified and corrected the DNS configuration after installation using Netplan.

---

### Network Connectivity Validation

**Issue**

Initial ping tests failed during validation.

**Resolution**

Determined the target virtual machines were powered off. After powering on DC01 and CLIENT01, connectivity testing completed successfully.

---

## Observations

- Ubuntu Server installation relies heavily on terminal-based administration compared to Windows Server.
- CIDR notation is used instead of traditional subnet masks.
- Ubuntu automatically configures storage using Logical Volume Manager.
- VMware Workstation automatically selects the virtual network adapter type during VM creation.
- Installing OpenSSH Server during deployment greatly simplifies remote administration.
- A temporary NAT adapter provides Internet access while preserving the isolated enterprise network.
- Basic Linux command-line familiarity is essential before administering enterprise Linux servers.

---

## Lessons Learned

- Linux networking uses CIDR notation (e.g., `10.10.10.20/24`) rather than traditional subnet masks.
- Ubuntu Server may not preserve DNS entries during installation, requiring post-install verification through Netplan.
- Enterprise Linux servers should use static IP addressing.
- OpenSSH Server should be installed during deployment to support remote administration.
- Logical Volume Manager simplifies future storage expansion.
- VMware automatically selects the appropriate virtual network adapter type.
- Package installation may require temporary Internet access during initial deployment.
- Connectivity testing requires all target systems to be powered on.

---

## Security Relevance

LINUX01 expands the enterprise lab by introducing a Linux server platform that will support future administration and offensive security exercises.

Future attack surfaces include:

- SSH
- Linux user and group management
- File permissions
- Web services
- Samba
- Scheduled tasks (Cron)
- System logging
- Service hardening and misconfiguration analysis

This lab establishes the Linux infrastructure but does not include offensive security testing.

---

## Skills Demonstrated

- Ubuntu Server Administration
- Linux Networking
- Netplan Configuration
- Static IPv4 Configuration
- OpenSSH Administration
- VMware Workstation Administration
- Logical Volume Manager (LVM)
- Linux Package Management
- Enterprise Infrastructure Deployment
- Infrastructure Validation
- Technical Documentation

---

## Next Lab

**Lab 006 - Offensive Security Workstation**

Deploy a dedicated penetration testing workstation, install offensive security tools, configure networking, and prepare the environment for attack simulations against the enterprise lab.
