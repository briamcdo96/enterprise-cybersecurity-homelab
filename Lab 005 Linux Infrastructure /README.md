=====================================================
Lab 005 - Linux Infrastructure
=====================================================

Objective
=====================================================

Deploy an Ubuntu Server 26.04 LTS virtual machine to serve as the enterprise Linux infrastructure server within the Active Directory lab environment.

Configure enterprise-standard virtual hardware, assign a static IPv4 address, install OpenSSH Server for remote administration, install VMware integration tools, validate network connectivity, and prepare the server for future enterprise services and offensive security labs.

This server will later support Linux administration, SSH, web services, Samba, monitoring, logging, and other services that will become part of the enterprise cyber range.

=====================================================
Lessons Learned
=====================================================

2026-07-06 21:42:18 - Linux networking uses CIDR notation, such as 10.10.10.0/24, instead of the Windows-style subnet mask 255.255.255.0.

2026-07-06 21:49:33 - Ubuntu Server installer may not retain DNS Name Server entries during installation. DNS can be verified and corrected later using Netplan.

2026-07-06 22:01:17 - Enterprise Linux servers should use static IP addressing rather than DHCP.

2026-07-06 22:05:41 - OpenSSH Server enables remote Linux administration and should be installed during deployment.

2026-07-06 22:14:52 - Ubuntu Server uses Logical Volume Manager, allowing future storage expansion.

2026-07-06 22:26:14 - VMware Workstation does not expose VMXNET3 selection in the GUI. Adapter type is automatically assigned.

2026-07-07 - Temporary internet access may be required to run apt update, install packages, and install administrative tools.

2026-07-07 - Network validation requires target systems to be powered on before ping tests will succeed.

=====================================================
VM Hardware Specs
=====================================================

| Setting                | Value                                 |
| ---------------------- | ------------------------------------- |
| Hardware Compatibility | Workstation 25H2 or later             |
| Guest OS               | Ubuntu Linux 64-bit                   |
| Firmware               | UEFI                                  |
| CPU                    | 2 Processors / 2 Cores Total (2 vCPU) |
| RAM                    | 4096 MB                               |
| Network                | VMnet2 (Host-only)                    |
| Controller             | LSI Logic                             |
| Disk                   | 60 GB                                 |
| Disk Type              | SCSI                                  |
| Single File            | Yes                                   |

=====================================================
Environment
=====================================================

VM Name: LINUX01
Operating System: Ubuntu Server 26.04 LTS
Hostname: linux01
Network: VMnet2 (Host-only)
Static IPv4 Address: 10.10.10.20/24
Default Gateway: None
DNS Server: 10.10.10.10
Primary Domain: lab.local

=====================================================
Configuration
=====================================================

Installation Type
- Ubuntu Server
- Standard installation
- Ubuntu Pro skipped
- OpenSSH Server installed
- Password authentication enabled
- No SSH keys imported

Networking
- Static IPv4 configured
- IP Address: 10.10.10.20/24
- DHCP disabled on enterprise interface
- IPv6 disabled
- VMnet2 Host-only network used for lab connectivity
- Temporary VMnet8 NAT adapter used for updates/package installation if needed

Storage
- Guided storage configuration
- Logical Volume Manager enabled
- ext4 filesystem
- 60 GB virtual disk
- Separate /boot partition
- Root filesystem deployed on LVM
- Free LVM space available for future expansion

Installed Packages
- open-vm-tools
- curl
- wget
- net-tools
- dnsutils
- vim
- git
- tree
- htop

Security
- OpenSSH Server enabled
- SSH password authentication enabled for lab administration
- Ubuntu Pro not enabled
- Server remains on isolated VMnet2 enterprise network after updates

=====================================================
Build Log - Notes on actual build progress
=====================================================

2026-07-06 21:18:42 - Created LINUX01 virtual machine.
2026-07-06 21:25:19 - Configured VM hardware specifications.
2026-07-06 21:39:11 - Installed Ubuntu Server 26.04 LTS.
2026-07-06 21:48:57 - Configured static IPv4 address.
2026-07-06 21:56:48 - Configured LVM storage layout.
2026-07-06 22:03:37 - Installed OpenSSH Server.
2026-07-06 22:18:12 - Completed operating system installation.
2026-07-06 22:31:55 - Successfully logged into Ubuntu Server.
2026-07-06 22:36:40 - Created VMware baseline snapshot: "Lab 005 - Clean Install".
2026-07-07 - Added temporary internet access to install updates and packages.
2026-07-07 - Installed Open VM Tools and administrative packages.
2026-07-07 - Validated hostname, IP configuration, SSH service, VMware Tools service, and package status.
2026-07-07 - Verified connectivity with DC01 and CLIENT01 after confirming required VMs were powered on.
2026-07-07 - Completed Linux orientation commands including pwd, ls, ls -la, cd /, tree -L 1 /, cat /etc/passwd, groups, and sudo -l.

=====================================================
Validation
=====================================================

Hostname Verification
- Command: hostnamectl
- Result: Confirmed system hostname and Ubuntu Server version.

Network Verification
- Command: ip addr
- Result: Confirmed LINUX01 static IPv4 address 10.10.10.20/24.

Route Verification
- Command: ip route
- Result: Confirmed routing configuration.

DNS / Netplan Verification
- Command: cat /etc/netplan/*.yaml
- Result: Confirmed network configuration.

SSH Verification
- Command: systemctl status ssh
- Result: Confirmed SSH service is active and running.

VMware Tools Verification
- Command: systemctl status open-vm-tools
- Result: Confirmed VMware Tools service is active and running.

Connectivity Verification
- Command: ping -c 4 10.10.10.10
- Result: Confirmed connectivity to DC01.

- Command: ping -c 4 10.10.10.100
- Result: Confirmed connectivity to CLIENT01.

Package Verification
- Command: sudo apt update
- Command: sudo apt list --upgradable
- Result: Confirmed package repositories and update status.

=====================================================
Observation Log - Things noticed during build process
=====================================================

Ubuntu Server installation differs from Windows Server deployment and relies heavily on terminal-based administration.

CIDR notation is used throughout the installer instead of subnet masks.

The installer automatically configures storage using LVM and leaves available free space for future expansion.

VMware Workstation does not expose VMXNET3 selection during VM creation.

OpenSSH Server is presented during installation and should be installed for remote administration.

A temporary NAT adapter can be used for updates while keeping the enterprise interface on VMnet2.

Basic Linux orientation is useful, but Lab 005 should remain focused on infrastructure deployment rather than deep Linux administration.

=====================================================
Issues Encountered - Issues encountered during Build
=====================================================

2026-07-06 22:08:34 - Unable to retain DNS Name Server entry during IPv4 configuration. Installer cleared the Name Server field after saving. Planned to verify and correct DNS post-install using Netplan if required.

2026-07-07 - Initial ping validation failed because target VMs were powered off. Connectivity was re-tested after powering on the required systems.

=====================================================
Security Relevance
=====================================================

LINUX01 introduces Linux infrastructure into the enterprise lab.

Future attack surface may include:
- SSH
- Linux users and groups
- File permissions
- Web services
- Samba shares
- Cron jobs
- Logs
- Misconfigured services

This lab does not include exploitation. It prepares the Linux server that will later support enterprise services and offensive security exercises.

=====================================================
Next Steps
=====================================================

- Create final VMware snapshot: "Lab 005 - Complete".
- Prepare GitHub README.
- Prepare LinkedIn summary.
- Begin Lab 006 - Offensive Security Workstation.
