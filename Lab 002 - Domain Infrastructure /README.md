# Lab 002 - Domain Infrastructure
#
# Objective
Build the first Windows Server in the environment.
Configure the server to become the Active Directory
Domain Controller for the lab.
#
# Lessons Learned
2026-07-04 00:15:30 - Learned that LDAP stands for Lightweight Directory Access Protocol
2026-06-29 21:09:37 - Found the command winget upgrade --all only pulls base updates.
2026-06-29 21:09:25 - When building a VM, use custom setup - Brian M
2026-06-29 21:08:25 - When the VM fails to image, just re-build since no Data is lost.
#VM Hardware Specs
Choose the Virtual Machine hardware Compatibility
    Hardware compatibility: Workstation 25H2 or Later

Guest OS Installation
    I will install the OS later

Select a Guest OS
    Microsoft Windows
    Version: Windows Server 2025

Name the Virtual Machine
    VM name: DC01
    Location: E:\VMs\Windows\DC01

Firmware Type
    UEFI

Processor Configuration
    Number of processor: 2
    Number of cores per processor: 2

Memory for the VM
    6144 MB

Network Type
    Use host-only networking
        Updated to VMnet2 (Host-only) after inital creation inside VM Settings

Select I/O Controller Types
    LSI Logic SAS

Select a Disk type
    SCSI

Select a Disk
    Create a new virtual disk

Specify Disk Capacity
    Maximum disk size (GB): 80
    Store Virtual disks as a single file
#
# Environment

VM Name: DC01
Operating System: Windows Server 2025 Standard Evaluation(Desktop Experience)
Network: VMnet2
Subnet: 10.10.10.0/24

#
# Configuration
Hostname: DC01
Domain: lab.local
Static IP: 10.10.10.10
Subnet Mask: 255.255.255.0
Default Gateway: None
Preferred DNS: 10.10.10.10
Alternate DNS: None

#
# Future Configuration
Roles

- Active Directory Domain Services
- DNS
- DHCP (Later)

Snapshots

- Fresh Install
- Windows Updated
- Static IP Configured
- AD Installed
- Domain Controller Complete

#
# Build Log - Notes on actual build progress
2026-07-04 00:54:16 - Configured Domain Controller, following AI Helper, created snapshot Completed Domain Controller.
2026-07-04 00:12:04 - Finalized configuration, and elected to automatic restart without warning. 
2026-07-04 00:11:13 - Installing AD Domain Services, and DNS using Add Roles and Features wizard.
2026-07-04 00:10:52 - Verified Hostname is DC01, and ip of VM is 10.10.10.10
2026-06-29 21:03:15 - Snapshot created for static IP and Hostname
2026-06-29 21:02:19 - Using Settings > System tab, renamed computer to DC01
2026-06-29 21:00:32 - Settings Static IP on Ethner0 using Network Connections from Control Panel - Brian M
2026-06-29 21:00:19 - Removing VMnet8 network adapter from VM - Brian M
2026-06-29 20:55:49 - Windows Updates completed, waiting for VM to reboot - Brian M
2026-06-29 20:39:00 - Checking for more windows updates, VM found 4 new updates. - Brian M
2026-06-29 20:37:30 - Used shutdown /r /t 0 command to restart VM - Brian M
2026-06-29 20:32:26 - Executed winget upgrade --all coimmand in CMD - Brian M
2026-06-29 20:31:57 - Added secondary network adapter using VNet 8 to grant internet access - Brian M
2026-06-29 20:02:04 - Created Administrator account, credentials can be found in Personal Journal - Brian M
2026-06-29 19:57:25 - Device is now sitting on Administrator Screen - Brian M
2026-06-29 19:51:55 - Booting device into Windows 2025 Installation Media - Brian M
2026-06-29 19:49:23 - Re-image failed, decided to rebuild VM from scratch. - Brian M
2026-06-29 19:49:11 - Due to no data being on the VM, re-imaging VM - Brian M
2026-06-29 19:48:39 - Updating VM settings to boot to windows ISO and setup Network controller. - Brian M
2026-06-29 19:48:22 - Rebuild VM using custom settings (see VM hardware specs) - Brian M
2026-06-29 19:29:54 - Reconnected Sever ISO and re-installed W2025 Server OS. - Brian M
2026-06-29 19:13:37 - See VM Hardware Specs for VM details- Brian M
2026-06-29 19:11:27 - Creating Virtual Machine - Brian M
#
# Observation Log - Things noticed during build process
2026-06-29 20:52:45 - Device is running the last update for 2026-06 Security Update (KB5094125)(26100.32995)
2026-06-29 20:02:33 - During creating an administrator password the password "Rotartsinimda" did not meet requirments - Brian M
2026-06-29 19:55:47 - Device rebooted and seems to be booting into windows - Brian M
2026-06-29 19:55:17 - Device currently at 77% marker - Brian M
2026-06-29 19:54:46 - Device currently at 55% marker - Brian M
2026-06-29 19:53:37 - Device currently at 30% marker - Brian M
2026-06-29 19:52:36 - Device is currently imaging - Brian M
#
# Issues Encountered - Issues encountered during Build

2026-07-04 00:58:02 - Subnet mask was incorrectly configured as 255.0.0.0. Updated to 255.255.255.0 for the 10.10.10.0/24 lab network.
2026-06-29 19:30:23 - Device is currently sitting on a black screen frozen. - Brian M
2026-06-29 19:17:19 - When attempting to boot the VM we are getting Attempting to start up from: menu - Brian M
2026-06-29 19:15:29 - During Windows installation the VM restarted and tried to boot back to CD/DVD. - Brian M
