# AD vs Entra Behavior — Sync & Identity Governance

## AD DS (meridianiam.net)
- Authoritative identity source
- OU placement determines departmental scope
- Security groups determine access
- Attribute changes drive lifecycle events
- Account disablement originates here

## Entra ID (Google042.onmicrosoft.com)
- Cloud identity layer
- Receives identity via Entra Connect
- Enforces:
  - Conditional Access
  - Session revocation
  - Licensing
  - MFA
- Mirrors AD group membership for synced users

## Sync Behavior
- Delta sync pushes attribute changes
- Group membership changes propagate within minutes
- Disabled AD accounts become “Blocked” in Entra
