# Qurany for Mac

A calm, native Quran app for the Mac. No account, no ads, no tracking. Read in Arabic with translation and tafsir,
listen with word-by-word follow-along, memorise, and keep your prayer times, all on your own Mac. Available in
English, Arabic and French.

Website: https://qurany.zawalid.com

This repository only holds the downloads. The app's source code is private. Each version is a release here, with the
disk image and its checksum.

## Status

Qurany is at its first public releases, so expect rough edges.

- **Not notarized.** The app is signed ad hoc, not with a paid Apple Developer ID, so macOS asks you to confirm the
  first launch. See [First launch](#first-launch-macos-asks-you-to-confirm).
- **Releases start as drafts.** A version appears here only after it has been tried on a clean Mac account.
- **Draft text.** French and Arabic wording is still waiting for a native read, and the surah introductions and the
  knowledge cards are marked as drafts in the app until they have been reviewed. Please report anything that reads
  wrongly.
- **Some content is not yet confirmed.** A few datasets, the recitation audio and some translations are used while
  permission from their publishers is pending. [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) lists each one honestly.
- **Free for now.** Qurany costs nothing today. This may change in a future version, and any change will be written
  here and on the website before it happens.

## Download

Get the latest `Qurany.dmg` from the [Releases page](../../releases/latest), or directly:

https://github.com/Zawalid/qurany-app/releases/latest/download/Qurany.dmg

Requires macOS 14 Sonoma or later, on Apple silicon or Intel.

## Install

1. Open the disk image and drag Qurany to the Applications folder.
2. Open Qurany from Applications. The first time, macOS shows a warning and does not open it. That is expected, see
   below.

## First launch: macOS asks you to confirm

Qurany is not notarized by Apple, because there is no paid Apple Developer account behind the project. macOS cannot
check it, so it blocks the first launch with "Apple could not verify Qurany is free of malware". That message is about
the missing notarization, not a finding about the app. You confirm once and macOS remembers.

**macOS 15 Sequoia and later**

1. Open Qurany from Applications. When the warning appears, click Done. Do not choose Move to Trash.
2. Open System Settings, then Privacy & Security, and scroll down to Security.
3. Qurany is listed as blocked. Click Open Anyway, confirm with your password or Touch ID, then click Open.

**macOS 14 Sonoma**

1. In Applications, right-click Qurany and choose Open.
2. Click Open in the dialog. You only do this once.

On macOS 15 and later, right-click then Open no longer skips the check. Open Anyway in System Settings is the
supported way.

If you prefer the Terminal, and you trust this download, this removes the quarantine flag:

```bash
xattr -dr com.apple.quarantine /Applications/Qurany.app
```

## Check your download

Each release has a `.sha256` file. Put it next to the disk image and run, in that folder:

```bash
shasum -a 256 -c Qurany-0.1.0.dmg.sha256
```

Replace the version with the one you downloaded. It should print `OK`.

## What it does

- **Read**: verse list or a 604-page Mushaf layout with a real page turn, juz and surah navigation, five themes,
  tajweed colouring, three Arabic fonts, focus mode and auto-scroll.
- **Understand**: translations, tafsir, surah introductions, a word-by-word popover with meaning and root, similar
  ayahs, topics, and a search that ignores diacritics (Arabic and English) with go-to such as `2:255`, `page 50`
  or `juz 5`.
- **Listen**: dozens of reciters, word-by-word highlighting for many of them, repeat, speed, A-B loop, sleep timer,
  offline downloads, media keys, a mini player and a menu bar item.
- **Memorise**: a hifz plan with a calendar, spaced reviews, guided learning, look-alike ayah drills, saved words
  with flashcards, and recite aloud with speech recognition.
- **Daily life**: prayer times, adhan and reminders, Qibla, Hijri calendar, tasbih, habits, journal, a khatma plan with
  streaks, and awards.
- **Share**: turn an ayah into a picture card in several styles and sizes.
- **Keep your own data**: bookmarks with folders, notes and highlights, export and import as one file, and optional
  sync between devices through a folder you choose.

## Privacy

The short version: no account, no analytics, no advertising identifier, no server of ours. What you read, mark,
memorise and write stays on your Mac.

What can leave your Mac, and when:

| What | Sent to | When |
| --- | --- | --- |
| Which recitation file you ask for | everyayah.com (audio) and mp3quran.net (whole-surah audio) | When you play or download a recitation you do not already have. Nothing about you is sent. |
| Your approximate location | api.aladhan.com | Only if you turn on exact prayer times. Otherwise times are worked out on your Mac and location is not used. |
| Your voice | Apple | Only while you recite aloud, and only if you allow online recognition. Qurany stores nothing. |

Sync is off until you pick a folder. If you do, Qurany keeps a small file per device in that folder, and the folder's
own service (iCloud Drive, Dropbox, Syncthing) moves it. The app is sandboxed. Location, microphone and speech
recognition are asked for only when you use the feature that needs them. The full statement is at
https://qurany.zawalid.com/privacy/.

## Updates

For now, download the new version and replace the app in Applications. Your reading position, bookmarks, notes and
settings stay.

## Languages

English, Arabic (right to left) and French. Change it in Settings.

## Credits and data sources

Qurany stands on the work of others. The Arabic text is from the Tanzil Project (CC BY 3.0). Word timing for
follow-along is quran-align by Collin Fair (CC BY 4.0). Recitations are from everyayah.com and mp3quran.net. Fonts are
Amiri Quran, Amiri and Scheherazade New (SIL Open Font License). Adhan recordings are from Wikimedia Commons. Reciter
photographs are credited in the app. Every item, its licence and what is still unconfirmed is in
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md), and the website lists them at https://qurany.zawalid.com/sources/.

## Licence

Qurany is free to use but is not open source. See [LICENSE](LICENSE). In short: personal use, no resale, no
redistribution of the app or its data.

## Support and feedback

Open an [issue](../../issues) on this repository. Please say your macOS version, the Qurany version (Qurany menu,
About Qurany) and what you were doing. For a wrong translation, introduction or fact, say which ayah or page.

## About this repository

The code is in a private repository, so there is no source here to read or build. This repository exists to host
downloads and this page, and nothing else.
