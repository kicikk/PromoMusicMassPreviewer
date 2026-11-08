# Changelog

Newest first. Download: [latest release](https://github.com/kicikk/PromoMusicMassPreviewer/releases/latest).

## v20261108_b6.2 - 2026-11-08

- **NO now moves the file to the `to_delete` subfolder right away by default**, as the
  manual describes. On a fresh install it only marked the track, so "Purge deleted" had
  nothing to remove. Nothing is lost: files in `to_delete` can be moved back until you
  press "Purge deleted". If you already ran an earlier version, your saved setting stays -
  set `"delete_on_no": true` in `config.json` to get the new behaviour.
- macOS (beta): moving and purging files is now tested on a real build.

## v20261107_b6.1 - 2026-11-07

- macOS (beta): fixed the app quitting right after start (the icon only bounced in
  the Dock). The global hotkey listener read the keyboard layout outside the main
  thread, which macOS 14 and newer does not allow.
- macOS: readable buttons and larger text in the activation window.
- If the program does not start, it now writes `startup.log`, which helps find the
  cause - see "If the app does not start" in [MAC.md](https://github.com/kicikk/PromoMusicMassPreviewer/blob/main/MAC.md).

## v20261106_b6.0 - 2026-11-06

First public release.

- Windows 10/11, 64-bit, a single exe - no installation. The version is part of the
  file name.
- Free 3-day trial, then a free activation key for your computer - see
  [Activation](https://github.com/kicikk/PromoMusicMassPreviewer#activation).
- Smart skip through each track with drop protection, four scan modes, waveform,
  global hotkeys, "now playing" overlay, Auto-cull and Stream Deck control.
- Spotify mode (Premium): an artist's whole discography, an album or a playlist,
  previewed and rated like files.
- English and Polish interface.
- macOS version (beta, added 2026-11-07): `.dmg` for Apple Silicon and for Intel,
  macOS 11 or newer - see [MAC.md](https://github.com/kicikk/PromoMusicMassPreviewer/blob/main/MAC.md).
