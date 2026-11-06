# Nitro Beat Lab

Browser-based drum learning game for the Alesis Nitro Mesh. The project is being migrated from a working local v0.3 prototype to v0.4 with song support.

## Song chart library

The `songs/` folder contains five original practice charts and `songs/manifest.json` catalogs them. The charts are preloaded repository assets, but the playable application and accompanying audio are **not yet deployed**. These are not commercial song transcriptions.

Chart notes use quarter-note beat positions, with entries like `[0,"kick"]` and `[0.5,"hat","closed"]`. BPM is fixed per chart. Supported instruments: kick, snare, hat, tom1, tom2, tom3, crash, ride. Hi-hat articulations: closed, open, pedal.

## Next deployment

Publish the v0.4 application files and original licensed backing audio, then enable GitHub Pages at Settings → Pages → Deploy from a branch → main / root. The app will load `songs/manifest.json` and chart/audio assets through relative URLs. Modern Chrome/Edge over HTTPS supports Web MIDI permission requests.

Personal MIDI mappings remain local to each browser; music that users independently import stays local.
