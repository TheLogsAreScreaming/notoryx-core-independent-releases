# NOTORYX Core downloads (independent edition)

**Off-grid messaging over your MeshCore LoRa radio.** Part of the **NOTORYX** off-grid communications family. **No Towers. No Limits.**

This repository hosts builds of the new NOTORYX Core for Android, iPhone and Mac. Get them from **[Releases](../../releases)**.

## Status: in development, no builds yet

This edition of NOTORYX Core is being written from scratch in [notoryx-core-independent](https://github.com/TheLogsAreScreaming/notoryx-core-independent). Until it matches the current app's features, the current NOTORYX Core keeps shipping from [notoryx-core-releases](https://github.com/TheLogsAreScreaming/notoryx-core-releases) and stays the one to use every day.

Progress so far:

| Part | State |
|---|---|
| Radio protocol (commands and replies) | Done |
| Command queue and Wi-Fi (TCP) connection | Done |
| Bluetooth and USB connections | Next |
| Contacts, messages and channels | Planned |
| Chats, nodes, map and radio screens | Planned |

The first test build will appear here once the app can connect to a radio and send and receive messages.

## Installs alongside the current app

The new app has its own app ID, so you can keep both installed. It shows up as **NOTORYX Independent** while it's in development.

| | Current NOTORYX Core | NOTORYX Independent |
|---|---|---|
| Android app ID | `com.bastionmesh.bastion` | `com.bastionmesh.notoryx_core` |
| Mac bundle ID | `com.bastionmesh.bastion` | `com.bastionmesh.notoryxCore` |
| Downloads | [notoryx-core-releases](https://github.com/TheLogsAreScreaming/notoryx-core-releases) | here |

The two apps don't share data. Contacts and channels stored on your radio show up in both, because they live on the radio.

## Installing a build

When releases are posted, each one will include:

- **Android:** an `.apk`. Open it on your phone and allow installs from your browser or file manager if asked.
- **Mac:** a `.zip` with the app. Unzip it, move it to Applications, and if macOS blocks it, right-click it and choose **Open**.
- **Checksums:** a `SHA256SUMS.txt` file, so you can confirm a download wasn't changed:

```bash
shasum -a 256 -c SHA256SUMS.txt
```

Builds marked **Pre-release** are for testing and may have bugs.

## Works with

[MeshCore](https://meshcore.io/) companion radios over Bluetooth, USB or Wi-Fi. Firmware v1.18 is the main target; older firmware is supported where the protocol allows.

## Reporting problems

Open an issue in this repository with your phone or Mac model, the app version (from the About screen), your radio model and its firmware version.
