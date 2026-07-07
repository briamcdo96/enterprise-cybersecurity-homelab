# Lab 004 - Active Directory Administration

## Objective

Learn how Active Directory is organized and administered in an enterprise environment by designing a scalable Organizational Unit (OU) structure, implementing Security Groups using enterprise best practices, and creating administrative and standard user accounts.

---

## Lab Status

| Item | Value |
|------|-------|
| Status | Completed |
| Completion Date | 2026-07-06 |
| Time Spent | 1 Hour 15 Minutes |
| Result | Completed Successfully |

---

## Environment

| Component | Configuration |
|-----------|---------------|
| Domain | lab.local |
| Domain Controller | DC01 |
| Administrative Workstation | CLIENT01 |
| Management Tool | Active Directory Users and Computers (ADUC) |

---

## Active Directory Structure

### Organizational Units

```
lab.local
│
├── Administrative Accounts
├── Groups
│   ├── Administrative Roles
│   └── Departments
├── Servers
├── Service Accounts
└── Workstations
    ├── Finance
    ├── Front Desk
    ├── Human Resources
    ├── Information Technology
    ├── Marketing
    └── Training
```

---

## Security Groups

### Administrative Roles

- Domain Administrators
- Help Desk
- Server Administrators
- Workstation Administrators

### Departments

- Finance
- Human Resources
- Information Technology
- Marketing

---

## User Accounts Created

| Account | Type | Notes |
|---------|------|------|
| James Bond | Administrative Account | Added to **Domain Admins** |
| Betty Ross | Standard User | Password configured to never expire |

---

## Current Status

- [x] Organizational Unit structure created
- [x] Administrative Security Groups created
- [x] Department Security Groups created
- [x] Administrative account created
- [x] Standard domain user created
- [x] CLIENT01 moved into Workstations OU
- [x] Enterprise Active Directory structure verified

---

## Build Log

| Date & Time | Activity |
|-------------|----------|
| 2026-07-06 20:14 | Created Organizational Units for Administrative Accounts, Groups, Servers, Service Accounts, and Workstations. |
| 2026-07-06 20:20 | Created administrative user account **James Bond**. |
| 2026-07-06 20:21 | Configured administrative account so the password never expires. |
| 2026-07-06 20:23 | Added James Bond to the **Domain Admins** security group. |
| 2026-07-06 20:24 | Created standard user account **Betty Ross**. |
| 2026-07-06 20:24 | Configured Betty Ross account so the password never expires. |
| 2026-07-06 20:36 | Moved **CLIENT01** from the default Computers container into the **Workstations → Front Desk** Organizational Unit. |
| 2026-07-06 20:44 | Created departmental Organizational Units beneath **Workstations**. |
| 2026-07-06 20:58 | Created **Administrative Roles** and **Departments** Organizational Units beneath **Groups**. |
| 2026-07-06 20:58 | Created departmental Security Groups. |
| 2026-07-06 20:58 | Created administrative Security Groups. |
| 2026-07-06 21:00 | Removed previously created Security Groups after redesigning the Active Directory structure. |
| 2026-07-06 21:01 | Added the Information Technology department Security Group. |

---

## Issues Encountered

### Organizational Unit Protected from Deletion

**Issue**

An Organizational Unit was accidentally created with **Protect object from accidental deletion** enabled, preventing it from being removed.

**Resolution**

Enabled **View → Advanced Features** in Active Directory Users and Computers, opened the Organizational Unit properties, selected the **Object** tab, disabled accidental deletion protection, and removed or renamed the Organizational Unit as required.

---

## Observations

- Newly created Organizational Units are protected from accidental deletion by default.
- Separating **Department Security Groups** from **Administrative Role Security Groups** creates a cleaner and more scalable enterprise design.
- Moving users or computers between Organizational Units does not affect their Security Group memberships.
- Organizational Units are primarily used for Group Policy application and administrative delegation, while Security Groups control access and permissions.

---

## Lessons Learned

- Department Security Groups should identify **where users belong**, while Administrative Role Security Groups define **what permissions users receive**.
- Organizational Units provide logical organization for Active Directory objects and are commonly used for Group Policy deployment and delegated administration.
- Security Groups are responsible for assigning permissions and controlling access to resources.
- Moving or renaming objects within Organizational Units does not impact Security Group membership.
- Organizational Units are protected against accidental deletion by default to reduce the risk of administrators unintentionally removing critical Active Directory infrastructure.

---

## Skills Demonstrated

- Active Directory Administration
- Organizational Unit Design
- Enterprise Active Directory Architecture
- Security Group Management
- Administrative Account Management
- User Account Administration
- Active Directory Best Practices
- Principle of Least Privilege
- Enterprise Documentation

---

## Next Lab

**Lab 005 - Group Policy Management**

Design and implement Group Policy Objects (GPOs) to centrally manage user and computer configurations, enforce security settings, and automate enterprise workstation administration.
