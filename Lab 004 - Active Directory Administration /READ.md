# Lab 004 - Active Directory Administration

## Lab Status

| Item | Status |
|------|--------|
| Status | Completed |
| Completion Date | 2026-07-06 |
| Time Spent | 1 Hour 15 Minutes |
| Verified By | Brian McDonald |

---

# Objective

This lab focused on designing and implementing a scalable Active Directory structure that follows enterprise administration best practices.

## Goals

- Design a logical Organizational Unit (OU) hierarchy.
- Create administrative and standard user accounts.
- Organize Security Groups using enterprise best practices.
- Separate department-based groups from administrative role groups.
- Gain a foundational understanding of Active Directory object organization and delegation.

---

# Environment

| Component | Value |
|-----------|-------|
| Domain | lab.local |
| Domain Controller | DC01 |
| Client | CLIENT01 |
| Operating System | Windows Server 2025 |
| Active Directory | Domain Services |
| DNS | Installed |

---

# Organizational Unit Structure

```text
lab.local
│
├── Administrative Accounts
├── Groups
│   ├── Administrative Roles
│   └── Departments
├── Servers
├── Service Accounts
├── Users
└── Workstations
    ├── Finance
    ├── Front Desk
    ├── Human Resources
    ├── Information Technology
    ├── Marketing
    └── Training
