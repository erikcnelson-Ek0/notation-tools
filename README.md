# Notation Instruments

A small set of browser-based, single-file audio and notation tools — playable surfaces, generative
scores, and analysis utilities. Each tool is a single self-contained HTML file: open it in a
browser and it runs, no build step and no dependencies beyond the browser's own Web Audio and
Canvas APIs.

Open `index.html` for the full list, or jump straight to a tool:

- **[XY Pad Instrument](./xy-pad-instrument.html)** — X sweeps register, Y selects a note lane.
  Space bar triggers a randomized arpeggiation. Records a session and exports standard MIDI.
- **[Scale Field Instrument](./scale-field-instrument.html)** — a generative visual score played by
  drawing across it; waveform, scale, and tempo are all live.
- **[Dual Surface Instrument](./dual-surface-instrument.html)** — two playable surfaces sharing one
  master key, for two-handed or two-player performance.
- **[Chord Fold Instrument](./chord-fold-instrument.html)** — drag to fold a plane into a chord;
  density, spread, and inversion follow the gesture. Store snapshots, sequence them, export MIDI
  or a PNG score.
- **[Score Extractor](./score-extractor.html)** — audio in, a beat-aware score you can correct
  (grid, sensitivity, density), MIDI out.
- **[Sound Analyzer](./sound-analyzer.html)** — mel spectrogram, chroma, and onset detection on a
  loaded audio file, live, exporting to JSON, CSV, or MIDI.
- **[Ensemble Performance Controller](./ensemble-performance-controller.html)** — four independent
  players on one shared clock, with cueable groups, transpose, scale-guard, and five generative
  pattern engines.
- **[Note Generator](./note-generator.html)** — five pattern engines turn a key, scale, and tempo
  into a note sequence, with a piano-roll preview and CSV/MIDI export.

## Running locally

Every tool works by opening the `.html` file directly in a browser. A few tools (anything that
loads an audio file for analysis) are more reliable served over `http://` than `file://`, since
some browsers restrict what a `file://` page can do:

```bash
python -m http.server
```

then visit `http://localhost:8000/`.

## Design

All eight tools and the landing page share one visual system, defined in
[`assets/theme.css`](./assets/theme.css): a warm paper ground, hairline rule work, uppercase
micro-type, and a single soft two-tone accent used sparingly. Each tool file still carries a small
amount of its own `<style>` for layout specific to that one tool.

## Structure

```
index.html                              landing page
xy-pad-instrument.html
scale-field-instrument.html
dual-surface-instrument.html
chord-fold-instrument.html
score-extractor.html
sound-analyzer.html
ensemble-performance-controller.html
note-generator.html
assets/theme.css                        shared design tokens + components
```

## License

MIT — see [LICENSE](./LICENSE).
