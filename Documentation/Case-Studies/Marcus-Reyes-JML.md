# Case Study — Marcus Reyes (Finance → Engineering → Termination)

## Summary
This case study documents the full identity lifecycle of employee **Marcus Reyes**, demonstrating proper governance across hybrid identity.

---

## Joiner — July 1
Marcus was onboarded into the Finance department. His AD attributes and group membership were configured, and Entra reflected the correct sync source and licensing.

---

## Mover — July 22
Marcus transferred to Engineering. His OU placement, job title, department, and group membership were updated. Finance access was fully removed, preventing permission accumulation.

---

## Leaver — October 15
Marcus left the company. His AD account was disabled, removed from groups, synced to Entra, and all sessions were revoked. Access was fully terminated.

---

## Outcome
This lifecycle demonstrates:
- Clean onboarding
- Proper access removal during role change
- Complete termination workflow
- Audit-ready documentation
