# integration-plex pilot repo bundle

This directory simulates the first low-risk external split target repo:

- Proposed external repo: `carapace-app/carapace-integration-plex`
- Package ID: `integration-plex`
- Package family: `integration`

## Extraction boundary (pilot)

Moves to split repo:
- `carapace-package.json`
- `files/integrations/plex/**`
- package-level docs specific to Plex integration package behavior

Stays in monorepo:
- Package manager runtime (`services/packageManager.js`, `/api/packages/*`)
- UI (`new_frontend/.../PackageManager.tsx`)
- Feed registry (`.carapace-home/packages/github-feeds.json`)
- Other integrations (`integration-remote-collab`)
- Any cross-cutting backend Plex APIs in `server.js`

## Transitional install model

- Local install path remains authoritative and functional via:
  - `.carapace-home/packages/local/integration-plex`
- GitHub release source is now represented in feed metadata for source-selection readiness.

This pilot is intentionally reversible: local package layout and install semantics are unchanged.