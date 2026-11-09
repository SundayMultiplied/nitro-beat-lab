# Nitro Beat Lab

Free, browser-based rhythm-game drum trainer for Alesis Nitro Mesh and other USB-MIDI electronic drums.

## Current status (v0.5 beta)

The browser app is committed at [index.html](index.html). Five original practice charts are listed in [songs/manifest.json](songs/manifest.json) and load on demand. Simple synthesized drum-and-bass backing sounds are generated in your browser during play, not streamed from commercial recordings.

- Eight individual kit lanes: kick, snare, closed/open/pedal hi-hat, three toms, crash and ride
- USB-MIDI input in Chrome or Edge; MIDI note event monitor
- Saved pad mappings in browser localStorage (each computer configures its own)
- Falling notes, accuracy, score, practice tempo, loop, calibration
- JSON chart importing from your computer
- Local MP3/WAV/audio file loading from the Song & Practice Settings panel (audio never uploads)
- Four-beat optional count-in, bar-range practice/loop, position controls and playback-speed tracking
- Lightweight static app; no account, database or subscription

**Not yet included in this hosted build:** Standard MIDI File (.mid) chart importing, automatic drum transcription from MP3 files, and a library of licensed commercial backing tracks. Commercial music is not redistributed. The beta still needs physical kit/audio synchronization testing.

## Try the v0.5 song-practice beta

1. Connect your kit and select one of the built-in practice charts.
2. Expand **Song & Practice Settings**, load a matching MP3/WAV backing track from your computer, and leave **Four-beat count-in** checked.
3. Select **From bar** and **To bar** for a section; use Loop to repeat it. The built-in charts are eight bars long.
4. Press Start, listen to the count-in, and play when the note discs reach the line. Adjust the Tempo slider to slow the song and chart together.
5. If the audio and notes are offset, use **Timing calibration** for small timing adjustments. For a larger mismatch, ensure the imported audio actually matches the chart and contains the same start position.

**Important:** Loading a music file does not transcribe drums or invent a chart. The app requires a matching JSON drum chart; the bundled charts are original practice grooves, not charts for commercial recordings.

On Chrome/Edge the audio file stays in memory on your computer, not in the GitHub repository. Browser music decoding and playback-rate behavior vary by format and browser.

## Enable sharing with GitHub Pages

Repository owner: Settings → Pages → Build and deployment → Deploy from a branch → `main` → `/(root)` → Save.

Once Pages finishes publishing, use: https://sundaymultiplied.github.io/nitro-beat-lab/

If enabling Pages is already complete, the page may take a short while to become available. Access the site with Chrome or Edge over HTTPS, connect the Nitro kit via a USB-A to USB-B cable, and allow MIDI access in the browser.

## Data format

Each JSON drum chart has `title`, `bpm` and `notes` (an array of tuples like `[0, "kick"]` and `[0.5, "hat", "closed"]`). Timestamps are in quarter-note beats (zero-based). Supported lane names: `kick`, `snare`, `hat`, `tom1`, `tom2`, `tom3`, `crash`, `ride`. Hi-hat articulations: `closed`, `open`, `pedal`.

## Development

No build dependencies: the static app is contained in `index.html`. Load via HTTPS (GitHub Pages) or a local HTTP server on localhost. Do not open directly with `file://` for hosted chart fetching/MIDI.

We use only original chart assets in this repository. Please upload audio or charts only when you have rights to distribute them.
