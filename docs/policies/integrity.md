# Integrity Policy

This document defines how Artifacts Audio ensures the integrity of all releases and how you can verify them.

## Principles

1. **Every release is signed.** No Artifact or tool is published without a cryptographic signature.
2. **Every release is recorded.** This ledger contains the canonical list of all releases with their checksums.
3. **Verification is your right.** You can and should verify any release before installing it.
4. **Transparency is non-negotiable.** The verification process is fully documented and uses standard tools.

## What Gets Signed

- Forge application releases (macOS and Windows)
- Individual Artifact bundles (`.af3` files)
- Release manifests (JSON files listing bundle contents)
- This repository's release tags

## Verification Methods

### Method 1: Checksum Verification (Simplest)

Every release has a SHA-256 checksum published in the [Releases](../releases/index.md) section.

```bash
# Calculate the checksum of your downloaded file
shasum -a 256 Artifact-Name.af3

# Compare with the published checksum
# They must match exactly
```

### Method 2: GPG Signature Verification

Releases are signed with the Artifacts Audio GPG key.

```bash
# Import the public key (one-time)
curl -sL https://artifacts.audio/keys/release-signing.asc | gpg --import

# Verify a release
gpg --verify Artifact-Name.af3.sig Artifact-Name.af3
```

The signing key fingerprint is:

```
[KEY FINGERPRINT WILL BE PUBLISHED HERE]
```

This fingerprint is also recorded in the [Registry](../registry/index.md) and can be verified against multiple sources.

### Method 3: Git Tag Verification

Release tags in this repository are signed. You can verify them with:

```bash
git clone https://github.com/artifacts-audio/artifacts-ledger.git
cd artifacts-ledger
git tag -v v1.0.0  # Replace with the release tag
```

## The Release Record

Each release in this ledger includes:

| Field | Description |
|-------|-------------|
| `version` | Semantic version number |
| `date` | Release date (UTC) |
| `sha256` | SHA-256 checksum of the release file |
| `signature` | Detached GPG signature (or link to) |
| `changelog` | Summary of changes |
| `git_tag` | Corresponding Git tag in this repository |

## What to Do If Verification Fails

1. **Do not install the file.**
2. Delete it immediately.
3. Download again from your official account dashboard.
4. Re-verify.
5. If verification still fails, contact [support@artifacts.audio](mailto:support@artifacts.audio) and do not install until the issue is resolved.

A verification failure may indicate:

- A corrupted download
- A man-in-the-middle attack
- A compromised distribution channel
- A revoked release

All of these are serious. Do not proceed without resolution.

## Key Revocation

If the signing key is ever compromised:

1. A revocation notice will be published in this repository
2. A new key will be generated and published
3. All releases will be re-signed with the new key
4. The old key fingerprint will be added to a revocation list

Check the [Policies](index.md) section for any active revocation notices before verifying releases.

## Auditing

This repository's commit history is the audit trail. Every change to release records is a Git commit with a timestamp and author.

You can audit the history:

```bash
git log --oneline docs/releases/
git log --oneline registry/
```

We do not rewrite Git history on the main branch. Force-pushes are disabled.
