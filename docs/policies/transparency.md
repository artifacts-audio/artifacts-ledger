# Transparency Policy

This document defines what is public, what is private, and why.

## Guiding Principle

Artifacts Audio operates on the principle of **maximum practical transparency**. We make public everything that:

1. Users need to verify authenticity
2. Collectors need to assess value
3. The community needs to trust the system

We keep private only what would compromise security or violate user privacy.

## What Is Public

### This Ledger

The `artifacts-ledger` repository is public. It contains:

- All documentation and policies
- The complete Artifact registry (every Artifact ever released)
- All release manifests and checksums
- Signing key fingerprints
- Evolution stage history for every Artifact
- Governance and decision records

### Registry Data

For each Artifact, the following is public:

| Field | Public | Reason |
|-------|--------|--------|
| Artifact ID | ✅ | Required for verification |
| Name and description | ✅ | Required for identification |
| Evolution stage | ✅ | Determines capabilities and value |
| Release checksums | ✅ | Required for verification |
| First release date | ✅ | Provenance |
| Total units (if limited) | ✅ | Scarcity verification |
| Creator name (if disclosed) | ✅ | Attribution |
| Changelog | ✅ | Update transparency |

### Forge Source (Partial)

Selected components of Forge are open-sourced for auditability:

- Signature verification routines
- Checksum calculation
- Manifest parsing

The full Forge application source remains private (see below).

## What Is Private

### User Data

We do not publish:

- User identities or email addresses
- Purchase history
- License keys or authorization tokens
- Machine identifiers
- Usage analytics

User data is stored in a Supabase database with row-level security. Even Artifacts Audio staff access is logged and auditable.

### Business Logic

The following remain private to protect the platform:

- Forge application source code (except audit-critical components)
- API implementation details
- Anti-piracy mechanisms
- Pricing algorithms
- Operational infrastructure details

### Unreleased Work

Work in progress is private until release:

- Artifacts in development
- Unannounced features
- Internal testing builds

Once released, all relevant metadata becomes public in this ledger.

## The API Boundary

The `api.artifacts.audio` backend handles:

- Authentication and authorization
- License validation
- Purchase processing
- Telemetry (anonymized)

The API is private, but its **interface** is documented:

- Endpoints are versioned and stable
- Breaking changes are announced in advance
- Error codes and responses are documented

We do not publish:

- API source code
- Database schemas (beyond what's needed for the public registry)
- Infrastructure configuration
- Security controls

## Supabase and Data Storage

Our database is hosted on Supabase. The architecture:

| Layer | Visibility | Contents |
|-------|------------|----------|
| Public schema | Queryable | Registry data, public stats |
| Private schema | API only | User accounts, licenses, transactions |
| Storage buckets | Mixed | Public assets (public), user files (private) |

Row-level security ensures users can only access their own private data.

## How to Request Information

If you need information not covered by this policy:

1. Check if it's in this ledger first
2. Search the community forums
3. Contact [transparency@artifacts.audio](mailto:transparency@artifacts.audio)

We will either provide the information, explain why it's private, or add it to the public record if appropriate.

## Changes to This Policy

Changes to transparency boundaries require:

1. A documented rationale
2. A commit to this repository
3. Announcement in the changelog

We do not reduce transparency without serious cause (e.g., security vulnerabilities, legal requirements).
