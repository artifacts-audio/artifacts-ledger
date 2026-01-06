# Manual

This section contains practical documentation for working with Artifacts and the Forge application.

## Contents

- [Installation](installation.md) — How to download and install Forge and individual Artifacts
- [Authorization](authorization.md) — How licensing and entitlements work
- [Updates](updates.md) — How to check for and apply updates safely
- [Troubleshooting](troubleshooting.md) — Common issues and their resolutions

## Before You Begin

Artifacts are audio plugins distributed as signed, versioned bundles. Unlike conventional plugins, each Artifact carries cryptographic proof of its authenticity and evolution stage.

To work with Artifacts, you will need:

1. **Forge** — The desktop application for managing, verifying, and (if you are a creator) authoring Artifacts
2. **An Artifacts Account** — For license management and cloud sync
3. **A compatible DAW** — Artifacts support VST3, AU, and AAX formats on macOS and Windows

## Verification First

Before installing any Artifact, you should verify its integrity. See the [Integrity Policy](../policies/integrity.md) for detailed instructions.

The short version:

```bash
# Check the SHA-256 hash against the registry
shasum -a 256 Artifact-Name.af3

# Compare with the hash published in this ledger
```

If the hashes do not match, do not install the Artifact.
