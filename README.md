# Employee Lifecycle Management (JML) — Hybrid Identity (AD DS + Entra ID)

## Overview
Northstar Medical previously implemented foundational RBAC and departmental scoping in Active Directory. However, the organization lacked a formalized Joiner–Mover–Leaver (JML) lifecycle across its hybrid identity environment. With identities sourced from **meridianiam.net (AD DS)** and synchronized into **Google042.onmicrosoft.com (Entra ID)**, a consistent, auditable lifecycle process was required.

This project demonstrates a complete JML workflow using:
- Active Directory Domain Services (authoritative identity source)
- Entra ID (cloud identity + governance)
- Entra Connect (synchronization)
- Group-based licensing
- Attribute-driven access decisions
- Audit-ready documentation

The lab simulates a real employee, **Marcus Reyes**, moving through all three lifecycle phases:
1. Joiner — onboarding into Finance
2. Mover — transfer to Engineering
3. Leaver — termination and access revocation

---

## Architecture
### On-Prem Identity Source
- **Domain:** meridianiam.net  
- **Directory:** Active Directory Domain Services  
- **Connector:** AD DS Connector  
- **Role:** Authoritative identity store

### Cloud Identity Layer
- **Tenant:** Google042.onmicrosoft.com  
- **Directory:** Entra ID  
- **Connector:** Entra Connect  
- **Role:** Cloud identity, session revocation, licensing

---

## Tools Used
- Windows Server (AD DS)
- Entra ID
- Entra Connect
- PowerShell (delta sync)
- VirtualBox / UTM
- RBAC
- GitHub

---

## Project Timeline
**Day 1:** Joiner onboarding (AD → Entra sync)  
**Day 2:** Mover role change + access removal  
**Day 3:** Leaver termination + session revocation  
**Day 4:** Documentation + audit evidence  
**Day 5:** Packaging into GitHub case study  

---

## Key Accomplishments
- Implemented full JML lifecycle across hybrid identity
- Demonstrated proper access removal during department transfer
- Documented AD → Entra sync behavior
- Produced audit-ready artifacts for each lifecycle stage
- Showcased IAM operational maturity beyond basic onboarding
