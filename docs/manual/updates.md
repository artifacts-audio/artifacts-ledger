# Updates

This guide covers how Artifacts and Forge receive updates, and how to apply them safely.

## Update Philosophy

Artifacts Audio takes a conservative approach to updates:

- **Stability over features**: We do not push updates that risk breaking existing projects
- **Opt-in evolution**: The Combust mechanism means major changes are a user choice, not forced
- **Verification required**: All updates are signed and can be verified before installation

## Checking for Updates

### Forge Updates

Forge checks for updates automatically on launch (if online). You can also check manually:

1. Open Forge
2. Go to **Help → Check for Updates**
3. If an update is available, Forge will show the version, changelog, and verification hash

### Artifact Updates

Individual Artifacts may receive updates for:

- Bug fixes
- Performance improvements
- Compatibility with new OS versions

Artifact updates do **not** change the Artifact's evolution stage. Stage changes only happen through [Combust](../concepts/combust.md).

To check for Artifact updates:

1. Open Forge
2. Go to **Library**
3. Artifacts with available updates show a badge
4. Click the Artifact and select **Update**

## Verifying Updates

Before applying any update:

1. Note the **SHA-256 hash** shown in Forge
2. Check this hash against the [Releases](../releases/index.md) page in this ledger
3. If the hashes match, proceed with the update
4. If they do not match, **do not install** and report the discrepancy

!!! danger "Never Install Unverified Updates"
    An update that cannot be verified against this ledger may be compromised. Do not install it.

## Applying Updates

### Automatic (Recommended)

1. When Forge shows an available update, click **Update**
2. Forge will download, verify, and install the update
3. Restart Forge if prompted

### Manual

For users who prefer manual control:

1. Download the update from your account dashboard
2. Verify the checksum manually:
   ```bash
   shasum -a 256 Forge-x.x.x.dmg
   ```
3. Compare with the hash in the [Releases](../releases/index.md)
4. Install as you would a fresh installation

## Rolling Back

If an update causes issues:

### Forge

1. Download the previous version from your account dashboard (all versions are retained)
2. Uninstall the current version
3. Install the previous version

### Artifacts

Artifacts are immutable once released. If an Artifact update causes issues:

1. Contact support to request the previous version
2. Uninstall the updated version via Forge
3. Install the previous version

We retain all released versions indefinitely.

## Release Channels

Forge supports multiple release channels:

| Channel | Description | Stability |
|---------|-------------|-----------|
| **Stable** | Production releases, fully tested | High |
| **Beta** | Pre-release features, may have bugs | Medium |
| **Dev** | Bleeding edge, for testing only | Low |

To change your release channel:

1. Open Forge
2. Go to **Preferences → Updates**
3. Select your preferred channel

Most users should stay on **Stable**.
