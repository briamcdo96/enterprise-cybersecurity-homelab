
Lab 001 - VMware Foundation
=====================================================

Lessons Learned
=====================================================
Intel VT-x must be enabled before VMware can efficiently run 64-bit operating systems.

VMware Workstation Pro is available at no cost for personal use.

A Host-only network allows virtual machines to communicate with each other while remaining isolated from the physical network.

Using an isolated subnet prevents accidental interaction with production devices on the home network.

VMware's DHCP service can be used during the initial deployment phase before replacing it with a Windows DHCP server.

Objective
=====================================================

Build and configure the virtualization platform that
will host the offensive security home lab.


Environment
=====================================================

Host OS:
Windows 11 Pro

CPU:
Intel Core i9-14900

RAM:
64GB DDR5

Hypervisor:
VMware Workstation Pro 25H2u1

Lab Storage:
E:\CyberSecurity Labs


Current State
=====================================================

Hardware Verified

Intel VT-x Enabled

VMware Installed

Folder Structure Created

Virtual Network Editor Open

VMnet2 Pending

Default VM Location Pending

=====================================================
Build Log
=====================================================
2026-06-28 23:01:57 - Verified VMnet2 is enabled using ncpa.cpl command
2026-06-28 22:57:43 - Did not have to change Subnet mask
2026-06-28 22:56:30 - Set Subnet IP to 10.10.10.0
2026-06-28 22:53:57 - Created VMnet2
2026-06-28 22:30:00 - Opened VMware Virtual Network Editor with administrative privileges.
2026-06-28 22:18:00 - Created CyberSecurity Labs folder structure on E:\.
2026-06-28 22:05:14 - Installed VMware Workstation Pro 25H2u1.
2026-06-28 21:52:11- Verified Intel VT-x is enabled through Task Manager.
2026-06-28 21:45:00 - Verified host hardware using HWINFO64.
=====================================================
Observations
=====================================================

Host hardware exceeds the recommended specifications
for running multiple Windows and Linux virtual machines.

The cybersecurity lab will reside on the 2TB HDD.


