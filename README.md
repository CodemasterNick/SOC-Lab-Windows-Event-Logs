# SOC Lab — Windows Event Logs Investigation

## Overview

This project simulates a basic Security Operations Center (SOC) investigation using Windows Security Event Logs.

The objective was to identify, analyze, and interpret security events related to authentication, user account management, group membership changes, and special privileges.

## Environment

- Operating System: Windows 11
- Tools: Windows Event Viewer
- Command Line: Windows PowerShell
- Lab Type: Controlled local environment

## Investigated Security Events

| Event ID | Description | Investigation |
|---|---|---|
| 4624 | Successful logon | Identified different logon types |
| 4625 | Failed logon | Generated and investigated a failed authentication |
| 4720 | User account created | Created and investigated the SOC_Lab account |
| 4732 | Member added to a security-enabled local group | Identified the addition of SOC_Lab to the Users group |
| 4672 | Special privileges assigned to a new logon | Investigated special privileges associated with the SYSTEM account |

## Investigation Process

### 1. Authentication Analysis

Investigated successful and failed authentication events.

- Event ID 4624: analyzed logon types 2, 5, 7, and 11.
- Event ID 4625: generated a controlled failed login attempt and analyzed the event details.
- Identified the `winlogon.exe` process during the investigation of a successful interactive logon.

### 2. User Account Management

Created a temporary local account named `SOC_Lab` using PowerShell.

Command:

`net user SOC_Lab /add`

Investigated Event ID 4720 to identify the account creation activity and its associated details.

### 3. Group Membership Investigation

Added the temporary account to the standard local Users group.

Investigated Event ID 4732 to identify the account and the target group.

### 4. Special Privileges Analysis

Investigated Event ID 4672 and identified the `SYSTEM` account and its associated special privileges.

### 5. Lab Cleanup

Removed the temporary account after completing the investigation.

Command:

`net user SOC_Lab /delete`

## Key Findings

- Identified successful and failed authentication events.
- Differentiated interactive logons, service logons, unlock events, and cached interactive logons.
- Investigated local user account creation.
- Identified a local group membership change.
- Analyzed special privileges associated with the Windows SYSTEM account.
- Practiced interpreting Windows Security Event Logs in a controlled environment.

## Conclusion

This lab provided practical experience in Windows security event monitoring and basic SOC investigation procedures.

It reinforced the importance of understanding authentication events, account management activities, and privilege assignments when investigating potential security incidents.
