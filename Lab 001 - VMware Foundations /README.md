# Lab 001 - VMware Foundation

## Objective

Build and configure the virtualization platform that will host the enterprise cybersecurity home lab. This foundation provides an isolated environment for deploying Active Directory, Windows clients, offensive security tools, and future security testing.

---

## Environment

| Component | Configuration |
|-----------|---------------|
| **Host Operating System** | Windows 11 Pro |
| **Processor** | Intel Core i9-14900 |
| **Memory** | 64 GB DDR5 |
| **Hypervisor** | VMware Workstation Pro 25H2 Update 1 |
| **Lab Storage** | E:\CyberSecurity Labs |

---

## Technologies Used

- VMware Workstation Pro
- VMware Virtual Network Editor
- Windows 11 Pro
- Intel VT-x Virtualization
- Host-only Networking

---

## Current Status

- [x] Host hardware verified
- [x] Intel VT-x virtualization enabled
- [x] VMware Workstation Pro installed
- [x] CyberSecurity Labs directory created
- [x] Virtual Network Editor configured
- [x] VMnet2 Host-only network created

---

## Build Log

| Date & Time | Activity |
|-------------|----------|
| 2026-06-28 21:45 | Verified host hardware using HWiNFO64. |
| 2026-06-28 21:52 | Verified Intel VT-x was enabled using Windows Task Manager. |
| 2026-06-28 22:05 | Installed VMware Workstation Pro 25H2 Update 1. |
| 2026-06-28 22:18 | Created **E:\CyberSecurity Labs** directory structure. |
| 2026-06-28 22:30 | Opened VMware Virtual Network Editor with administrative privileges. |
| 2026-06-28 22:53 | Created Host-only network (**VMnet2**). |
| 2026-06-28 22:56 | Configured subnet address to **10.10.10.0/24**. |
| 2026-06-28 22:57 | Verified default subnet mask configuration. |
| 2026-06-28 23:01 | Confirmed VMnet2 adapter using **ncpa.cpl**. |

---

## Observations

- The host hardware exceeds the recommended specifications for running multiple Windows and Linux virtual machines simultaneously.
- The cybersecurity lab will be stored on a dedicated **2 TB HDD**, separating lab data from the operating system drive.
- Using a dedicated Host-only network isolates lab traffic from the home network while allowing communication between virtual machines.

---

## Lessons Learned

- Intel VT-x must be enabled before VMware can efficiently run 64-bit operating systems.
- VMware Workstation Pro is available free of charge for personal use.
- Host-only networking provides secure communication between virtual machines while preventing exposure to the production network.
- Using an isolated subnet reduces the risk of accidental interaction with production devices.
- VMware's built-in DHCP service can simplify the initial deployment phase before migrating to a Windows Server DHCP service.

---

##  Skills Demonstrated

- VMware Workstation Administration
- Virtual Network Configuration
- Host-only Network Design
- Windows Virtualization
- Enterprise Lab Planning
- Infrastructure Documentation

---

## Next Lab

**Lab 002 – Domain Infrastructure**

Deploy Windows Server 2025, configure networking, and promote the server to an Active Directory Domain Controller.
