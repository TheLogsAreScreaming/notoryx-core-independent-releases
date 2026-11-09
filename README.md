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
| Automatic reconnect (at launch and after a drop) | Works on Mac; fixing Android |
| Unread counts, muting and notifications | Done |
| Add, share and manage contacts and channels | Done |
| Radio settings and local mesh presets | Done |
| Local mesh settings (suggests your area's radio settings) | Done |
| Map and node details | Done |
| QR codes for contacts and channels | Done |
| Repeater and room tools (log in, status, console) | Done |
| Message search | Done |
| Delivery details for sent messages | Done |
| Staying connected in the background (Android) | Done, needs a phone test |
| Path trace | Done |
| Packet log (everything the radio hears) | Done |
| Smaller phone-only Android download (40 MB) | Done |
| Map works offline where you've looked | Done |
| Telemetry history (battery and sensors over time) | Done |
| Quick messages and drafts | Done |
| Reactions and replies | Done |
| SOS (hold to send, repeats until answered, I'm safe) | Done |
| Check-ins: four kinds, trip contacts, who it reached, quiet warnings | Done |
| Noise floor history | Done, needs a radio test |
| Contact meter and making room for new contacts | Done |
| Automatic updates with Obtainium | Done |
| About screen with details for problem reports | Done |
| Encrypted backup and restore | Done |
| Block senders, highlight mentions | Done |
| Find channels (heard on air, near you, directory) | Done, needs a radio test |
| Share a position or contact in chat | Done |
| Track log with GPX export, sensor badges on the map | Done, needs a phone test |
| Repeater ping, neighbors and access control | Done, needs a radio test |
| Antenna hunt | Done, needs a radio test |
| Command line for your own radio, Wi-Fi setup | Done, needs a radio test |
| Your radio's battery and sensors on the home screen, refresh rate | Done, needs a radio test |
| Eight themes and chat text size | Done |
| Add contacts from an advert or key, or several at once | Done, needs a radio test |
| Auto-delete old channel messages, hide repeated posts | Done |
| Forget last advert time | Done, needs a radio test |
| Trip brief and Field Log | Done, needs a radio test |
| Field guide | Done |
| App-icon shortcuts (Android) | Done, needs a phone test |
| Separate Bluetooth and app logs | Done |
| Full app and menus with or without a radio | Done, needs a phone test |
| Trusted contact's command line | Done, needs a radio test |
| Channel post regions (real region scoping) | Done, needs a radio test |
| SALUTE and 9-Line reports | Done, needs a radio test |

The latest test build, **[0.1.0 test 18](../../releases/tag/v0.1.0-test.18)**, connects to a radio over Bluetooth, USB (Android) or Wi-Fi, sends and receives channel and direct messages with retries, reconnects by itself, shows unread counts and notifications, manages contacts and channels (with QR codes), changes the radio's own settings, shows nodes on a map, logs in to repeaters and room servers, searches messages, explains deliveries, traces routes, stays connected in the background on Android, logs every packet heard, keeps the map working offline where you've looked, charts battery and sensor telemetry, has one-tap quick messages and saved drafts, reactions and replies, an SOS that repeats until someone answers, check-ins to up to six trip contacts showing who each reached, a noise floor chart, a contact meter that helps make room when the radio is full, encrypted backup and restore, blocking and highlighted mentions, a way to find channels in use nearby, and sharing positions and contacts in chat.

## Which Android file?

- `…-android-arm64.apk` (about 40 MB): almost every phone since 2017. Start here.
- `…-android.apk` (about 83 MB): older 32-bit phones, Chromebooks and emulators.

Both have the same version and signature, so either updates the other in place.

## Automatic updates (Obtainium)

[Obtainium](https://github.com/ImranR98/Obtainium) can install new Android builds from here as they come out:

1. In Obtainium, tap **Add App**.
2. **App source URL:** `https://github.com/TheLogsAreScreaming/notoryx-core-independent-releases`
3. Turn on **Include prereleases**. Every test build is a pre-release, so without this Obtainium finds nothing.
4. **Filter APKs by regular expression:** `arm64` for most phones, or `android\.apk$` for the full build.
5. Tap **Add**, then **Install**. A copy you installed by hand gets updated too, because the signing key is the same.

This works from test 15 on. Earlier builds all reported version `0.1.0`, so Obtainium couldn't tell them apart.

## Installs alongside the current app

The new app has its own app ID, so you can keep both installed. It shows up as **NOTORYX Independent**, with a silver NOTORYX icon, while it's in development.

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

## Local mesh settings

[`regional_presets.json`](regional_presets.json) lists areas whose meshes use different radio settings from the usual ones for their part of the world, such as Phoenix on 908.205 MHz / 62.5 / SF9. Most are worked out from the public [MeshCore map](https://map.meshcore.io), where node owners report their settings, so they aren't checked on air. The app checks this file at launch and also ships a built-in copy. If your area is missing or wrong, [open an issue](../../issues/new) and say where the settings come from.

## Reporting problems

Open an issue in this repository with your phone or Mac model, the app version (from the About screen), your radio model and its firmware version.
