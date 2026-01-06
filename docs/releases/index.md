# Release History

Signed releases for Forge and all Artifacts.

## About Releases

Every release published by Artifacts Audio is:

1. **Signed** with our GPG key
2. **Checksummed** with SHA-256
3. **Tagged** in this Git repository
4. **Recorded** in this ledger

If you cannot verify a release against this page, do not install it.

## Verification Instructions

See the [Integrity Policy](../policies/integrity.md) for detailed verification steps.

Quick verification:

```bash
# Calculate checksum of your download
shasum -a 256 <filename>

# Compare with the checksum listed below
# They must match exactly
```

---

## Forge Releases

### Current Version

| Version | Date | Platform | SHA-256 | Status |
|---------|------|----------|---------|--------|
| — | — | — | — | *No releases yet* |

### Previous Versions

All previous versions are retained for compatibility and audit purposes.

| Version | Date | Platform | SHA-256 | Notes |
|---------|------|----------|---------|-------|
| — | — | — | — | *No releases yet* |

---

## Artifact Releases

Artifacts are released individually. Each Artifact's releases are listed on its registry page.

| Artifact | Latest Version | Date | SHA-256 |
|----------|----------------|------|---------|
| [Genesis](../registry/index.md) | — | — | *Pending release* |

---

## Release Signing Key

All releases are signed with the Artifacts Audio release key.

**Key ID**: `[TO BE PUBLISHED]`

**Fingerprint**: 
```
[TO BE PUBLISHED]
```

**Download**: [release-signing.asc](https://artifacts.audio/keys/release-signing.asc)

To import:

```bash
curl -sL https://artifacts.audio/keys/release-signing.asc | gpg --import
```

### Key History

| Key ID | Status | Valid From | Valid Until | Notes |
|--------|--------|------------|-------------|-------|
| — | — | — | — | *Initial key pending* |

---

## Git Tags

Release tags in this repository are signed and can be verified:

```bash
git clone https://github.com/artifacts-audio/artifacts-ledger.git
cd artifacts-ledger
git tag -v <tag-name>
```

### Tag Naming Convention

- Forge releases: `forge-vX.Y.Z`
- Artifact releases: `artifact-<slug>-vX.Y.Z`
- Ledger milestones: `ledger-vX.Y.Z`

---

## Release Notes Format

Each release includes:

```yaml
version: "X.Y.Z"
date: "YYYY-MM-DD"
sha256:
  macos-arm64: "..."
  macos-x64: "..."
  windows-x64: "..."
signature: "https://artifacts.audio/releases/.../signature.asc"
git_tag: "forge-vX.Y.Z"
changes:
  added:
    - "New feature description"
  changed:
    - "Changed behavior description"
  fixed:
    - "Bug fix description"
  security:
    - "Security fix description"
```

---

## Revoked Releases

If a release is found to be compromised or defective, it will be listed here.

| Release | Revocation Date | Reason | Replacement |
|---------|-----------------|--------|-------------|
| — | — | — | *No revocations* |

!!! danger "Check Before Installing"
    Always check this section before installing any release. Do not install revoked versions.
