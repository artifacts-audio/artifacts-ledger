# Troubleshooting

Common issues and their resolutions.

## Installation Issues

### "Forge cannot be opened because it is from an unidentified developer" (macOS)

1. Open **System Preferences → Security & Privacy → General**
2. Click **Open Anyway** next to the Forge message
3. Alternatively, right-click Forge and select **Open**

### Forge installer fails on Windows

1. Ensure you are running the installer as Administrator
2. Temporarily disable antivirus software
3. Check that you have at least 1 GB of free disk space
4. Download a fresh copy and verify the checksum

### Plugin not appearing in DAW

1. Confirm the plugin was installed to the correct location (see [Installation](installation.md))
2. Rescan plugins in your DAW:
   - **Ableton Live**: Preferences → Plug-Ins → Rescan
   - **Logic Pro**: Restart Logic, it scans automatically
   - **Pro Tools**: Restart Pro Tools
   - **FL Studio**: Options → Manage Plugins → Rescan
3. Check if the plugin format is supported (VST3, AU, AAX)
4. On macOS, check **System Preferences → Security & Privacy** for blocked plugins

## Authorization Issues

### "License not found" error

1. Ensure you are signed in to Forge with the correct account
2. Click **Account → Refresh Licenses**
3. Check your internet connection
4. Verify the purchase in your account dashboard at artifacts.audio

### "Too many activations" error

1. Go to your account dashboard
2. Click **Manage Activations**
3. Deactivate machines you no longer use
4. Return to Forge and sign in again

### Offline mode not working

1. Ensure you signed in while online within the last 30 days
2. Check that Forge's data folder was not deleted or corrupted
3. If issues persist, connect to the internet and sign in again

## Audio Issues

### Plugin causes DAW to crash

1. Check that your DAW is updated to the latest version
2. Verify the Artifact's system requirements match your setup
3. Try increasing your audio buffer size
4. Disable other plugins to isolate the issue
5. Contact support with your crash log

### High CPU usage

1. Reduce polyphony if applicable
2. Increase your audio buffer size
3. Check if oversampling is enabled and try lowering it
4. Ensure your computer meets the minimum requirements

### No audio output

1. Check that the plugin is receiving MIDI (for instruments)
2. Verify routing in your DAW
3. Ensure the plugin is not bypassed
4. Check the plugin's output level and mix settings

## Verification Issues

### Checksum does not match

!!! danger "Stop"
    A mismatched checksum may indicate a corrupted or tampered file. Do not install it.

1. Delete the downloaded file
2. Download again from your official account dashboard
3. Re-verify the checksum
4. If it still fails, contact support immediately

### Signature verification failed

1. Ensure you are using the latest version of Forge
2. Check that your system clock is accurate
3. Try downloading the Artifact again
4. If issues persist, the Artifact may have been revoked—check the Registry

## Getting Help

If your issue is not covered here:

1. Check the [Registry](../registry/index.md) for known issues with specific Artifacts
2. Search the community forums at [artifacts.audio/community](https://artifacts.audio/community)
3. Contact support at [support@artifacts.audio](mailto:support@artifacts.audio)

When contacting support, include:

- Your operating system and version
- Forge version (Help → About)
- DAW name and version
- The exact error message or behavior
- Steps to reproduce the issue
