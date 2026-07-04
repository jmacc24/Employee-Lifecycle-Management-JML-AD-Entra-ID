# JML Workflow — Hybrid Identity (AD DS → Entra ID)

This document outlines the full Joiner–Mover–Leaver lifecycle for employee **Marcus Reyes**, demonstrating identity governance across on-prem AD DS and Entra ID.

---

## 1. Joiner — July 1

### AD DS Actions
- Created user in **Finance OU**
- Attributes set:
  - Job Title: Finance Analyst
  - Department: Finance
  - Manager: Finance Manager
- Added to **Finance-Users** security group
- Password set (lab standard)
- “User must change password at next logon” unchecked for lab convenience

### Sync Actions
- Forced delta sync: Import-Module ADSync
Start-ADSyncSyncCycle -PolicyType Delta

- User appears in Entra with:
- Sync source: Windows Server AD
- Group membership: Finance-Users
- License applied via group-based licensing (if configured)


---

## 2. Mover — July 22

### AD DS Actions
- Moved Marcus from **Finance OU → Engineering OU**
- Updated attributes:
- Job Title: Junior DevOps Engineer
- Department: Engineering
- Group membership changes:
- Removed: Finance-Users
- Added: Engineering-Users

### Sync Actions
- Forced delta sync
- Entra reflects updated group membership

### Audit Requirement
Document:
- Access removed (Finance resources)
- Access added (Engineering resources)
- Confirmation that no Finance access remains


---

## 3. Leaver — October 15

### AD DS Actions
- Disabled Marcus’s account
- Removed from all groups except Domain Users
- Reset password to random string
- Optional: moved to Disabled Users OU

### Sync Actions
- Forced delta sync
- Entra reflects disabled state

### Entra Actions
- Revoke sessions (invalidates refresh tokens)
- Verify sign-in blocked
- Optional: convert mailbox to shared (if Exchange Online)


---

## Summary
This workflow demonstrates:
- Proper identity lifecycle governance
- Attribute-driven access changes
- Hybrid identity synchronization
- Audit-ready documentation

