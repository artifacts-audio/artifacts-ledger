# Artifact Registry

The canonical catalog of all Artifacts ever created.

## About the Registry

This registry is the single source of truth for Artifact existence. An Artifact that does not appear here does not officially exist.

Each entry includes:

- **ID**: Unique identifier (format: `AA-NNNNNN`)
- **Slug**: URL-safe name
- **Title**: Display name
- **Status**: Current state (active, retired, revoked)
- **Stage**: Current evolution stage (Spark through Inferno)
- **Supply**: Total units (if limited) or "Unlimited"
- **First Seen**: Date of first release
- **Canonical Page**: Link to detailed information

## Registry Data

The machine-readable registry is maintained at:

```
/registry/artifacts.yaml
```

This file is the authoritative source. The entries below are rendered from it.

## Registered Artifacts

| ID | Title | Status | Stage | Supply | First Seen |
|----|-------|--------|-------|--------|------------|
| AA-000001 | Genesis | Pending | — | 1 | TBD |

---

## Verification

To verify an Artifact against this registry:

1. Obtain the Artifact's claimed ID
2. Look up the ID in the registry
3. Compare the SHA-256 checksum of your file against the registered checksum
4. If they match, the Artifact is authentic

If the ID is not in this registry, the Artifact is not recognized by Artifacts Audio.

## Registry Schema

Each Artifact entry follows this schema:

```yaml
- id: "AA-000001"
  slug: "genesis"
  title: "Genesis"
  status: "active"           # active | retired | revoked
  stage: "spark"             # spark | ember | flame | blaze | inferno
  supply:
    type: "limited"          # limited | unlimited
    total: 1
    claimed: 0
  creator: "Artifacts Audio"
  first_seen: "2025-01-01"
  canonical_page: "/registry/artifacts/genesis"
  releases:
    - version: "1.0.0"
      date: "2025-01-01"
      sha256: "..."
      notes: "Initial release"
  transfer_policy: "non-transferable"  # transferable | non-transferable | limited
  notes: "The first Artifact. One of one."
```

## Adding to the Registry

Only Artifacts Audio can add entries to the official registry. The process:

1. Artifact is created in Forge
2. Artifact passes internal validation
3. Artifact is signed with the release key
4. Entry is added to `registry/artifacts.yaml`
5. Commit is pushed to this repository
6. Git tag is created for the release

Community-created Artifacts (when supported) will follow a similar process with additional verification steps.
