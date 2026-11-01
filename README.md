# Qurany for Mac

A calm, native Quran app for the Mac. Free, no account, no tracking. Reads in Arabic with translation and tafsir, plays recitations with word-by-word follow-along, and works offline once you download what you need.

Website: https://qurany.zawalid.com

This repository only holds the downloads. The app's source is private. Each version is a release here, with the disk image and its checksum.

## Download

Get the latest `Qurany.dmg` from the [Releases page](../../releases/latest), or directly:

https://github.com/Zawalid/qurany-app/releases/latest/download/Qurany.dmg

Requires macOS 14 Sonoma or later. Works on Apple silicon and Intel.

## Install

1. Open the disk image and drag Qurany to the Applications folder.
2. Open Qurany from Applications. The first time, macOS shows a warning and does not open it. That is expected, see below.

## The first launch warning

Qurany is not notarized by Apple yet, because there is no paid Apple Developer account behind the project. macOS therefore cannot check it and blocks the first launch with "Apple could not verify Qurany is free of malware". That message is about the missing notarization, not a finding about the app. You confirm once and macOS remembers.

macOS 15 Sequoia and later:

1. Open Qurany from Applications. When the warning appears, click Done. Do not choose Move to Trash.
2. Open System Settings, then Privacy & Security, and scroll down to Security.
3. Qurany is listed as blocked. Click Open Anyway, confirm with your password or Touch ID, then click Open.

macOS 14 Sonoma:

1. In Applications, right-click Qurany and choose Open.
2. Click Open in the dialog. You only do this once.

On macOS 15 and later, right-click then Open no longer skips the check. Open Anyway in System Settings is the supported way.

If you prefer the Terminal, and you trust this download, this removes the quarantine flag:

```bash
xattr -dr com.apple.quarantine /Applications/Qurany.app
```

## Check your download

Each release has a `.sha256` file. In the folder with both files:

```bash
shasum -a 256 -c Qurany-0.1.0.dmg.sha256
```

Replace the version with the one you downloaded. It should print `OK`.

## Updates

For now, download the new version and replace the app in Applications. Your reading position, bookmarks and settings stay.

## Privacy

Qurany has no account and no analytics. Your location is used once, on your Mac, to work out prayer times. The full statement is at https://qurany.zawalid.com/privacy/.

## Problems and feedback

Open an issue on this repository. Please say your macOS version and what you were doing.
