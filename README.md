# NOTORYX Core downloads (independent edition)

**Off-grid messaging over your MeshCore LoRa radio.** Part of the **NOTORYX** off-grid communications family. **No Towers. No Limits.**

This repository hosts builds of the new NOTORYX Core for Android, iPhone and Mac. Get them from **[Releases](../../releases)**.

## Status: in development, test builds out

This edition of NOTORYX Core is being written from scratch in [notoryx-core-independent](https://github.com/TheLogsAreScreaming/notoryx-core-independent). Until it matches the current app's features, the current NOTORYX Core keeps shipping from [notoryx-core-releases](https://github.com/TheLogsAreScreaming/notoryx-core-releases) and stays the one to use every day.

Progress so far:

| Part | State |
|---|---|
| Radio protocol (commands and replies) | Done |
| Command queue and Wi-Fi (TCP) connection | Done |
| Bluetooth connection | Done |
| USB connection (Android; Mac later) | Done |
| Contacts, messages and channels | Done |
| Connect, chats, contacts and conversation screens | Done |
| Reliable direct messages (retries, flood fallback, resend) | Done |
| Nodes, map and radio settings screens | Planned |

The latest test build, **[0.1.0 test 4](../../releases/tag/v0.1.0-test.4)**, connects to a radio over Bluetooth, USB (Android) or Wi-Fi, sends and receives channel and direct messages, and retries direct messages until they're delivered. It's for testing; keep using the current NOTORYX Core day to day.

## Installs alongside the current app

The new app has its own app ID, so you can keep both installed. It shows up as **NOTORYX Independent** while it's in development.

| | Current NOTORYX Core | NOTORYX Independent |
|---|---|---|
| Android app ID | `com.bastionmesh.bastion` | `com.bastionmesh.notoryx_core` |
| Mac bundle ID | `com.bastionmesh.bastion` | `com.bastionmesh.notoryxCore` |
| Downloads | [notoryx-core-releases](https://github.com/TheLogsAreScreaming/notoryx-core-releases) | here |

The two apps don't share data. Contacts and channels stored on your radio show up in both, because they live on the radio.

## Installing a build

Each release includes:

- **Android:** an `.apk`. Open it on your phone and allow installs from your browser or file manager if asked.
- **Mac** (Intel and Apple silicon, macOS 12 or newer): a `.zip` with the app. Unzip it, move it to Applications, and the first time right-click it and choose **Open** (it isn't notarized yet). Allow Bluetooth when asked.
- **Checksums:** a `SHA256SUMS.txt` file, so you can confirm a download wasn't changed:

```bash
shasum -a 256 -c SHA256SUMS.txt
```

Builds marked **Pre-release** are for testing and may have bugs.

Android builds are signed with the NOTORYX Independent release key (certificate SHA-256 `2a3e26c01231a764fb398ef4fd844f8a0b782228013b1aba5a10c41ac3500924`), so each new build updates the previous one in place.

## Works with

[MeshCore](https://meshcore.io/) companion radios over Bluetooth, USB or Wi-Fi. Firmware v1.18 is the main target; older firmware is supported where the protocol allows.

## Reporting problems

Open an issue in this repository with your phone or Mac model, the app version (from the About screen), your radio model and its firmware version.
