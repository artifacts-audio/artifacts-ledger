# Installation

This guide covers installing Forge and individual Artifacts on macOS and Windows.

## System Requirements

| Component | macOS | Windows |
|-----------|-------|---------|
| OS Version | macOS 11+ (Big Sur) | Windows 10+ |
| Architecture | Intel or Apple Silicon | x64 |
| RAM | 8 GB minimum | 8 GB minimum |
| Disk Space | 500 MB for Forge | 500 MB for Forge |
| Plugin Formats | VST3, AU, AAX | VST3, AAX |

## Installing Forge

Forge is the central application for managing your Artifacts library.

### macOS

1. Download `Forge-x.x.x.dmg` from your account at [artifacts.audio](https://artifacts.audio)
2. Verify the download (see [Integrity Policy](../policies/integrity.md))
3. Open the DMG and drag Forge to your Applications folder
4. On first launch, macOS may require you to approve the app in System Preferences → Security & Privacy

### Windows

1. Download `Forge-x.x.x-Setup.exe` from your account
2. Verify the download
3. Run the installer and follow the prompts
4. Forge will be available in your Start menu

## Installing Artifacts

Individual Artifacts are distributed as `.af3` files (Artifact Format v3).

### Via Forge (Recommended)

1. Open Forge
2. Go to **Library → Import**
3. Select your `.af3` file
4. Forge will verify the signature, extract the plugin, and register it

### Manual Installation

If you prefer to install plugins directly:

1. Verify the `.af3` file's checksum against the [Registry](../registry/index.md)
2. Extract the plugin bundle using Forge CLI or a compatible tool
3. Copy the extracted plugin to your system plugin folder:
   - **macOS VST3**: `/Library/Audio/Plug-Ins/VST3/`
   - **macOS AU**: `/Library/Audio/Plug-Ins/Components/`
   - **Windows VST3**: `C:\Program Files\Common Files\VST3\`
4. Rescan plugins in your DAW

!!! warning "Signature Verification"
    Manually installed plugins bypass Forge's automatic verification. You are responsible for confirming authenticity before use.

## Plugin Locations

Forge installs verified plugins to standard system locations by default. You can customize this in **Forge → Preferences → Plugin Paths**.

## Uninstalling

To remove an Artifact:

1. Open Forge
2. Go to **Library**
3. Right-click the Artifact and select **Uninstall**
4. Forge will remove the plugin files and update your library

To remove Forge itself:

- **macOS**: Delete Forge from Applications and remove `~/Library/Application Support/Artifacts Audio/`
- **Windows**: Use Add/Remove Programs, then delete `%APPDATA%\Artifacts Audio\`
