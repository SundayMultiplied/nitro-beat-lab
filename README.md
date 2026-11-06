# Nitro Beat Lab

Free, browser-based rhythm-game drum trainer for Alesis Nitro Mesh and other USB-MIDI electronic drums.

## Current status (v0.4)

The browser app is committed at [index.html](index.html). Five original practice charts are listed in [songs/manifest.json](songs/manifest.json) and load on demand. Simple synthesized drum-and-bass backing sounds are generated in your browser during play, not streamed from commercial recordings.

- Eight individual kit lanes: kick, snare, closed/open/pedal hi-hat, three toms, crash and ride
- USB-MIDI input in Chrome or Edge; MIDI note event monitor
- Saved pad mappings in browser localStorage (each computer configures its own)
- Falling notes, accuracy, score, practice tempo, loop, calibration
- JSON chart importing from your computer
- Lightweight static app; no account, database or subscription

**Not yet included in this hosted build:** MP3/WAV playback and Standard MIDI File chart import present in the prior local v0.4 prototype. Commercial music is not redistributed.

## Enable sharing with GitHub Pages

Repository owner: Settings → Pages → Build and deployment → Deploy from a branch → `main` → `/(root)` → Save.

Once Pages finishes publishing, use: https://sundaymultiplied.github.io/nitro-beat-lab/

If enabling Pages is already complete, the page may take a short while to become available. Access the site with Chrome or Edge over HTTPS, connect the Nitro kit via a USB-A to USB-B cable, and allow MIDI access in the browser.

## Data format

Each JSON drum chart has `title`, `bpm` and `notes` (an array of tuples like `[0, "kick"]` and `[0.5, "hat", "closed"]`). Timestamps are in quarter-note beats (zero-based). Supported lane names: `kick`, `snare`, `hat`, `tom1`, `tom2`, `tom3`, `crash`, `ride`. Hi-hat articulations: `closed`, `open`, `pedal`.

## Development

No build dependencies: the static app is contained in `index.html`. Load via HTTPS (GitHub Pages) or a local HTTP server on localhost. Do not open directly with `file://` for hosted chart fetching/MIDI.

We use only original chart assets in this repository. Please upload audio or charts only when you have rights to distribute them.
