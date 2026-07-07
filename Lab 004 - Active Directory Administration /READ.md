# Lab 004 - Active Directory Administration

## Lab Status

| Item | Status |
|---|---|
| Status | Completed |
| Completion Date | 2026-07-06 |
| Time Spent | 1 hour 15 minutes |
| Objective | Completed Successfully |
| Verified By | Brian McDonald |

---

## Objective

Learn how Active Directory is organized and administered in an enterprise environment.

Design and implement a logical Organizational Unit structure.

Create and organize Security Groups using enterprise best practices.

Create administrative and standard domain user accounts.

Understand the relationship between Organizational Units, Security Groups, and Active Directory permissions.

---

## Environment

| Component | Value |
|---|---|
| Domain | lab.local |
| Domain Controller | DC01 |
| Client | CLIENT01 |
| Server OS | Windows Server 2025 |
| Client OS | Windows 11 Pro |
| Network | VMnet2 / 10.10.10.0/24 |

---

## Final Active Directory Structure

```text
lab.local
|
├── Administrative Accounts
├── Groups
|   ├── Administrative Roles
|   |   ├── Domain Administrators
|   |   ├── Help Desk
|   |   ├── Server Administrators
|   |   └── Workstation Administrators
|   |
|   └── Departments
|       ├── Finance
|       ├── Human Resources
|       ├── Information Technology
|       └── Marketing
|
├── Servers
├── Service Accounts
├── Users
└── Workstations
    ├── Finance
    ├── Front Desk
    |   └── CLIENT01
    ├── Human Resources
    ├── Information Technology
    ├── Marketing
    └── Training

2026-07-06 20:47:28 - Separate Department groups from Administrative Role groups. Department groups identify where a user belongs, while Administrative Role groups identify what permissions a user has.

2026-07-06 20:50:12 - Organizational Units organize Active Directory objects and are commonly used for Group Policy and delegation. Security Groups assign permissions and access.

2026-07-06 20:51:35 - Renaming or moving a user between OUs does not affect Security Group membership.

2026-07-06 20:52:18 - New Organizational Units are commonly protected from accidental deletion to prevent administrators from unintentionally removing large portions of Active Directory.
Enable View > Advanced Features inside Active Directory Users and Computers.

Open the OU Properties > Object tab.
Uncheck "Protect object from accidental deletion."
Apply changes and delete the OU if required.

2026-07-06 21:01:39 - Added Information Technology group inside Groups > Departments.
2026-07-06 21:00:02 - Deleted Server Administrator, Network Administrator, and Security Engineer groups after redesigning security group structure.
2026-07-06 20:58:49 - Created Domain Administrators, Help Desk, Server Administrators, and Workstation Administrators groups inside Groups > Administrative Roles.
2026-07-06 20:58:27 - Added Finance, Marketing, Human Resources, and Information Technology groups inside Groups > Departments.
2026-07-06 20:58:06 - Created Administrative Roles and Departments Organizational Units inside Groups.
2026-07-06 20:44:28 - Created Finance, Marketing, Human Resources, Information Technology, and Training Organizational Units inside Workstations.
2026-07-06 20:36:13 - Moved CLIENT01 from Computers container to Workstations > Front Desk.
2026-07-06 20:24:23 - Created standard domain user Betty Ross inside default Users container.
2026-07-06 20:24:06 - Configured Betty Ross account so password never expires.
2026-07-06 20:23:10 - Added James Bond to Domain Admins security group.
2026-07-06 20:21:25 - Configured James Bond account so password never expires.
2026-07-06 20:20:21 - Created personal administrator account James Bond inside Administrative Accounts OU.
2026-07-06 20:14:11 - Created Administrative Accounts, Groups, Servers, Service Accounts, and Workstations Organizational Units.

2026-07-06 20:59:54 - Newly created Organizational Units are protected against accidental deletion by default.
2026-07-06 21:02:14 - Separating Department groups from Administrative Role groups creates a cleaner and more scalable Active Directory design.

2026-07-06 20:49:34 - Accidentally enabled "Protect object from accidental deletion" on the wrong Organizational Unit. Renamed the OU to "Administrative" instead of deleting it.
