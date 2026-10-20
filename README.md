# Microsoft Entra ID Administration Lab

## Project Overview

This project documents a hands-on Microsoft Entra ID lab using a test Microsoft 365 tenant. The goal was to practice foundational cloud identity administration, security group management, and role-based access control (RBAC).

## Lab Environment

- **Platform:** Microsoft Entra admin center
- **Tenant:** Test tenant using the `onmicrosoft.com` domain
- **Test account:** John Smith
- **Administrator account:** Separate administrator account used to manage the tenant

## Objectives

- Verify administrator role assignments.
- Create and manage a test user.
- Create a security group and manage membership.
- Inspect administrative role permissions.
- Understand least-privilege access management.

## Tasks Completed

### 1. Administrator Role Verification

Opened the Global Administrator role assignments page and verified that the administrator account appeared in the assignments list.

### 2. Test User Management

Created a test user named John Smith for identity administration practice.

### 3. Security Group Management

Created the **IT Support Team** security group.

- **Group type:** Security
- **Membership type:** Assigned
- **Description:** Security Group for IT Employees
- **Membership verification:** Confirmed John Smith appeared in the Members tab.

### 4. Role-Based Access Control Review

Inspected the Helpdesk Administrator role description and reviewed its privileged capabilities.

- Opened the role's Assignments page.
- Confirmed that no role assignments were listed at the time of inspection.
- Reviewed the Add assignments interface without submitting an assignment.
- Did not grant the Helpdesk Administrator role to the test user.

### 5. Microsoft 365 Administration Concepts

Previously reviewed Microsoft 365 license assignment concepts without changing John Smith's license.

## Skills Practiced

- Microsoft Entra ID navigation
- Cloud user administration
- Security group creation and membership verification
- Role-based access control fundamentals
- Least-privilege principles
- Administrative role inspection
- Configuration verification and documentation

## Security Notes

This project uses a test environment. No passwords, access tokens, or other secrets are included in this repository.

Privileged role assignments were inspected but not created as part of this exercise.

## Future Improvements

- Capture sanitized screenshots of key configuration pages.
- Practice safe password-reset workflows with a test account.
- Explore additional Entra ID roles and permissions.
- Build a separate Windows Server Active Directory lab covering AD DS, DNS, and Group Policy.

## Outcome

Completed a foundational cloud identity administration exercise covering test user management, security group membership, and privileged-role inspection in Microsoft Entra ID.
